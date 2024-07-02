### What is Metrics Server

The Metrics Server is a cluster-wide aggregator of resource usage data in Kubernetes. It collects resource metrics (such as CPU and memory usage) from the kubelet on each node and makes them available via the Kubernetes API. These metrics are used by various Kubernetes components to make scheduling and scaling decisions.

### Metrics Server Architecture

- **Metrics API**: The Metrics Server implements the Kubernetes Metrics API, which provides CPU and memory usage statistics for nodes and pods.
- **Data Collection**: The Metrics Server collects data from the Kubelet on each node. The Kubelet itself collects data from the cAdvisor component running on each node.
- **Aggregation**: The collected data is aggregated and made available via the Metrics API for use by Kubernetes components and external tools.
- **Deployment**: The Metrics Server runs as a Deployment in the Kubernetes cluster.

### Resource Metrics in Kubernetes

Resource metrics in Kubernetes include:
- **CPU Usage**: The amount of CPU resources used by pods and nodes.
- **Memory Usage**: The amount of memory used by pods and nodes.

These metrics are used for:
- **Horizontal Pod Autoscaling (HPA)**: Automatically scaling the number of pod replicas based on CPU or memory usage.
- **Cluster Autoscaling**: Adjusting the size of the cluster based on resource usage.
- **Monitoring and Alerting**: Providing visibility into resource usage for monitoring and alerting purposes.

### Lab Session - Installation and Configuration of Metrics Server

#### Step 1: Deploy Metrics Server

Create a YAML file named `metrics-server-deployment.yaml`:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: metrics-server
  namespace: kube-system
  labels:
    k8s-app: metrics-server
spec:
  replicas: 1
  selector:
    matchLabels:
      k8s-app: metrics-server
  template:
    metadata:
      labels:
        k8s-app: metrics-server
    spec:
      containers:
      - name: metrics-server
        image: k8s.gcr.io/metrics-server/metrics-server:v0.6.1
        args:
        - --cert-dir=/tmp
        - --secure-port=4443
        - --kubelet-preferred-address-types=InternalIP,Hostname,InternalDNS,ExternalDNS,ExternalIP
        - --kubelet-use-node-status-port
        - --metric-resolution=15s
        ports:
        - name: main-port
          containerPort: 4443
          protocol: TCP
        volumeMounts:
        - name: tmp-dir
          mountPath: /tmp
      volumes:
      - name: tmp-dir
        emptyDir: {}
```

Apply the Deployment:

```bash
kubectl apply -f metrics-server-deployment.yaml
```

#### Step 2: Create the Service

Create a YAML file named `metrics-server-service.yaml`:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: metrics-server
  namespace: kube-system
  labels:
    k8s-app: metrics-server
spec:
  selector:
    k8s-app: metrics-server
  ports:
    - port: 443
      targetPort: 4443
      protocol: TCP
      name: https
```

Apply the Service:

```bash
kubectl apply -f metrics-server-service.yaml
```

#### Step 3: Verify Metrics Server Deployment

Check the status of the Metrics Server:

```bash
kubectl get deployment metrics-server -n kube-system
kubectl get pods -n kube-system | grep metrics-server
kubectl get svc metrics-server -n kube-system
```

#### Step 4: Verify Metrics API

Use the following command to check if the Metrics API is available and returning data:

```bash
kubectl top nodes
kubectl top pods --all-namespaces
```

If Metrics Server is working correctly, you should see resource usage data for nodes and pods.

### Summary

1. **Metrics Server**: A Kubernetes component that aggregates resource usage data.
2. **Architecture**: Collects data from kubelets, aggregates it, and provides it via the Metrics API.
3. **Resource Metrics**: Includes CPU and memory usage for nodes and pods.
4. **Installation and Configuration**: Deploy the Metrics Server using a Deployment and Service, then verify its operation.

### Introduction to Horizontal Pod Autoscaling (HPA)

Horizontal Pod Autoscaling (HPA) automatically scales the number of pod replicas in a Kubernetes deployment, replica set, or stateful set based on observed CPU utilization, memory usage, or custom metrics. HPA helps ensure that applications have the right amount of resources available to handle the current load.

#### Key Concepts of HPA
- **Metrics**: HPA can scale pods based on metrics like CPU usage, memory usage, or custom metrics provided by the application.
- **Targets**: Defines the desired metric value for scaling (e.g., 50% CPU utilization).
- **Controller**: A controller periodically checks the metrics and adjusts the number of pod replicas to match the target utilization.

### Lab Session - Creating and Managing HPA Resources

#### Prerequisites

Ensure that the Metrics Server is installed and configured in your cluster.

#### Step 1: Create a Deployment

Create a deployment manifest file named `nginx-deployment.yaml`:

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
        resources:
          requests:
            cpu: 200m
          limits:
            cpu: 500m
```

Apply the deployment:

```bash
kubectl apply -f nginx-deployment.yaml
```

#### Step 2: Create a Horizontal Pod Autoscaler

Create an HPA manifest file named `hpa.yaml`:

```yaml
apiVersion: autoscaling/v1
kind: HorizontalPodAutoscaler
metadata:
  name: nginx-hpa
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: nginx-deployment
  minReplicas: 1
  maxReplicas: 10
  targetCPUUtilizationPercentage: 50
```

Apply the HPA:

```bash
kubectl apply -f hpa.yaml
```

#### Step 3: Verify the HPA

Check the status of the HPA:

```bash
kubectl get hpa
```

You should see output similar to the following, showing the current CPU utilization and the desired number of replicas:

```plaintext
NAME        REFERENCE                  TARGETS    MINPODS   MAXPODS   REPLICAS   AGE
nginx-hpa   Deployment/nginx-deployment   10%/50%    1         10        1          1m
```

#### Step 4: Generate Load to Test HPA

To test the HPA, generate load on the deployment. You can use a simple load generator, such as a busy loop in a container, or a load testing tool like `hey` or `ab`.

For example, you can run a busybox pod that continuously makes HTTP requests to the NGINX deployment:

```bash
kubectl run -i --tty load-generator --image=busybox /bin/sh

# Inside the busybox shell, run:
while true; do wget -q -O- http://nginx-deployment; done
```

#### Step 5: Monitor the HPA

Monitor the HPA to see if it scales the number of replicas based on the increased CPU load:

```bash
kubectl get hpa
kubectl get pods
```

You should see the number of replicas increase to handle the load.

#### Step 6: Clean Up

Once you are done testing, delete the HPA and the deployment:

```bash
kubectl delete -f hpa.yaml
kubectl delete -f nginx-deployment.yaml
```

### Summary

1. **Introduction to HPA**: Understanding the basics and key concepts.
2. **Creating a Deployment**: Define a deployment with resource requests and limits.
3. **Creating an HPA**: Define and apply an HPA to manage the deployment.
4. **Verify and Test HPA**: Generate load and monitor the HPA's scaling behavior.
5. **Clean Up**: Remove the HPA and deployment resources.

