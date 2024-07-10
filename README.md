### Introduction to Kubernetes ConfigMaps

- **Kubernetes ConfigMaps** are Kubernetes objects used to store configuration data in key-value pairs, files, or as plain text.
- They allow you to separate configuration from your containerized applications, making it easier to manage and update configuration settings without rebuilding container images.

### Lab Session: Kubernetes ConfigMaps

#### Objectives:
- Learn how to create and use Kubernetes ConfigMaps.

#### Steps:

1. **Create a ConfigMap YAML:**
   - Create a file named `my-configmap.yaml` with the following content:
     ```yaml
     apiVersion: v1
     kind: ConfigMap
     metadata:
       name: my-configmap
     data:
       key1: value1
       key2: value2
     ```
   - This creates a ConfigMap named `my-configmap` with two key-value pairs (`key1: value1` and `key2: value2`).

2. **Apply the ConfigMap:**
   ```bash
   kubectl apply -f my-configmap.yaml
   ```

3. **Verify ConfigMap Creation:**
   ```bash
   kubectl get configmaps
   kubectl describe configmap my-configmap
   ```

4. **Access ConfigMap Data from Pod:**
   - Mount ConfigMap data as environment variables or volumes in a Pod.
   - Example of using ConfigMap data in a Pod spec:
     ```yaml
     apiVersion: v1
     kind: Pod
     metadata:
       name: my-pod
     spec:
       containers:
       - name: my-container
         image: nginx
         env:
         - name: KEY1
           valueFrom:
             configMapKeyRef:
               name: my-configmap
               key: key1
     ```

5. **Access ConfigMap Data from CLI:**
   - Retrieve specific data from ConfigMap:
     ```bash
     kubectl get configmap my-configmap -o jsonpath='{.data.key1}'
     ```

### Introduction to Kubernetes Secrets

**Kubernetes Secrets** are Kubernetes objects used to store sensitive information, such as passwords, OAuth tokens, and SSH keys, in a secure manner. They are encoded in Base64 by default but can be encrypted for further security.

### Lab Session: Kubernetes Secrets

#### Objectives:
- Learn how to create and use Kubernetes Secrets.

#### Steps:

1. **Create a Secret YAML:**
   - Create a file named `my-secret.yaml` with the following content:
     ```yaml
     apiVersion: v1
     kind: Secret
     metadata:
       name: my-secret
     type: Opaque
     data:
       username: YWRtaW4=   # Base64 encoded 'admin'
       password: MWYyZDFlMmU2N2Rm
     ```
   - This creates a Secret named `my-secret` with two key-value pairs (`username` and `password`).

2. **Apply the Secret:**
   ```bash
   kubectl apply -f my-secret.yaml
   ```

3. **Verify Secret Creation:**
   ```bash
   kubectl get secrets
   kubectl describe secret my-secret
   ```

4. **Access Secret Data from Pod:**
   - Mount Secret data as environment variables or volumes in a Pod.
   - Example of using Secret data in a Pod spec:
     ```yaml
     apiVersion: v1
     kind: Pod
     metadata:
       name: my-pod
     spec:
       containers:
       - name: my-container
         image: nginx
         env:
         - name: DB_USERNAME
           valueFrom:
             secretKeyRef:
               name: my-secret
               key: username
         - name: DB_PASSWORD
           valueFrom:
             secretKeyRef:
               name: my-secret
               key: password
     ```

5. **Access Secret Data from CLI:**
   - Retrieve specific data from Secret:
     ```bash
     kubectl get secret my-secret -o jsonpath='{.data.username}' | base64 --decode
     ```
