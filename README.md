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

### What is Storage Classes

Storage Classes in Kubernetes provide a way to describe the "classes" of storage that are offered by a cluster. Different classes might map to quality-of-service levels, backup policies, or arbitrary policies determined by the cluster administrators. Storage Classes allow for dynamic provisioning of Persistent Volumes (PVs) so that you don't need to manually create PVs beforehand.

Key concepts related to Storage Classes:
- **Provisioner**: Determines the type of backend storage provisioner (e.g., AWS EBS, GCE PD, etc.).
- **Parameters**: Specific parameters required by the provisioner to create volumes.
- **Reclaim Policy**: Determines what happens to the persistent volume when it is released from its claim.
- **Volume Binding Mode**: Controls when volume binding and dynamic provisioning should occur (Immediate or WaitForFirstConsumer).

### Lab Session - Storage Classes

### Step 1: Create a Storage Class
First, create a Storage Class manifest file named storage-class.yaml.

```yaml
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: standard
provisioner: kubernetes.io/aws-ebs
parameters:
  type: gp2
  fsType: ext4
reclaimPolicy: Retain
volumeBindingMode: Immediate
```

Apply the Storage Class:
```bash
kubectl apply -f storage-class.yaml
```

#### Step 2: Define the Persistent Volume Claim (PVC)

Create a PVC manifest file named `pvc-with-sc.yaml`:

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: my-pvc
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 5Gi
  storageClassName: standard
```

Apply the PVC:
```bash
kubectl apply -f pvc-with-sc.yaml
```

#### Step 3: Define the Deployment

Create a Deployment manifest file named `deployment-with-pvc.yaml`:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 2
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
          name: storage
      volumes:
      - name: storage
        persistentVolumeClaim:
          claimName: my-pvc
```

#### Step 4: Apply the Deployment

Apply the Deployment:
```bash
kubectl apply -f deployment-with-pvc.yaml
```

#### Step 5: Verify the Deployment and PVC

Check the status of the Deployment and PVC:
```bash
kubectl get deployments
kubectl get pods
kubectl get pvc
```

#### Step 6: Verify the Volume is Mounted

Verify that the volume is correctly mounted inside one of the Pods:
```bash
kubectl get pods
kubectl exec -it <pod-name> -- /bin/bash
ls /usr/share/nginx/html
```

### Summary
- **Storage Class**: Defines the characteristics and provisioner for storage.
- **PVC**: Requests storage dynamically provisioned by the Storage Class.
- **Deployment**: Uses the PVC to mount the dynamically provisioned storage in the Pods.
