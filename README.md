# Kubernetes Lab Sessions

## Lab Session 1: Creating a Pod Using Imperative Commands in Kubernetes

### Objectives:
- Understand how to create a Pod using imperative commands.
- Learn basic kubectl commands.

### Steps:

1. **Set Up Your Environment:**
   - Ensure you have a Kubernetes cluster running (Minikube, Kind, or any managed Kubernetes service).
   - Install `kubectl` CLI tool.

2. **Create a Pod Imperatively:**
   ```bash
   kubectl run my-pod --image=nginx --restart=Never
   ```

3. **Verify Pod Creation:**
   ```bash
   kubectl get pods
   kubectl describe pod my-pod
   ```

4. **Access Pod Logs:**
   ```bash
   kubectl logs my-pod
   ```

5. **Delete the Pod:**
   ```bash
   kubectl delete pod my-pod
   ```

---

## Lab Session 2: Creating Pods with YAML using Declarative Syntax

### Objectives:
- Understand how to create Pods using YAML files.
- Learn the structure of Kubernetes manifest files.

### Steps:

1. **Set Up Your Environment:**
   - Ensure you have a Kubernetes cluster running and `kubectl` installed.

2. **Create a YAML File:**
   - Create a file named `my-pod.yaml` with the following content:
     ```yaml
     apiVersion: v1
     kind: Pod
     metadata:
       name: my-pod
     spec:
       containers:
       - name: nginx
         image: nginx
     ```

3. **Create the Pod:**
   ```bash
   kubectl apply -f my-pod.yaml
   ```

4. **Verify Pod Creation:**
   ```bash
   kubectl get pods
   kubectl describe pod my-pod
   ```

5. **Delete the Pod:**
   ```bash
   kubectl delete -f my-pod.yaml
   ```

---

## Lab Session 3: Developing Kubernetes Manifest Files using Editor

### Objectives:
- Learn to develop Kubernetes manifest files using an editor.
- Understand the benefits of using an IDE or text editor for Kubernetes YAML files.

### Steps:

1. **Choose an Editor:**
   - Install a code editor like VS Code, Atom, or Sublime Text.
   - Install Kubernetes-related extensions/plugins for syntax highlighting and autocompletion.

2. **Create a Deployment Manifest:**
   - Create a file named `nginx-deployment.yaml` with the following content:
     ```yaml
     apiVersion: apps/v1
     kind: Deployment
     metadata:
       name: nginx-deployment
     spec:
       replicas: 3
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
             image: nginx:1.14.2
             ports:
             - containerPort: 80
     ```

3. **Apply the Deployment:**
   ```bash
   kubectl apply -f nginx-deployment.yaml
   ```

4. **Verify Deployment:**
   ```bash
   kubectl get deployments
   kubectl describe deployment nginx-deployment
   ```

---

## Lab Session 4: Deployments

### Objectives:
- Understand the concept of deployments in Kubernetes.
- Learn how to create and manage deployments.

Here is an example of a Kubernetes Deployment using a declarative YAML format:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
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
        image: nginx:1.14.2
        ports:
        - containerPort: 80
```

### Explanation:

- **apiVersion**: Specifies the API version for the deployment. For Deployments, it's usually `apps/v1`.
- **kind**: Specifies the type of resource. In this case, it's a `Deployment`.
- **metadata**: Provides metadata about the deployment, including the `name` and `labels`.
- **spec**: The specification of the deployment.
  - **replicas**: Defines the number of pod replicas to run.
  - **selector**: Defines how the deployment finds which Pods to manage based on labels.
    - **matchLabels**: Specifies the label selector to match the Pods.
  - **template**: Describes the Pods that will be created by the deployment.
    - **metadata**: Specifies the labels for the Pods.
    - **spec**: Defines the container specifications for the Pods.
      - **containers**: Specifies the list of containers in the Pod.
        - **name**: The name of the container.
        - **image**: The container image to run.
        - **ports**: The ports that the container will expose.

### Applying the Deployment:

1. Save the above YAML content to a file named `nginx-deployment.yaml`.
2. Apply the deployment using `kubectl`:

   ```bash
   kubectl apply -f nginx-deployment.yaml
   ```

### Verifying the Deployment:

- Check the status of the deployment:

  ```bash
  kubectl get deployments
  ```

- Describe the deployment to see detailed information:

  ```bash
  kubectl describe deployment nginx-deployment
  ```

- List the Pods created by the deployment:

  ```bash
  kubectl get pods
  ```

### Updating the Deployment:

To update the deployment, you can modify the `nginx-deployment.yaml` file. For example, change the image version:

```yaml
image: nginx:1.16.0
```

Then, apply the changes:

```bash
kubectl apply -f nginx-deployment.yaml
```
To delete a Kubernetes deployment, you can use the `kubectl delete` command. Here is how you can delete the `nginx-deployment` we created earlier.

1. **Delete the Deployment using `kubectl`**:

   ```bash
   kubectl delete -f nginx-deployment.yaml
   ```

   This command will delete the deployment defined in the `nginx-deployment.yaml` file.

2. **Alternatively, Delete the Deployment by Name**:

   ```bash
   kubectl delete deployment nginx-deployment
   ```

   This command will delete the deployment with the name `nginx-deployment`.

3. **Verify the Deletion**:

   ```bash
   kubectl get deployments
   ```

## Lab Session 5: Updating and Rolling Back Deployments

### Objectives:
- Learn how to update and roll back deployments in Kubernetes.
- Understand deployment history and rollback features.

### Steps:

1. **Update the Deployment:**
   - Update the `nginx-deployment.yaml` file with a new image version:
     ```yaml
     image: nginx:1.17.0
     ```
   - Apply the update:
     ```bash
     kubectl apply -f nginx-deployment.yaml
     ```

2. **Check Deployment History:**
   ```bash
   kubectl rollout history deployment/nginx-deployment
   ```

3. **Rollback to a Previous Revision:**
   ```bash
   kubectl rollout undo deployment/nginx-deployment
   ```

4. **Verify Rollback:**
   ```bash
   kubectl rollout status deployment/nginx-deployment
   kubectl get pods
   ```
