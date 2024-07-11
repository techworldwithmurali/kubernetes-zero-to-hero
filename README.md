
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
- Apply the modified Kubernetes Ingress Controller manifest file (e.g., `ingress.yaml`) using:
  ```bash
  kubectl apply -f ingress.yaml
  ```

#### Step 8: Verify Ingress Controller Deployment
- Check if the Ingress Controller components are deployed correctly in the `kube-system` namespace:
  ```bash
  kubectl get all -n kube-system
  ```

