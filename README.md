# Setting up AWS EKS

**Author**: Moole Muralidhara Reddy  
**Email**: telugudevopsguru@gmail.com  
**Website**: [https://www.techworldwithmurali.com/](https://www.techworldwithmurali.com/)  
**Description**: Setting up AWS EKS  

## Step-by-Step Guide

### Step 1: Create the IAM user and provide Admin Access
```xml
Username: moole
```

### Step 1.1: Login to the AWS Console using moole user
```xml
UserName: moole
```

### Step 2: Create the VPC and 2 public subnets
```xml
Note: We are going to use the default VPC so we don't need to create the VPC.
```

### Step 3: Create the KeyPair
```xml
KeyPair Name: dev
```

### Step 4: Create the AWS EKS Cluster Role
```xml
Name: dev-cluster-role
```

### Step 5: Create the AWS EKS Cluster
```xml
Cluster Name: dev-cluster
```

### Step 6: Create the AWS EKS worker node Role
```xml
Name: dev-cluster-worker-node-role
```
Attach the below policies for the worker node Role:
```xml
AmazonEKSWorkerNodePolicy
AmazonEC2ContainerRegistryReadOnly
AmazonEKS_CNI_Policy
```

### Step 7: Create the Node Group
```xml
Worker group name: dev-cluster-worker-node
```

### Step 8: Configure the AWS CLI using Access Key ID & Secret Access Key
```bash
aws configure --profile dev
```

### Step 9: Connect to the EKS cluster using the command below
```bash
aws eks update-kubeconfig --name dev-cluster --region us-east-1 --profile dev
```

#### Congratulations: You have successfully created the AWS EKS Cluster.
```
