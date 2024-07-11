## What is Cluster Autoscaler

- Cluster Autoscaler automatically adjusts the size of a Kubernetes cluster by adding or removing nodes based on the current workload.
- It works in conjunction with the Horizontal Pod Autoscaler (HPA) to ensure that the cluster has enough resources to run all scheduled pods and scales down the cluster when there are idle nodes.
- The Cluster Autoscaler is particularly useful in cloud environments where you pay for the resources you use, as it helps optimize costs by only running the necessary number of nodes.

### Key Features and Functionality of Cluster Autoscaler:

1. **Dynamic Scaling**: Cluster Autoscaler dynamically adjusts the number of nodes in a cluster based on the current workload. When pods cannot be scheduled due to resource constraints (such as insufficient CPU or memory), Cluster Autoscaler will provision additional nodes to accommodate the demand.

2. **Integration with Cloud Providers**: It integrates with cloud provider APIs to manage the lifecycle of virtual machines (VMs) or instances that form the Kubernetes nodes. This allows it to seamlessly add or remove nodes in response to workload changes.

3. **Configuration**: Cluster Autoscaler can be configured with various parameters such as minimum and maximum node counts, node group settings, and scaling behavior thresholds. This flexibility allows operators to tailor autoscaling behavior to match specific workload patterns and cluster requirements.

4. **Scale Down Considerations**: Cluster Autoscaler also includes safeguards to prevent premature scale-down events, ensuring that nodes are only removed when their pods can be safely evicted or rescheduled elsewhere.

### Deployment and Configuration:

Deploying Cluster Autoscaler typically involves setting up proper IAM roles or permissions for cloud provider APIs and configuring the autoscaler with appropriate parameters like:

- `--max-nodes`: Maximum number of nodes that can be added to the cluster.
- `--min-nodes`: Minimum number of nodes that should be maintained in the cluster.
- `--scale-down-delay`: Delay before a node is considered for termination after it becomes underutilized.
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

## Step 7: Create an Nginx deployment to test the functionality of the Cluster Autoscaler

Create an Nginx deployment to test the functionality of the Cluster Autoscaler.
