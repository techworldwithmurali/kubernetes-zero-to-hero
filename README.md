## What is Cluster Autoscaler

- Cluster Autoscaler automatically adjusts the size of a Kubernetes cluster by adding or removing nodes based on the current workload.
- It works in conjunction with the Horizontal Pod Autoscaler (HPA) to ensure that the cluster has enough resources to run all scheduled pods and scales down the cluster when there are idle nodes.
- The Cluster Autoscaler is particularly useful in cloud environments where you pay for the resources you use, as it helps optimize costs by only running the necessary number of nodes.

### Key Features and Functionality of Cluster Autoscaler:

1. **Dynamic Scaling**:
   - Cluster Autoscaler dynamically adjusts the number of nodes in a cluster based on the current workload.
   - When pods cannot be scheduled due to resource constraints (such as insufficient CPU or memory), Cluster Autoscaler will provision additional nodes to accommodate the demand.

2. **Integration with Cloud Providers**:
   - It integrates with cloud provider APIs to manage the lifecycle of virtual machines (VMs) or instances that form the Kubernetes nodes.
   - This allows it to seamlessly add or remove nodes in response to workload changes.

3. **Scale Down Considerations**:
    - Cluster Autoscaler also includes safeguards to prevent premature scale-down events, ensuring that nodes are only removed when their pods can be safely evicted or rescheduled elsewhere.

### Benefits:

- **Scalability**: Ensures that the Kubernetes cluster can handle varying workloads without manual intervention.
- **Reliability**: Improves application reliability by maintaining adequate resources for all scheduled pods.
- **Cost Optimization**: Optimizes cloud infrastructure costs by scaling resources based on actual demand.


# Setting up Kubernetes Cluster Autoscaler on AWS EKS

Follow these steps to set up and test the Kubernetes Cluster Autoscaler on an AWS EKS cluster.

### Prerequisites

- AWS CLI configured with appropriate permissions.
- Kubernetes cluster running on AWS EKS.
## Step 1: Set up an EKS cluster on AWS

Ensure your EKS cluster is configured and running.

## Step 2: Review the prerequisites required for the Cluster Autoscaler

- **k8s.io/cluster-autoscaler/dev-cluster**
  - **Owned**: yes
- **k8s.io/cluster-autoscaler/enabled**
  - **Value**: true
  - **Owned**: yes

## Step 3: Create IAM OIDC provider

Enable IAM OIDC provider for your EKS cluster.

## Step 4: Create IAM policy for Cluster Autoscaler

### Name: dev-ca-policy

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "autoscaling:DescribeAutoScalingGroups",
                "autoscaling:DescribeAutoScalingInstances",
                "autoscaling:DescribeLaunchConfigurations",
                "autoscaling:DescribeTags",
                "autoscaling:SetDesiredCapacity",
                "autoscaling:TerminateInstanceInAutoScalingGroup",
                "ec2:DescribeLaunchTemplateVersions"
            ],
            "Resource": "*",
            "Effect": "Allow"
        }
    ]
}
```

## Step 5: Create IAM role for Cluster Autoscaler

### Name: dev-ca-role

```plaintext
system:serviceaccount:kube-system:cluster-autoscaler
```

## Step 6: Deploy the Kubernetes Cluster Autoscaler onto the EKS cluster

Follow the deployment instructions for the Cluster Autoscaler.
```yaml
---
apiVersion: v1
kind: ServiceAccount
metadata:
  labels:
    k8s-addon: cluster-autoscaler.addons.k8s.io
    k8s-app: cluster-autoscaler
  annotations:
    eks.amazonaws.com/role-arn: arn:aws:iam::338240650890:role/ca-role
  name: cluster-autoscaler
  namespace: kube-system
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  name: cluster-autoscaler
  labels:
    k8s-addon: cluster-autoscaler.addons.k8s.io
    k8s-app: cluster-autoscaler
rules:
  - apiGroups: [""]
    resources: ["events", "endpoints"]
    verbs: ["create", "patch"]
  - apiGroups: [""]
    resources: ["pods/eviction"]
    verbs: ["create"]
  - apiGroups: [""]
    resources: ["pods/status"]
    verbs: ["update"]
  - apiGroups: [""]
    resources: ["endpoints"]
    resourceNames: ["cluster-autoscaler"]
    verbs: ["get", "update"]
  - apiGroups: [""]
    resources: ["nodes"]
    verbs: ["watch", "list", "get", "update"]
  - apiGroups: [""]
    resources:
      - "namespaces"
      - "pods"
      - "services"
      - "replicationcontrollers"
      - "persistentvolumeclaims"
      - "persistentvolumes"
    verbs: ["watch", "list", "get"]
  - apiGroups: ["extensions"]
    resources: ["replicasets", "daemonsets"]
    verbs: ["watch", "list", "get"]
  - apiGroups: ["policy"]
    resources: ["poddisruptionbudgets"]
    verbs: ["watch", "list"]
  - apiGroups: ["apps"]
    resources: ["statefulsets", "replicasets", "daemonsets"]
    verbs: ["watch", "list", "get"]
  - apiGroups: ["storage.k8s.io"]
    resources: ["storageclasses", "csinodes", "csidrivers", "csistoragecapacities"]
    verbs: ["watch", "list", "get"]
  - apiGroups: ["batch", "extensions"]
    resources: ["jobs"]
    verbs: ["get", "list", "watch", "patch"]
  - apiGroups: ["coordination.k8s.io"]
    resources: ["leases"]
    verbs: ["create"]
  - apiGroups: ["coordination.k8s.io"]
    resourceNames: ["cluster-autoscaler"]
    resources: ["leases"]
    verbs: ["get", "update"]
---
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  name: cluster-autoscaler
  namespace: kube-system
  labels:
    k8s-addon: cluster-autoscaler.addons.k8s.io
    k8s-app: cluster-autoscaler
rules:
  - apiGroups: [""]
    resources: ["configmaps"]
    verbs: ["create","list","watch"]
  - apiGroups: [""]
    resources: ["configmaps"]
    resourceNames: ["cluster-autoscaler-status", "cluster-autoscaler-priority-expander"]
    verbs: ["delete", "get", "update", "watch"]

---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: cluster-autoscaler
  labels:
    k8s-addon: cluster-autoscaler.addons.k8s.io
    k8s-app: cluster-autoscaler
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: cluster-autoscaler
subjects:
  - kind: ServiceAccount
    name: cluster-autoscaler
    namespace: kube-system

---
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: cluster-autoscaler
  namespace: kube-system
  labels:
    k8s-addon: cluster-autoscaler.addons.k8s.io
    k8s-app: cluster-autoscaler
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: Role
  name: cluster-autoscaler
subjects:
  - kind: ServiceAccount
    name: cluster-autoscaler
    namespace: kube-system

---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: cluster-autoscaler
  namespace: kube-system
  labels:
    app: cluster-autoscaler
spec:
  replicas: 1
  selector:
    matchLabels:
      app: cluster-autoscaler
  template:
    metadata:
      labels:
        app: cluster-autoscaler
      annotations:
        prometheus.io/scrape: 'true'
        prometheus.io/port: '8085'
    spec:
      priorityClassName: system-cluster-critical
      securityContext:
        runAsNonRoot: true
        runAsUser: 65534
        fsGroup: 65534
      serviceAccountName: cluster-autoscaler
      containers:
        - image: registry.k8s.io/autoscaling/cluster-autoscaler:v1.28.2
          name: cluster-autoscaler
          resources:
            limits:
              cpu: "2"
              memory: 2500Mi
            requests:
              cpu: 100m
              memory: 600Mi
          command:
            - ./cluster-autoscaler
            - --v=4
            - --stderrthreshold=info
            - --cloud-provider=aws
            - --skip-nodes-with-local-storage=false
            - --expander=least-waste
            - --node-group-auto-discovery=asg:tag=k8s.io/cluster-autoscaler/enabled,k8s.io/cluster-autoscaler/dev-cluster
            - --balance-similar-node-groups
            - --skip-nodes-with-system-pods=false
          volumeMounts:
            - name: ssl-certs
              mountPath: /etc/ssl/certs/ca-certificates.crt #/etc/ssl/certs/ca-bundle.crt for Amazon Linux Worker Nodes
              readOnly: true
          imagePullPolicy: "Always"
      volumes:
        - name: ssl-certs
          hostPath:
            path: "/etc/ssl/certs/ca-bundle.crt"
```
   Apply the deployment YAML to deploy the Cluster Autoscaler:

   ```bash
   kubectl apply -f cluster-autoscaler.yaml
   ```
### Important Notes

#### Update IAM Role ARN

To set up the Cluster Autoscaler on Amazon EKS, you need to create a ServiceAccount with the correct IAM role ARN. Here's a note detailing the steps and an example configuration:

### Important Note for Setting Up Cluster Autoscaler on Amazon EKS

#### Update IAM Role ARN in ServiceAccount

Make sure to update the IAM role ARN in the annotations of your ServiceAccount configuration. This role provides the necessary permissions for the Cluster Autoscaler to interact with AWS resources.

```yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  labels:
    k8s-addon: cluster-autoscaler.addons.k8s.io
    k8s-app: cluster-autoscaler
  annotations:
    eks.amazonaws.com/role-arn: arn:aws:iam::338240650890:role/ca-role
  name: cluster-autoscaler
  namespace: kube-system
```

Replace `arn:aws:iam::338240650890:role/ca-role` with the IAM role ARN you created for the Cluster Autoscaler.

You need to update the IAM role ARN in your deployment configuration to match the IAM role created for the Cluster Autoscaler.

Add the following annotation in your deployment configuration:

```yaml
annotations:
  eks.amazonaws.com/role-arn: arn:aws:iam::338240650890:role/ca-role
```

Replace `arn:aws:iam::338240650890:role/ca-role` with your specific IAM role ARN.

#### Update the Cluster Autoscaler Image

Ensure you are using the latest or appropriate version of the Cluster Autoscaler image for your Kubernetes version. Update the image in your deployment configuration:

```yaml
- image: registry.k8s.io/autoscaling/cluster-autoscaler:v1.28.2
```

Replace `v1.28.2` with the latest version or the version compatible with your Kubernetes cluster.

#### Update Node Group Auto-Discovery Tags

You need to update the tags used for node group auto-discovery to match the tags used in your AWS environment.

Update the command arguments in your deployment configuration:

```yaml
- --node-group-auto-discovery=asg:tag=k8s.io/cluster-autoscaler/enabled,k8s.io/cluster-autoscaler/dev-cluster
```

Ensure the tags `k8s.io/cluster-autoscaler/enabled` and `k8s.io/cluster-autoscaler/dev-cluster` match the tags applied to your Auto Scaling Groups (ASGs) in AWS.


   Adjust the `image` version (`v1.21.0` here) to match the version of Kubernetes and Cluster Autoscaler you are using.

## Step 7: Create an Nginx deployment to test the functionality of the Cluster Autoscaler

Create an Nginx deployment to test the functionality of the Cluster Autoscaler.
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-managed
spec:
  replicas: 1
  selector:
    matchLabels:
      app: nginx-managed
  template:
    metadata:
      labels:
        app: nginx-managed
    spec:
      containers:
      - name: nginx-managed
        image: nginx:1.14.2
        ports:
        - containerPort: 80

```

   Apply the deployment YAML to create Nginx pods:

   ```bash
   kubectl apply -f nginx-deployment.yaml
   ```

   This will create 5 replicas of the Nginx deployment.

## Step 8. Monitor Cluster Autoscaler behavior:

   Monitor the logs of the Cluster Autoscaler to observe how it scales the number of nodes in response to the increased workload from the Nginx deployment:

   ```bash
   kubectl logs -f -n kube-system deployment.apps/cluster-autoscaler
   ```

   Check the number of nodes and pods to ensure they are scaling appropriately:

   ```bash
   kubectl get nodes
   kubectl get pods
   ```
