# What is Metrics Server

- The Metrics Server is a cluster-wide aggregator of resource usage data in Kubernetes.
- It collects resource metrics (such as CPU and memory usage) from the kubelet on each node and makes them available via the Kubernetes API.
- These metrics are used by various Kubernetes components to make scheduling and scaling decisions.

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
To set up the Kubernetes Metrics Server, follow these steps:

### Step 1: Go to the Metrics Server Release Page

Navigate to the Metrics Server release page on GitHub:

[Metrics Server Releases](https://github.com/kubernetes-sigs/metrics-server/releases)

### Step 2: Choose the Version

Choose the desired version of the Metrics Server. For this example, we'll use version 0.7.1.

### Step 3: Apply the Components YAML

Run the following command to deploy the Metrics Server using `kubectl`:

```bash
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/download/v0.7.1/components.yaml
```

This command will download the components.yaml file for version 0.7.1 from the Metrics Server GitHub repository and apply it to your Kubernetes cluster.

### Step 4: Verify the Installation

To verify that the Metrics Server is running correctly, you can check the status of the `metrics-server` deployment in the `kube-system` namespace:

```bash
kubectl get deployment metrics-server -n kube-system
```

Ensure that the `metrics-server` pods are running and ready:

```bash
kubectl get pods -n kube-system | grep metrics-server
```

### Step 5: Use the Metrics Server

After the Metrics Server is installed and running, you can use it to gather resource metrics. For example, you can use the following command to get the resource usage of nodes:

```bash
kubectl top nodes
```

And to get the resource usage of pods:

```bash
kubectl top pods --all-namespaces
```

If Metrics Server is working correctly, you should see resource usage data for nodes and pods.

# What  is Autoscaling in Kubernetes
- Autoscaling in Kubernetes is the process of automatically adjusting the number of running pods in a deployment or the resources allocated to a pod based on the current demand.
- This ensures that applications can handle varying workloads efficiently without manual intervention, leading to optimal resource utilization and cost savings. Kubernetes supports several types of autoscaling:

### Types of Autoscaling in Kubernetes

1. **Horizontal Pod Autoscaling (HPA)**:
   - **Definition**: HPA automatically scales the number of pods in a deployment, replica set, or stateful set based on observed CPU utilization, memory usage, or other custom metrics.

   - **Example Use Case**: If the CPU utilization of pods exceeds a defined threshold, HPA will increase the number of pods to handle the load.
2. **Vertical Pod Autoscaling (VPA)**:
   - **Definition**: VPA automatically adjusts the CPU and memory requests and limits for containers in a pod based on historical usage.
   - **Example Use Case**: If a pod consistently uses more memory than initially requested, VPA will increase its memory allocation.

3. **Cluster Autoscaler**:
   - **Definition**: Cluster Autoscaler adjusts the size of the cluster by adding or removing nodes based on the pending pods and resource utilization.
   - **Example Use Case**: If the cluster runs out of resources to schedule new pods, the Cluster Autoscaler can add more nodes to the cluster.

### What is Horizontal Pod Autoscaling (HPA)

- Horizontal Pod Autoscaling (HPA) automatically scales the number of pod replicas in a Kubernetes deployment, replica set, or stateful set based on observed CPU utilization, memory usage, or custom metrics.
- HPA helps ensure that applications have the right amount of resources available to handle the current load.

#### Key Concepts of HPA
- **Metrics**: HPA can scale pods based on metrics like CPU usage, memory usage, or custom metrics provided by the application.
- **Targets**: Defines the desired metric value for scaling (e.g., 50% CPU utilization).
- **Controller**: A controller periodically checks the metrics and adjusts the number of pod replicas to match the target utilization.

### Lab Session - Creating and Managing HPA Resources

#### Prerequisites

Ensure that the Metrics Server is installed and configured in your cluster.

#### Step 1: Create a Deployment

Create a deployment manifest file named `deployment.yaml`:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: php-apache
spec:
  selector:
    matchLabels:
      run: php-apache
  template:
    metadata:
      labels:
        run: php-apache
    spec:
      containers:
      - name: php-apache
        image: registry.k8s.io/hpa-example
        ports:
        - containerPort: 80
        resources:
          limits:
            cpu: 500m
          requests:
            cpu: 200m
```

Apply the deployment:

```bash
kubectl apply -f nginx-deployment.yaml
```
#### Step 2: Create a Service

Create a deployment manifest file named `service.yaml`:
```yaml
apiVersion: v1
kind: Service
metadata:
  name: php-apache
  labels:
    run: php-apache
spec:
  ports:
  - port: 80
  selector:
    run: php-apache
```

Apply the service:

```bash
kubectl apply -f nginx-service.yaml
```
#### Step 3: Create a Horizontal Pod Autoscaler

Create an HPA manifest file named `hpa.yaml`:

```yaml
# https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale-walkthrough/
apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata:
  name: php-apache
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: php-apache
  minReplicas: 1
  maxReplicas: 10
  metrics:
  - type: Resource
    resource:
      name: cpu
      target:
        type: Utilization
        averageUtilization: 50
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
php-apache   Deployment/php-apache   10%/50%    1         10        1          1m
```

#### Step 4: Generate Load to Test HPA

To see how the Horizontal Pod Autoscaler (HPA) reacts to increased load, you can set up a client Pod that continuously sends requests to your service (in this case, the php-apache service). This will generate load on the service, triggering the autoscaler to adjust the number of replicas based on the load.

```bash
kubectl run -i --tty load-generator --rm --image=busybox:1.28 --restart=Never -- /bin/sh -c "while sleep 0.01; do wget -q -O- http://php-apache; done"
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
kubectl delete -f deployment.yaml
kubectl delete -f service.yaml
```

