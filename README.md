### What are Probes in Kubernetes

In Kubernetes, probes are mechanisms used to determine the readiness and liveness of containers running within a pod. They are crucial for ensuring the availability and health of applications.

### Types of Probes

1. **Readiness Probe**: Determines when a container is ready to accept traffic. If the Readiness Probe fails, Kubernetes removes the pod from the endpoints of all Services that match the pod, which means the pod's IP address is removed from the load balancer pool, and no new connections are sent to the pod until it passes the probe.

2. **Liveness Probe**: Checks if a container is running as expected. If the Liveness Probe fails, Kubernetes restarts the container to restore it to a healthy state.

3. **Startup Probe**: Determines when a container application has started. It complements the Readiness Probe by detecting the initial startup phase of the container.

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
