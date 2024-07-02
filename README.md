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
