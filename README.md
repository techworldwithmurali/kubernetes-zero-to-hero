
### What is a Kubernetes Ingress Controller?

- A Kubernetes Ingress Controller is a specialized type of controller that manages the routing of external HTTP(S) traffic to services within a Kubernetes cluster.
- It implements the Ingress resource, which provides rules and configurations for routing traffic, enabling external access to internal services in a cluster.
- The Ingress Controller watches the Kubernetes API for changes to Ingress resources and updates its configuration accordingly.

### Features of a Kubernetes Ingress Controller:

1. **Load Balancing:**
   - Distributes incoming traffic across multiple backend services to ensure high availability and reliability.

2. **Path-Based and Host-Based Routing:**
   - Routes traffic to different services based on URL paths and host headers. For example, `/api` can be directed to one service, while `/app` is directed to another, and different domains can route to different services.

3. **SSL/TLS Termination:**
   - Handles SSL/TLS encryption and decryption, allowing secure HTTPS traffic to be routed to services within the cluster.

4. **Custom Rules and Annotations:**
   - Supports custom routing rules for advanced use cases and additional configuration through annotations on Ingress resources.

5. **Integration with External Load Balancers::**
   - Works with external load balancers (e.g., AWS ALB, GCP GLB) to provide additional capabilities and integration with cloud services..

6. **Health Checks and Monitoring:**
   - Monitors the health of backend services and routes traffic only to healthy instances, while also providing metrics and logs for monitoring traffic patterns, performance, and potential issues.
  
------
### Lab Session: Installing and Configuring an AWS Load Balancer Ingress Controller

#### Prerequisites:
1. **Install AWS CLI**: Ensure AWS CLI is installed and configured with appropriate credentials.
2. **Install kubectl**: Install kubectl to interact with your Kubernetes cluster.
3. **Create and Connect to the EKS Cluster**: Ensure you have created an EKS cluster and configured kubectl to connect to it.

#### Step 1: Create the OIDC Provider for EKS Cluster
- **Name**: dev-cluster
- Follow AWS documentation to create the OIDC provider for your EKS cluster.

#### Step 2: Creating a Policy for Your Service Account
- **Policy Name**: dev-ingress-controller-policy
- **Path**: Specify the path for the policy JSON file (`dev-ingress-controller-policy.json`).

#### Step 3: Creating an IAM Role and Attaching the Policy
- **Name**: dev-ingress-role
- **Role Type**: Use web identity federation for the IAM role.
- **Service Account**: `system:serviceaccount:kube-system:aws-load-balancer-controller`

#### Step 4: Install cert-manager
- Run the following command to install cert-manager:
  ```bash
  kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.14.2/cert-manager.yaml
  ```
- Reference URL for cert-manager releases: [Cert-Manager Releases](https://github.com/cert-manager/cert-manager/releases)

#### Step 5: Verify cert-manager Deployment
- Check if cert-manager components are deployed correctly:
  ```bash
  kubectl get all -n cert-manager
  ```

#### Step 6: Download AWS Load Balancer Ingress Controller YAML Files
- Download the AWS Load Balancer Ingress Controller YAML files from the following URL:
  [AWS Load Balancer Controller Install](https://github.com/kubernetes-sigs/aws-load-balancer-controller/tree/v2.7.1/docs/install)
- Update the YAML files with your cluster name, image tag, and service account annotations as needed.

#### Step 7: Apply Kubernetes Ingress Controller Manifest File
- Apply the modified Kubernetes Ingress Controller manifest file (e.g., `ingress-controler-alb.yaml`) using:
  ```bash
  kubectl apply -f ingress-controler-alb.yaml
  ```

#### Step 8: Verify Ingress Controller Deployment
- Check if the Ingress Controller components are deployed correctly in the `kube-system` namespace:
  ```bash
  kubectl get all -n kube-system
  ```

# Deploy Sample Ingress Resource without SSL

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
  name: nginx-app
  namespace: dev
  annotations:
    alb.ingress.kubernetes.io/scheme: internet-facing
    alb.ingress.kubernetes.io/tags: app=techworldwithmurali,Team=DevOps
spec:
  ingressClassName: alb
  rules:
    - host: dev.telugudevopsguru.in
      http:
        paths:
          - path: /index.html
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

### Explanation:

- **Namespace (`ns.yaml`)**: Creates a namespace named `dev`.
- **Deployment (`deployment.yaml`)**: Deploys an nginx container using the latest image of nginx, exposing port 80.
- **Service (`service.yaml`)**: Exposes the nginx deployment on port 80 using a NodePort type service.
- **Ingress (`ingress.yaml`)**: Defines an Ingress resource named `nginx-app` in the `dev` namespace, specifying that requests to `dev.techworldwithmurali.in/index.html` should route to the `nginx-app` service.

Make sure to replace `dev.techworldwithmurali.in` with your actual domain name or DNS name pointing to your Kubernetes cluster.

After applying these configurations, Kubernetes will deploy the nginx application, expose it via a service, and configure the Ingress to route traffic to it based on the specified rules.
