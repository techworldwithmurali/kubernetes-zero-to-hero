### What is Kubernetes Volumes
- Volumes in Kubernetes are a way to manage data in pods that can outlive the lifecycle of individual containers.
- They provide a way for containers to share data and store data persistently across pod restarts.

### Types of Volumes
1. **emptyDir**: Created when a pod is assigned to a node and exists as long as the pod is running on that node.
2. **hostPath**: Maps to a file or directory on the host node’s filesystem.
3. **nfs**: Mounts an NFS share to be used by the pods.
4. **persistentVolumeClaim (PVC)**: Requests for storage by a pod that must match a persistentVolume (PV) resource.
5. **configMap**: Provides a way to inject configuration data into pods.
6. **secret**: Provides a way to manage sensitive information, such as passwords or API keys.
7. **awsElasticBlockStore (EBS)**: Mounts an Amazon Web Services EBS volume into a pod.
8. **gcePersistentDisk**: Mounts a Google Compute Engine persistent disk into a pod.
9. **azureDisk**: Mounts an Azure Data Disk into a pod.
10. **csi (Container Storage Interface)**: Allows for the use of different storage solutions via CSI plugins.

### What is Persistent Volumes and Claims
- **Persistent Volumes (PVs)**: A storage resource in a Kubernetes cluster that has been provisioned by an administrator or dynamically provisioned using Storage Classes. PVs are independent of the lifecycle of a pod.
- **Persistent Volume Claims (PVCs)**: A request for storage by a user that specifies the size and access mode (e.g., ReadWriteOnce, ReadOnlyMany, ReadWriteMany). PVCs are bound to PVs that match the requested size and access mode.

### Lab Session - Provisioning and Managing PVs and PVCs

#### Step 1: Creating a Persistent Volume (PV)
```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: test-pv
  namespace: dev
spec:
  accessModes:
  - ReadWriteOnce
  capacity:
    storage: 5Gi
  csi:
    driver: ebs.csi.aws.com
    fsType: ext4
    volumeHandle: vol-039d16206ce355d91
```

#### Step 2: Creating a Persistent Volume Claim (PVC)
```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: ebs-claim
  namespace: dev
spec:
  storageClassName: "" # Empty string must be explicitly set otherwise default StorageClass will be set
  volumeName: test-pv
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 5Gi
```

#### Step 3: Creating a Deployment with PVC
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
        volumeMounts:
        - mountPath: "/usr/share/nginx/html"
          name: html
      volumes:
      - name: html
        persistentVolumeClaim:
          claimName: my-pvc
```

### Lab Steps
1. **Apply the Persistent Volume**:
   ```bash
   kubectl apply -f pv.yaml
   ```

2. **Apply the Persistent Volume Claim**:
   ```bash
   kubectl apply -f pvc.yaml
   ```

3. **Verify PV and PVC**:
   ```bash
   kubectl get pv
   kubectl get pvc
   ```

4. **Apply the Deployment**:
   ```bash
   kubectl apply -f deployment.yaml
   ```

5. **Verify the Deployment**:
   ```bash
   kubectl get deployments
   kubectl get pods
   ```

6. **Verify the Volume is Mounted**:
   ```bash
   kubectl exec -it <pod-name> -- /bin/bash
   ls /usr/share/nginx/html
   ```
------

### What is Storage Classes
- Storage Classes in Kubernetes are indeed a key feature for managing and automating storage in a cluster.
- They enable dynamic provisioning of Persistent Volumes (PVs), which means that when a Persistent Volume Claim (PVC) is created, the necessary PV can be automatically provisioned based on the specifications defined in the StorageClass.

### Key Concepts of Storage Classes

1. **Dynamic Provisioning**: With Storage Classes, you can automatically create Persistent Volumes (PVs) based on the specifications in a PVC. This eliminates the need for cluster administrators to manually create PVs.

2. **Parameters**: Specific parameters required by the provisioner to create volumes.

3. **Reclaim Policy**:  Determines what happens to the persistent volume when it is released from its claim.

4. **Provisioner**: Each Storage Class defines a provisioner, which is responsible for dynamically creating PVs. Examples of provisioners include:
   - `kubernetes.io/aws-ebs` for Amazon EBS volumes
   - `kubernetes.io/gce-pd` for Google Cloud Persistent Disks
   - `kubernetes.io/azure-disk` for Azure Disks

5. **Volume Binding Mode**: Controls when volume binding and dynamic provisioning should occur (Immediate or WaitForFirstConsumer).


### Benefits of Using Storage Classes

1. **Automation**: Automatically provision storage without manual intervention, reducing administrative overhead.
2. **Flexibility**: Define multiple storage classes for different use cases, such as high-performance or high-durability storage.
3. **Scalability**: Easily scale storage resources as needed, without manual provisioning of PVs.
4. **Consistency**: Ensure that storage policies are consistently applied across the cluster.

### Lab Session - Storage Classes

Here's the detailed lab session for dynamic provisioning of Persistent Volumes (PV) and Persistent Volume Claims (PVC) using the Amazon EBS CSI driver in an EKS cluster:

## Lab Session: Dynamic Provisioning PV and PVC

### Step 1: Create the OIDC Provider for EKS Cluster
1. Create the OIDC provider to allow the EKS cluster to communicate with AWS IAM.
2. Ensure you have the necessary permissions to create the OIDC provider.

```sh
eksctl utils associate-iam-oidc-provider --region <region> --cluster dev-cluster --approve
```

### Step 2: Create an IAM Role and Attach the AmazonEBSCSIDriverPolicy Policy
1. **Create the IAM Role for the Amazon EBS CSI driver**:
   - Navigate to the IAM console.
   - Create a new role with the following details:
     - **Trusted entity**: Web identity
     - **OIDC provider**: The one you created for your cluster.
     - **Audience**: `sts.amazonaws.com`

2. **Attach the AmazonEBSCSIDriverPolicy policy**:
   - Policy ARN: `arn:aws:iam::aws:policy/service-role/AmazonEBSCSIDriverPolicy`

3. **Update the trust relationship**:
   - Add the following to the trust relationship JSON:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Federated": "arn:aws:iam::<account_id>:oidc-provider/oidc.eks.<region>.amazonaws.com/id/<eks_oidc_id>"
      },
      "Action": "sts:AssumeRoleWithWebIdentity",
      "Condition": {
        "StringEquals": {
          "oidc.eks.<region>.amazonaws.com/id/<eks_oidc_id>:sub": "system:serviceaccount:kube-system:ebs-csi-controller-sa"
        }
      }
    }
  ]
}
```

### Step 3: Deploy the Amazon EBS CSI Driver
1. Use the AWS CLI to deploy the Amazon EBS CSI driver:

```sh
aws eks create-addon \
 --cluster-name dev-cluster  \
 --addon-name aws-ebs-csi-driver \
 --service-account-role-arn arn:aws:iam::<account_id>:role/AmazonEKS_EBS_CSI_DriverRole
```

### Step 4: Verify the Installation
1. Check if the EBS CSI driver is installed successfully:

```sh
kubectl get all -A | grep csi
```

### Step 5: Test the Amazon EBS CSI Driver
You will test the EBS CSI driver using a sample application that dynamically provisions EBS volumes for pods.

1. **Clone the aws-ebs-csi-driver repository**:

```sh
git clone https://github.com/kubernetes-sigs/aws-ebs-csi-driver.git
```

2. **Change your working directory**:

```sh
cd aws-ebs-csi-driver/examples/kubernetes/dynamic-provisioning/
```

3. **Create the Kubernetes resources for testing**:

### `storage-class.yaml`
```yaml
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: standard
provisioner: kubernetes.io/aws-ebs
parameters:
  type: gp2
```

### `pvc.yaml`
```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: my-pvc
  namespace: dev
spec:
  accessModes:
    - ReadWriteOnce
  storageClassName: standard
  resources:
    requests:
      storage: 1Gi
```

### `deployment.yaml`
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-deployment
  namespace: dev
spec:
  replicas: 1
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-container
        image: nginx:latest
        volumeMounts:
        - mountPath: /data
          name: my-volume
      volumes:
      - name: my-volume
        persistentVolumeClaim:
          claimName: my-pvc
```

### Applying the YAML Files
1. **Create the StorageClass**:
   ```sh
   kubectl apply -f storage-class.yaml
   ```

2. **Create the PersistentVolumeClaim**:
   ```sh
   kubectl apply -f pvc.yaml
   ```

3. **Create the Deployment**:
   ```sh
   kubectl apply -f deployment.yaml
   ```

### Verify the Resources
1. **Check the PersistentVolumeClaim**:
   ```sh
   kubectl get pvc -n dev
   ```

2. **Check the PersistentVolume**:
   ```sh
   kubectl get pv
   ```

3. **Check the Deployment and Pod**:
   ```sh
   kubectl get deployments -n dev
   kubectl get pods -n dev
   ```

4. **Verify that the pod is writing data to the volume**:
   - Replace `pod_name` with the actual name of your pod.
   ```sh
   kubectl exec -it pod_name -n dev -- cat /data/out.txt
   ```

### Conclusion
You have successfully deployed and tested dynamic provisioning of PV and PVC using the Amazon EBS CSI driver in your EKS cluster.


### Summary
- **Storage Class**: Defines the characteristics and provisioner for storage.
- **PVC**: Requests storage dynamically provisioned by the Storage Class.
- **Deployment**: Uses the PVC to mount the dynamically provisioned storage in the Pods.
