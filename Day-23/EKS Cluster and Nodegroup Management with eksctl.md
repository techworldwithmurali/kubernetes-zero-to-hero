# EKS Cluster Management with eksctl

### 1. **Create a Cluster**
```bash
eksctl create cluster \
  --name infra-cluster \
  --region us-east-1 \
  --version 1.30 \
  --vpc-private-subnets subnet-062fe29906f128e40,subnet-06424bdeed3ba25c6 \
  --without-nodegroup \
  --with-oidc \
  --profile infra
```
- **`create cluster`**: Initializes and provisions a new EKS cluster.
- **`--name infra-cluster`**: Assigns the cluster a name, `infra-cluster`.
- **`--region us-east-1`**: Specifies the AWS region where the cluster will be created.
- **`--version 1.30`**: Specifies the Kubernetes version for the cluster.
- **`--vpc-private-subnets`**: Designates specific private subnets in the VPC for the cluster. Replace `subnet-0ab8d3e404d04be99` and `subnet-0140c441a31b472a4` with your actual subnet IDs.
- **`--without-nodegroup`**: Creates the control plane without worker nodes. This allows you to configure the node group separately.
- **`--with-oidc`**: Enables the OpenID Connect (OIDC) provider, required for using IAM roles for service accounts.

---

### 2. **Create a Nodegroup**
```bash
eksctl create nodegroup \
  --cluster infra-cluster \
  --region us-east-1 \
  --name infra-cluster-nodes \
  --nodes 2 \
  --node-private-networking \
  --ssh-access \
  --ssh-public-key infra \
  --nodes-min 2 \
  --nodes-max 5 \
  --node-type t2.micro \
  --managed \
  --profile infra
```
- **`create nodegroup`**: Provisions a worker node group for the specified cluster.
- **`--cluster infra-cluster`**: Associates the node group with the `infra-cluster` EKS cluster.
- **`--name infra-cluster-nodes`**: Names the node group as `infra-cluster-nodes`.
- **`--nodes 2`**: Sets the initial number of nodes to 2.
- **`--node-private-networking`**: Ensures nodes are launched in private subnets, enhancing security.
- **`--ssh-access`**: Allows SSH access to the nodes.
- **`--ssh-public-key infra`**: Specifies the SSH key pair (`infra`) to access the nodes.
- **`--nodes-min 2`, `--nodes-max 5`**: Sets the auto-scaling range for the node group.
- **`--node-type t2.micro`**: Uses the `t2.micro` instance type for nodes.
- **`--managed`**: Creates a managed node group, where AWS manages upgrades and scaling.

---

### 3. **Scale a Nodegroup**
```bash
eksctl scale nodegroup \
  --cluster infra-cluster \
  --region us-east-1 \
  --name infra-cluster-nodes \
  --nodes 1 \
  --nodes-min 1 \
  --nodes-max 1 \
  --profile infra
```
- **`scale nodegroup`**: Adjusts the number of nodes in the specified node group.
- **`--nodes 1`**: Sets the desired number of nodes to 1.
- **`--nodes-min 1`, `--nodes-max 1`**: Updates the minimum and maximum scaling limits for the node group to 1.

---

### 4. **Upgrade the Cluster**
```bash
eksctl upgrade cluster \
  --name infra-cluster \
  --region us-east-1 \
  --version 1.31 \
  --profile infra
```
- **`upgrade cluster`**: Upgrades the Kubernetes control plane version.
- **`--version 1.31`**: Specifies the new Kubernetes version to upgrade to.

---

### 5. **Upgrade the Nodegroup**
```bash
eksctl upgrade nodegroup \
  --cluster infra-cluster \
  --region us-east-1 \
  --name infra-cluster-nodes \
  --kubernetes-version 1.31 \
  --profile infra
```
- **`upgrade nodegroup`**: Upgrades the Kubernetes version of the node group.
- **`--kubernetes-version 1.31`**: Specifies the target Kubernetes version for the nodes.

---

### 6. **Delete a Nodegroup**
```bash
eksctl delete nodegroup \
  --cluster infra-cluster \
  --region us-east-1 \
  --name infra-cluster-nodes \
  --profile infra
```
- **`delete nodegroup`**: Removes the specified node group from the cluster.
- **`--name infra-cluster-nodes`**: Specifies the node group to delete.

---

### 7. **Delete the Cluster**
```bash
eksctl delete cluster \
  --name infra-cluster \
  --region us-east-1 \
  --profile infra
```
- **`delete cluster`**: Deletes the entire EKS cluster, including associated resources such as control plane and OIDC provider.
- **`--name infra-cluster`**: Specifies the cluster to delete.
