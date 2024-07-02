### What is Cluster Autoscaler

Cluster Autoscaler automatically adjusts the size of a Kubernetes cluster by adding or removing nodes based on the current workload. It works in conjunction with the Horizontal Pod Autoscaler (HPA) to ensure that the cluster has enough resources to run all scheduled pods and scales down the cluster when there are idle nodes. The Cluster Autoscaler is particularly useful in cloud environments where you pay for the resources you use, as it helps optimize costs by only running the necessary number of nodes.

### Prerequisites

- AWS CLI configured with appropriate permissions.
- Kubernetes cluster running on AWS EKS.

# Setting up Kubernetes Cluster Autoscaler on AWS EKS

Follow these steps to set up and test the Kubernetes Cluster Autoscaler on an AWS EKS cluster.

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

Create an Nginx deployment and Horizontal Pod Autoscaler (HPA) to observe autoscaling behavior.
