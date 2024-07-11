### What are Probes in Kubernetes

In Kubernetes, probes are mechanisms used to determine the readiness and liveness of containers running within a pod. They are crucial for ensuring the availability and health of applications.

There are three types of Probes in Kubernetes:

1. **Readiness Probe**:
   - **Purpose**: To determine if a container is ready to start accepting traffic. If the readiness probe fails, the endpoints controller removes the pod's IP address from the endpoints of all services that match the pod.
   - **Example**:
     ```yaml
     readinessProbe:
       httpGet:
         path: /index.html
         port: 80
       initialDelaySeconds: 5
       periodSeconds: 10
     ```

2. **Liveness Probe**:
   - **Purpose**: To determine if a container is still running. If the liveness probe fails, the kubelet kills the container, and the container is subjected to its restart policy.
   - **Example**:
     ```yaml
     livenessProbe:
       httpGet:
         path: /index.html
         port: 80
       initialDelaySeconds: 5
       periodSeconds: 10
     ```

3. **Startup Probe**:
   - **Purpose**: To determine if the application within the container has started. If the startup probe fails, the kubelet kills the container and follows the pod's restart policy. It is useful for slow-starting applications.
   - **Example**:
     ```yaml
     startupProbe:
       httpGet:
         path: /index.html
         port: 80
       initialDelaySeconds: 5
       periodSeconds: 10
       failureThreshold: 30
     ```

### Lab Session - Configuring Readiness Probes

#### Step 1: Create a Deployment with Readiness Probe

Create a deployment manifest file named `nginx-deployment.yaml` with a Readiness Probe configured:

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
        readinessProbe:
          httpGet:
            path: /index.html
            port: 80
          initialDelaySeconds: 5
          periodSeconds: 10
```

Apply the deployment:

```bash
kubectl apply -f nginx-deployment.yaml
```

#### Step 2: Verify Readiness Probe

Check the readiness status of the pod:

```bash
kubectl get pods -n dev
kubectl describe pod <pod-name> -n dev

```

### Lab Session - Configuring Liveness Probes

#### Step 1: Update Deployment with Liveness Probe

Update the `nginx-deployment.yaml` file to include a Liveness Probe:

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
        livenessProbe:
          httpGet:
            path: /index.html
            port: 80
          initialDelaySeconds: 5
          periodSeconds: 10
```

Apply the updated deployment:

```bash
kubectl apply -f nginx-deployment.yaml --force
```

#### Step 2: Verify Liveness Probe

Check the liveness status of the pod:

```bash
kubectl get pods -n dev
kubectl describe pod <pod-name> -n dev
```

### Lab Session - Configuring Startup Probes

#### Step 1: Add Startup Probe to Deployment

Update the `nginx-deployment.yaml` file to include a Startup Probe:

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
        readinessProbe:
          httpGet:
            path: /index.html
            port: 80
          initialDelaySeconds: 5
          periodSeconds: 10
        startupProbe:
          httpGet:
            path: /index.html
            port: 80
          timeoutSeconds: 300

```

Apply the updated deployment:

```bash
kubectl apply -f nginx-deployment.yaml --force
```

#### Step 2: Verify Startup Probe

Check the startup status of the pod:

```bash
kubectl get pods -n dev
kubectl describe pod <pod-name> -n dev

```
