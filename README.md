### Overview of Volumes
Volumes in Kubernetes are a way to manage data in pods that can outlive the lifecycle of individual containers. They provide a way for containers to share data and store data persistently across pod restarts.

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
  name: my-pv
spec:
  capacity:
    storage: 10Gi
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  hostPath:
    path: /mnt/data
```

#### Step 2: Creating a Persistent Volume Claim (PVC)
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
      storage: 10Gi
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

