### Explanation of EFK: Elasticsearch, Fluentd, Kibana

EFK is a stack commonly used for log aggregation and analysis in Kubernetes environments. It consists of:

- **Elasticsearch**: A distributed, RESTful search and analytics engine designed for horizontal scalability, real-time search, and analysis of data.

- **Fluentd**: An open-source data collector that allows you to unify data collection and consumption for better use and understanding. Fluentd helps in collecting, filtering, and forwarding logs to Elasticsearch for storage and analysis.

- **Kibana**: An open-source data visualization dashboard for Elasticsearch. It provides visualization capabilities on top of data indexed in Elasticsearch and allows you to perform advanced data analysis and search interaction.


### Lab Session - Setting up Elasticsearch and Kibana in AWS

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

```bash
kubectl apply -f fluentbit.yaml
```

#### Step 8: Update Elasticsearch Security Roles Mapping

Update the internal database of Elasticsearch security roles mapping for the 'all_access' role to include the IAM role:

```bash
curl -sS -u "admin:Admin@2580" -X PATCH https://search-dev-es-ujos6gbqlrsis3dsh4axnxlq5e.us-east-1.es.amazonaws.com/_opendistro/_security/api/rolesmapping/all_access?pretty -H 'Content-Type: application/json' -d '[{"op": "add", "path": "/backend_roles", "value": ["arn:aws:iam::714771635465:role/dev-fluent-bit-iam-role"]}]'
```

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

#### Step 1: Deploy Elasticsearch on AWS

Follow AWS documentation or use an Elasticsearch managed service (such as Amazon Elasticsearch Service) to deploy Elasticsearch. Ensure it is accessible within your AWS environment.

#### Step 2: Deploy Kibana on AWS

Deploy Kibana on AWS, connecting it to your Elasticsearch cluster or instance. Kibana should be configured to interact with Elasticsearch for data visualization and analysis.

### What is Fluentd?

Fluentd is an open-source data collector designed to unify data collection and consumption. It supports various inputs and outputs, making it versatile for collecting logs from different sources and forwarding them to multiple destinations.

### Lab Session - Deploying Fluentd as a Daemonset for Log Collection and sending logs to Elasticsearch

#### Step 1: Create Fluentd Daemonset Manifest

Create a Fluentd DaemonSet manifest file (`fluentd-daemonset.yaml`) with the following configuration:

```yaml
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: fluentd
  namespace: kube-system
spec:
  selector:
    matchLabels:
      app: fluentd
  template:
    metadata:
      labels:
        app: fluentd
    spec:
      containers:
      - name: fluentd
        image: fluent/fluentd
        resources:
          limits:
            memory: 200Mi
            cpu: 100m
          requests:
            memory: 100Mi
            cpu: 50m
        volumeMounts:
        - name: varlog
          mountPath: /var/log
        - name: varlibdockercontainers
          mountPath: /var/lib/docker/containers
          readOnly: true
      volumes:
      - name: varlog
        hostPath:
          path: /var/log
      - name: varlibdockercontainers
        hostPath:
          path: /var/lib/docker/containers
```

#### Step 2: Apply Fluentd DaemonSet

Apply the Fluentd DaemonSet to deploy Fluentd across all nodes in your Kubernetes cluster:

```bash
kubectl apply -f fluentd-daemonset.yaml
```

#### Step 3: Verify Fluentd Deployment

Check Fluentd pods are running and collecting logs:

```bash
kubectl get pods -n kube-system
```

### Summary

EFK (Elasticsearch, Fluentd, Kibana) stack is a powerful combination for log aggregation, storage, visualization, and analysis in Kubernetes environments. Elasticsearch serves as the backend for storing and indexing logs, Fluentd collects and forwards logs to Elasticsearch, and Kibana provides a user-friendly interface for visualizing and analyzing log data. Setting up Elasticsearch, Kibana, and Fluentd ensures efficient log management and monitoring capabilities within Kubernetes clusters.
