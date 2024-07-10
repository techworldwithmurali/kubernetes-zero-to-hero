### Introduction to Kubernetes ConfigMaps

- **Kubernetes ConfigMaps** are Kubernetes objects used to store configuration data in key-value pairs, files, or as plain text.
- They allow you to separate configuration from your containerized applications, making it easier to manage and update configuration settings without rebuilding container images.

### Key Features

1. **Decoupling Configuration from Code**:
   - ConfigMaps allow you to separate configuration artifacts from image content, enabling configuration changes without rebuilding your application images.

2. **Multiple Usage Scenarios**:
   - ConfigMaps can be used to store configuration files, command-line arguments, environment variables, and other configuration artifacts.

3. **Flexibility**:
   - They support a wide range of data types, including plain text, JSON, and even binary data encoded in base64.

### Accessing ConfigMap Data

There are several ways to use ConfigMap data within your pods:

1. **Environment Variables**:
   - You can expose ConfigMap values as environment variables in a pod.

2. **Volume Mounts**:
   - You can mount ConfigMap data as files within a pod.

3. **Command-line Arguments**:
   - You can pass ConfigMap values as command-line arguments to your container.

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
  name: my-config
  namespace: dev
data:
  DATABASE_URL: "mydatabase.nsvvbnnsnggsnbbn.us-west-2.rds.amazonaws.com"
  API_KEY: "jhgdjhhj5dsd2d325ad355da535da23543da35ad"

```
   - This creates a ConfigMap named my-config with two key-value pairs:
- DATABASE_URL: "mydatabase.nsvvbnnsnggsnbbn.us-west-2.rds.amazonaws.com"
- API_KEY: "jhgdjhhj5dsd2d325ad355da535da23543da35ad"

2. **Apply the ConfigMap:**
   ```bash
   kubectl apply -f my-configmap.yaml
   ```

3. **Verify ConfigMap Creation:**
   ```bash
   kubectl get configmaps
   kubectl describe configmap my-config
   ```

4. **Access ConfigMap Data from Pod:**
   - Mount ConfigMap data as environment variables or volumes in a Pod.
   - Example of using ConfigMap data in a Deployment  spec:
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
  namespace: dev
spec:
  replicas: 3
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-app-container
        image: nginx:latest
        envFrom:
          - configMapRef:
              name: my-config

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
