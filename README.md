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

- **Kubernetes Secrets** are Kubernetes objects used to store sensitive information, such as passwords, OAuth tokens, and SSH keys, in a secure manner.
- They are encoded in Base64 by default but can be encrypted for further security.

### Key Features

1. **Encryption**:
   - Secrets are encoded in Base64 but can be encrypted at rest when stored in etcd (the key-value store used by Kubernetes) to enhance security.

2. **Access Control**:
   - Secrets can be tightly controlled with Kubernetes RBAC (Role-Based Access Control), ensuring that only authorized users and pods can access them.

3. **Separation from Code**:
   - Secrets allow sensitive information to be managed separately from application code, providing better security and flexibility.


> **Note**: The values in the `data` field are Base64-encoded. You can encode a string to Base64 using the `echo -n 'your-string' | base64` command.

Some common use cases for Secrets in Kubernetes include:

- Storing database credentials
- Holding API keys or tokens
- Encrypting sensitive data
- Storing SSL/TLS certificates
- Managing service account credentials

# Kubernetes Secret Types

In Kubernetes, the type field of the Secret resource specifies the format and intended use of the Secret's data. This field influences how Kubernetes manages and validates the Secret's contents. 

## Built-in Secret Types

Kubernetes offers various built-in types tailored for different usage scenarios. Each type comes with its own set of validations and configurations to ensure secure handling of sensitive information.

| Built-in Type                        | Usage                                      |
|--------------------------------------|--------------------------------------------|
| Opaque                               | arbitrary user-defined data                |
| kubernetes.io/service-account-token | ServiceAccount token                       |
| kubernetes.io/dockercfg              | serialized ~/.dockercfg file               |
| kubernetes.io/dockerconfigjson       | serialized ~/.docker/config.json file      |
| kubernetes.io/basic-auth             | credentials for basic authentication      |
| kubernetes.io/ssh-auth               | credentials for SSH authentication        |
| kubernetes.io/tls                    | data for a TLS client or server            |
| bootstrap.kubernetes.io/token        | bootstrap token data                       |

### Opaque

The `Opaque` type is used for arbitrary user-defined data. It allows you to store any kind of sensitive information as key-value pairs.

### kubernetes.io/service-account-token

This type is specifically designed to store ServiceAccount tokens securely. ServiceAccount tokens are used by pods to authenticate to the Kubernetes API.

### kubernetes.io/dockercfg

`dockercfg` stores a Docker registry's authentication credentials. It is serialized from the `~/.dockercfg` file format.

### kubernetes.io/dockerconfigjson

Similar to `dockercfg`, `dockerconfigjson` stores Docker registry credentials but in the `~/.docker/config.json` file format.

### kubernetes.io/basic-auth

Use this type to store credentials for basic authentication mechanisms. It's useful for integrating with systems that require basic username and password authentication.

### kubernetes.io/ssh-auth

SSH keys and related authentication data are stored using this type. It allows Kubernetes applications to securely access SSH-enabled systems.

### kubernetes.io/tls

For TLS certificates and related data used in secure communication between components. This type ensures that sensitive certificate data is managed securely within Kubernetes.

### bootstrap.kubernetes.io/token

This type is used for storing bootstrap tokens, which are used during the bootstrap process of a Kubernetes cluster. It's essential for securely managing initial access and authentication tokens.

### Accessing Secret Data

There are several ways to use Secret data within your pods:

1. **Environment Variables**:
   - You can expose Secret values as environment variables in a pod.

2. **Volume Mounts**:
   - You can mount Secret data as files within a pod.

3. **Command-line Arguments**:
   - You can pass Secret values as command-line arguments to your container.


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
  name: myapp-secret
  namespace: dev
type: Opaque
data:
  username: bXl1c2Vy      # base64-encoded "myuser"
  password: bXlwYXNzd29yZA==  # base64-encoded "mypassword"

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
   - Example of using Secret data in a Deployment spec:
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp-deployment
  namespace: dev
spec:
  replicas: 3
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: myapp-container
        image: nginx:latest
        env:
        - name: MY_APP_USERNAME
          valueFrom:
            secretKeyRef:
              name: myapp-secret
              key: username
        - name: MY_APP_PASSWORD
          valueFrom:
            secretKeyRef:
              name: myapp-secret
              key: password

```
