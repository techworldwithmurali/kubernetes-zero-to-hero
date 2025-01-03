#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

### What is ExternalDNS?

1. **Kubernetes Add-On**: ExternalDNS is an add-on for Kubernetes clusters.
   
2. **DNS Management**: It automates the management of DNS records for Kubernetes services and ingresses.

3. **Monitors Kubernetes Resources**: ExternalDNS monitors Kubernetes resources such as services and ingresses for changes.

4. **Updates DNS Providers**: It updates DNS records in external DNS providers (e.g., AWS Route 53, Google Cloud DNS, Azure DNS) based on changes in Kubernetes resources.

### Why Use ExternalDNS?

1. **Dynamic DNS Updates**: Manages DNS records for Kubernetes services that may have dynamic IP addresses or endpoints due to scaling or updates.

2. **Cloud Provider Integration**: Integrates with major cloud DNS providers, facilitating consistent DNS management across different cloud environments.

3. **Automation**: Automates the process of updating DNS records, reducing manual overhead and potential errors.

4. **Standardization**: Enforces a standardized approach to DNS management across Kubernetes clusters and cloud environments.

5. **Reliability and Consistency**: Ensures that DNS records are updated promptly and accurately, maintaining service accessibility and reliability.


# Lab Session: Deploy External DNS in Kubernetes

## Step 1: Create the OIDC Provider for EKS Cluster
Name: dev-cluster

## Step 2: Creating a Policy for Your Service Account
Name: dev-external-policy

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "route53:ChangeResourceRecordSets"
            ],
            "Resource": [
                "arn:aws:route53:::hostedzone/*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "route53:ListHostedZones",
                "route53:ListResourceRecordSets"
            ],
            "Resource": [
                "*"
            ]
        }
    ]
}
```

## Step 3: Creating an IAM Role and Attaching the Policy for Your Service Account
Name: dev-external-dns-role

It should create the IAM role through web identity federation.

Update the Trust relationship:

```
system:serviceaccount:kube-system:external-dns
```

## Step 4: Download the external DNS manifest file
[external-dns.yaml](https://github.com/kubernetes-sigs/external-dns/releases/tag/v0.14.0)

Update the service account annotations:

```yaml
---
apiVersion: v1
kind: ServiceAccount
metadata:
  name: external-dns
  namespace: kube-system
  annotations:
    eks.amazonaws.com/role-arn: arn:aws:iam::424432388155:role/external-dns
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  name: external-dns
rules:
- apiGroups: [""]
  resources: ["services","endpoints","pods"]
  verbs: ["get","watch","list"]
- apiGroups: ["extensions","networking.k8s.io"]
  resources: ["ingresses"]
  verbs: ["get","watch","list"]
- apiGroups: [""]
  resources: ["nodes"]
  verbs: ["list","watch"]
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: external-dns-viewer
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: external-dns
subjects:
- kind: ServiceAccount
  name: external-dns
  namespace: kube-system
---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: external-dns
  namespace: kube-system
spec:
  strategy:
    type: Recreate
  selector:
    matchLabels:
      app: external-dns
  template:
    metadata:
      labels:
        app: external-dns
    spec:
      serviceAccountName: external-dns
      containers:
      - name: external-dns
        image: k8s.gcr.io/external-dns/external-dns:v0.12.0
        args:
        - --source=service
        - --source=ingress
        - --provider=aws
        - --policy=upsert-only
        - --aws-zone-type=public
        - --registry=txt
        - --txt-owner-id=eks-identifier
      securityContext:
        fsGroup: 65534
```

## Step 5: Deploy External DNS
```bash
kubectl apply -f external-dns.yaml
```
### ExternalDNS Policies

- **upsert-only:**
  ```bash
  --policy=upsert-only
  ```
  With this policy, ExternalDNS will only create or update DNS records but will not delete any existing records. It's a safe option to ensure that ExternalDNS doesn't remove records that are not present in the Kubernetes cluster.

- **sync:**
  ```bash
  --policy=sync
  ```
  This policy ensures that the DNS records in the DNS provider match the current state of the Kubernetes resources. It will create, update, or delete DNS records based on the current state of the resources.

- **create-only:**
  ```bash
  --policy=create-only
  ```
  With this policy, ExternalDNS will only create new DNS records. It won't update or delete existing records. This can be useful when you want ExternalDNS to be more cautious and avoid making changes to existing records.

- **delete:**
  ```bash
  --policy=delete
  ```
  This policy will delete DNS records that are associated with resources in the Kubernetes cluster but are no longer present. It can be more aggressive in removing outdated records.


## Step 6: Deploy a sample application and Ingress, and verify whether the record is automatically created in Route 53 or not.
### Deploy Sample Ingress Resource With SSL

**Prerequisites:**

You must have an Ingress controller for the Ingress resource to take effect; simply creating an Ingress resource alone will not suffice.

### Step 1: Create the Namespace

Save the following content in a file named `ns.yaml`:

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: dev
```

Apply the namespace configuration:

```bash
kubectl apply -f ns.yaml
```

### Step 2: Create the Deployment

Save the following content in a file named `deployment.yaml`:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-app
  namespace: dev
spec:
  selector:
    matchLabels:
      app: nginx-app
  replicas: 1
  template:
    metadata:
      labels:
        app: nginx-app
    spec:
      containers:
      - image: nginx:latest
        name: nginx-app
        ports:
        - containerPort: 80
```

Apply the deployment configuration:

```bash
kubectl apply -f deployment.yaml
```

### Step 3: Create the Service

Save the following content in a file named `service.yaml`:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: nginx-app
  namespace: dev
spec:
  ports:
  - port: 80
    targetPort: 80
    protocol: TCP
  type: NodePort
  selector:
    app: nginx-app
```

Apply the service configuration:

```bash
kubectl apply -f service.yaml
```

### Step 4: Create the Ingress

Save the following content in a file named `ingress.yaml`:

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: dev-ingress
  namespace: dev
  annotations:
    alb.ingress.kubernetes.io/scheme: internet-facing
    alb.ingress.kubernetes.io/tags: app=techworldwithmurali,Team=DevOps
    alb.ingress.kubernetes.io/certificate-arn: arn:aws:acm:us-east-1:338240650890:certificate/1ba71dbc-ed97-46b1-a2b3-16c38616b48c
    alb.ingress.kubernetes.io/listen-ports: '[{"HTTP": 80}, {"HTTPS":443}]'
    alb.ingress.kubernetes.io/ssl-redirect: '443'
spec:
  ingressClassName: alb
  rules:
    - host: nginx-app.techworldwithmurali.in
      http:
        paths:
          - path: /
            pathType: Exact
            backend:
              service:
                name: nginx-app
                port:
                  number: 80

```

Apply the ingress configuration:

```bash
kubectl apply -f ingress.yaml
```
### Access the application using below url
```yaml
https://nginx-app.techworldwithmurali.in
```
### Explanation:

- **Namespace (`ns.yaml`)**: Creates a namespace named `dev`.
- **Deployment (`deployment.yaml`)**: Deploys an nginx container using the latest image of nginx, exposing port 80.
- **Service (`service.yaml`)**: Exposes the nginx deployment on port 80 using a NodePort type service.
- **Ingress (`ingress.yaml`)**: Defines an Ingress resource named `nginx-app` in the `dev` namespace, specifying that requests to `dev.techworldwithmurali.in/index.html` should route to the `nginx-app` service.

Make sure to replace `nginx-app.techworldwithmurali.in` with your actual domain name or DNS name pointing to your Kubernetes cluster.

After applying these configurations, Kubernetes will deploy the nginx application, expose it via a service, and configure the Ingress to route traffic to it based on the specified rules.

