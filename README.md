### Explanation of EFK: Elasticsearch, Fluentd, Kibana

EFK is a stack commonly used for log aggregation and analysis in Kubernetes environments. It consists of:

- **Elasticsearch**: A distributed, RESTful search and analytics engine designed for horizontal scalability, real-time search, and analysis of data.

- **Fluentd**: An open-source data collector that allows you to unify data collection and consumption for better use and understanding. Fluentd helps in collecting, filtering, and forwarding logs to Elasticsearch for storage and analysis.

- **Kibana**: An open-source data visualization dashboard for Elasticsearch. It provides visualization capabilities on top of data indexed in Elasticsearch and allows you to perform advanced data analysis and search interaction.


### Lab Session - Setting up Elasticsearch / Opensaerch a in AWS

1. **Sign In to AWS Console:**
   - Navigate to [AWS Management Console](https://aws.amazon.com) and sign in.

2. **Access OpenSearch Service:**
   - Under Analytics, select "Amazon OpenSearch Service."

3. **Create Domain:**
   - Choose "Create domain."

4. **Domain Name:**
   - Enter a name for your domain (e.g., "movies").

5. **Domain Creation Method:**
   - Choose "Standard create."

6. **Templates:**
   - Select "Dev/test."

7. **Deployment Option:**
   - Choose "Domain with standby."

8. **Version:**
   - Select the latest version available.

9. **Network Configuration:**
   - Choose "Public access" for simplicity in this tutorial.

10. **Fine-Grained Access Control:**
    - Enable fine-grained access control.
    - Create a master user with a username and password.

11. **Access Policy:**
    - Choose "Only use fine-grained access control" for access policy.

12. **Ignore Additional Settings:**
    - Skip configurations related to SAML authentication, Amazon Cognito authentication, and other advanced settings for now.

13. **Create Domain:**
    - Review your settings and choose "Create."

14. **Domain Initialization:**
    - Wait for the domain to initialize. This process typically takes 15–30 minutes but can vary depending on configuration.

15. **Access Endpoint:**
    - Once initialized, note the domain endpoint (e.g., `https://search-my-domain.us-east-1.es.amazonaws.com`) from the General Information section.


### Lab Session - Deploying Fluent Bit for Log Collection

#### Step 1: Create Namespace

Create a namespace named `logging`:

```bash
kubectl create namespace logging
```

#### Step 2: Create the OIDC Provider for EKS Cluster

1. **Open the Amazon EKS Console**
   - Go to [Amazon EKS Console](https://console.aws.amazon.com/eks/home#/clusters).

2. **Select Your Cluster**
   - In the left pane, select **Clusters**.
   - On the Clusters page, click on the name of your cluster.

3. **Retrieve the OIDC Provider URL**
   - In the Details section on the **Overview** tab, note the value of the **OpenID Connect provider URL**.

4. **Open the IAM Console**
   - Go to [IAM Console](https://console.aws.amazon.com/iam/).

5. **Navigate to Identity Providers**
   - In the left navigation pane, choose **Identity Providers** under **Access management**.

6. **Check for Existing Provider**
   - If a provider is listed that matches the URL for your cluster, then you already have a provider for your cluster.
   - If a provider isn't listed that matches the URL for your cluster, then you need to create one.

7. **Create a New Provider**
   - Click on **Add provider**.

8. **Configure the Provider**
   - For **Provider type**, select **OpenID Connect**.
   - For **Provider URL**, enter the OIDC provider URL for your cluster, and then choose **Get thumbprint**.
   - For **Audience**, enter `sts.amazonaws.com`.
   - Choose **Add provider**.

#### Step 3: Create a Policy for Your Service Account

Create an IAM policy named `dev-fluent-bit-iam-policy`:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "es:ESHttp*"
            ],
            "Resource": "arn:aws:es:us-east-1:<your-account-id>:domain/dev-es",
            "Effect": "Allow"
        }
    ]
}

```
Replace <your-account-id> with your actual AWS account ID.
#### Step 4: Create an IAM Role and Attach the Policy for Your Service Account

Create an IAM role named `dev-fluent-bit-iam-role` with a trust relationship for your EKS cluster's OIDC provider. Attach the `dev-fluent-bit-iam-policy` to this role.

#### Step 5: Create the Service Account and Include the IAM Role Annotation

Create a service account in Kubernetes with the IAM role annotation:

```yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  labels:
    app: fluent-bit
  annotations:
    eks.amazonaws.com/role-arn: arn:aws:iam::714771635465:role/dev-fluent-bit-iam-role
  name: fluent-bit
  namespace: logging
```

Apply the service account configuration:

```bash
kubectl apply -f fluent-bit-service-account.yaml
```
Make sure to replace arn:aws:iam::714771635465:role/dev-fluent-bit-iam-role with your actual IAM role ARN for Fluent Bit. This annotation ensures that the service account fluent-bit in the logging namespace has the necessary permissions to perform actions allowed by the IAM role dev-fluent-bit-iam-role.

#### Step 6: Update the Trust Relationship of the IAM Role

Update the trust relationship of the `dev-fluent-bit-iam-role` role:

From:

```json
"oidc.eks.us-east-1.amazonaws.com/id/36768CCADCE3B1429AF675DA5E5304E1:aud": "sts.amazonaws.com"
```

To:

```json
"oidc.eks.us-east-1.amazonaws.com/id/36768CCADCE3B1429AF675DA5E5304E1:sub": "system:serviceaccount:logging:fluent-bit"
```

#### Step 7: Deploy Fluent Bit as a DaemonSet

Create a DaemonSet manifest file named `fluentbit.yaml` and deploy it. Ensure the service account name and namespace are correct.

```yaml
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  name: fluent-bit-read
rules:
- apiGroups: [""]
  resources:
  - namespaces
  - pods
  verbs: ["get", "list", "watch"]
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: fluent-bit-read
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: fluent-bit-read
subjects:
- kind: ServiceAccount
  name: fluent-bit
  namespace: logging
---
apiVersion: v1
kind: ConfigMap
metadata:
  name: fluent-bit-config
  namespace: logging
  labels:
    k8s-app: fluent-bit
data:
  # Configuration files: server, input, filters and output
  # ======================================================
  fluent-bit.conf: |
    [SERVICE]
        Flush         1
        Log_Level     info
        Daemon        off
        Parsers_File  parsers.conf
        HTTP_Server   On
        HTTP_Listen   0.0.0.0
        HTTP_Port     2020

    @INCLUDE input-kubernetes.conf
    @INCLUDE filter-kubernetes.conf
    @INCLUDE output-elasticsearch.conf

  input-kubernetes.conf: |
    [INPUT]
        Name              tail
        Tag               kube.*
        Path              /var/log/containers/*.log
        Parser            docker
        DB                /var/log/flb_kube.db
        Mem_Buf_Limit     50MB
        Skip_Long_Lines   On
        Refresh_Interval  10

  filter-kubernetes.conf: |
    [FILTER]
        Name                kubernetes
        Match               kube.*
        Kube_URL            https://kubernetes.default.svc:443
        Kube_CA_File        /var/run/secrets/kubernetes.io/serviceaccount/ca.crt
        Kube_Token_File     /var/run/secrets/kubernetes.io/serviceaccount/token
        Kube_Tag_Prefix     kube.var.log.containers.
        Merge_Log           On
        Merge_Log_Key       log_processed
        K8S-Logging.Parser  On
        K8S-Logging.Exclude Off

  output-elasticsearch.conf: |
    [OUTPUT]
        Name            es
        Match           *
        Host            search-dev-es-zuiy5hqs7l4kp27kwpwkmkhvbu.us-east-1.es.amazonaws.com
        Port            443
        TLS             On
        AWS_Auth        On
        Index           fluent_bit
        AWS_Region      us-east-1
        Retry_Limit     6

  parsers.conf: |
    [PARSER]
        Name   apache
        Format regex
        Regex  ^(?<host>[^ ]*) [^ ]* (?<user>[^ ]*) \[(?<time>[^\]]*)\] "(?<method>\S+)(?: +(?<path>[^\"]*?)(?: +\S*)?)?" (?<code>[^ ]*) (?<size>[^ ]*)(?: "(?<referer>[^\"]*)" "(?<agent>[^\"]*)")?$
        Time_Key time
        Time_Format %d/%b/%Y:%H:%M:%S %z

    [PARSER]
        Name   apache2
        Format regex
        Regex  ^(?<host>[^ ]*) [^ ]* (?<user>[^ ]*) \[(?<time>[^\]]*)\] "(?<method>\S+)(?: +(?<path>[^ ]*) +\S*)?" (?<code>[^ ]*) (?<size>[^ ]*)(?: "(?<referer>[^\"]*)" "(?<agent>[^\"]*)")?$
        Time_Key time
        Time_Format %d/%b/%Y:%H:%M:%S %z

    [PARSER]
        Name   apache_error
        Format regex
        Regex  ^\[[^ ]* (?<time>[^\]]*)\] \[(?<level>[^\]]*)\](?: \[pid (?<pid>[^\]]*)\])?( \[client (?<client>[^\]]*)\])? (?<message>.*)$

    [PARSER]
        Name   nginx
        Format regex
        Regex ^(?<remote>[^ ]*) (?<host>[^ ]*) (?<user>[^ ]*) \[(?<time>[^\]]*)\] "(?<method>\S+)(?: +(?<path>[^\"]*?)(?: +\S*)?)?" (?<code>[^ ]*) (?<size>[^ ]*)(?: "(?<referer>[^\"]*)" "(?<agent>[^\"]*)")?$
        Time_Key time
        Time_Format %d/%b/%Y:%H:%M:%S %z

    [PARSER]
        Name   json
        Format json
        Time_Key time
        Time_Format %d/%b/%Y:%H:%M:%S %z

    [PARSER]
        Name        docker
        Format      json
        Time_Key    time
        Time_Format %Y-%m-%dT%H:%M:%S.%L
        Time_Keep   On

    [PARSER]
        Name        syslog
        Format      regex
        Regex       ^\<(?<pri>[0-9]+)\>(?<time>[^ ]* {1,2}[^ ]* [^ ]*) (?<host>[^ ]*) (?<ident>[a-zA-Z0-9_\/\.\-]*)(?:\[(?<pid>[0-9]+)\])?(?:[^\:]*\:)? *(?<message>.*)$
        Time_Key    time
        Time_Format %b %d %H:%M:%S
---
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: fluent-bit
  namespace: logging
  labels:
    k8s-app: fluent-bit-logging
    version: v1
    kubernetes.io/cluster-service: "true"

spec:
  selector:
    matchLabels:
      k8s-app: fluent-bit-logging
  template:
    metadata:
      labels:
        k8s-app: fluent-bit-logging
        version: v1
        kubernetes.io/cluster-service: "true"
      annotations:
        prometheus.io/scrape: "true"
        prometheus.io/port: "2020"
        prometheus.io/path: /api/v1/metrics/prometheus
    spec:
      containers:
      - name: fluent-bit
        image: amazon/aws-for-fluent-bit:latest
        imagePullPolicy: Always
        ports:
          - containerPort: 2020
        volumeMounts:
        - name: varlog
          mountPath: /var/log
        - name: varlibdockercontainers
          mountPath: /var/lib/docker/containers
          readOnly: true
        - name: fluent-bit-config
          mountPath: /fluent-bit/etc/
      terminationGracePeriodSeconds: 10
      volumes:
      - name: varlog
        hostPath:
          path: /var/log
      - name: varlibdockercontainers
        hostPath:
          path: /var/lib/docker/containers
      - name: fluent-bit-config
        configMap:
          name: fluent-bit-config
      serviceAccountName: fluent-bit

```

Note: Before deploying the DaemonSet, ensure to update the Elasticsearch URL (`Host`) and AWS region (`AWS_Region`) in the `output-elasticsearch.conf` section of `fluentbit.yaml` according to your OpenSearch (formerly known as Elasticsearch) configuration and region.


```bash
kubectl apply -f fluentbit.yaml
```

#### Step 8: Update Elasticsearch Security Roles Mapping

Update the internal database of Elasticsearch security roles mapping for the 'all_access' role to include the IAM role:

```bash
curl -sS -u "admin:Admin@2580" -X PATCH https://search-dev-es-ujos6gbqlrsis3dsh4axnxlq5e.us-east-1.es.amazonaws.com/_opendistro/_security/api/rolesmapping/all_access?pretty -H 'Content-Type: application/json' -d '[{"op": "add", "path": "/backend_roles", "value": ["arn:aws:iam::714771635465:role/dev-fluent-bit-iam-role"]}]'
```
Note: Before executing the CURL command, ensure to update the username (`admin`) and password (`Admin@2580`) with your Elasticsearch credentials, and replace the URL (`https://search-dev-es-ujos6gbqlrsis3dsh4axnxlq5e.us-east-1.es.amazonaws.com`) with your actual Elasticsearch endpoint URL.


#### Step 9: Deploy a Sample Application

Create a deployment manifest file for a sample application named `php-apache` and deploy it:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: php-apache
spec:
  selector:
    matchLabels:
      run: php-apache
  template:
    metadata:
      labels:
        run: php-apache
    spec:
      containers:
      - name: php-apache
        image: registry.k8s.io/hpa-example
        ports:
        - containerPort: 80
        resources:
          limits:
            cpu: 500m
          requests:
            cpu: 200m
---
apiVersion: v1
kind: Service
metadata:
  name: php-apache
  labels:
    run: php-apache
spec:
  type: NodePort
  ports:
  - port: 80
    targetPort: 80
    nodePort: 30000
  selector:
    run: php-apache
```

Apply the deployment and service:

```bash
kubectl apply -f php-apache-deployment.yaml
```

#### Step 10: Access the Application

Perform port forwarding to access the application:

```bash
kubectl port-forward service/php-apache 8080:80
```

Access the application using the following URL:

URL: [http://127.0.0.1:8080/](http://127.0.0.1:8080/)

#### Step 11: Review Logs in the Kibana Dashboard

Access the Kibana Dashboard to review the logs collected by Fluent Bit:

URL: [https://search-dev-es-zuiy5hqs7l4kp27kwpwkmkhvbu.us-east-1.es.amazonaws.com/_dashboards](https://search-dev-es-zuiy5hqs7l4kp27kwpwkmkhvbu.us-east-1.es.amazonaws.com/_dashboards)

