### What is Monitoring in Kubernetes

Monitoring in Kubernetes refers to the process of observing the state and performance of applications, workloads, and infrastructure within a Kubernetes cluster. It involves collecting metrics, logs, and events to gain insights into resource utilization, application health, and overall cluster performance.

### What is Prometheus

Prometheus is an open-source monitoring and alerting toolkit originally built at SoundCloud. It is now a standalone open-source project maintained independently of any company. Prometheus is designed for reliability, scalability, and to provide a single source of truth for monitoring data in a Kubernetes environment. It scrapes metrics from instrumented jobs, stores them efficiently, and supports powerful queries and alerting.

### What is Grafana?

Grafana is an open-source platform for monitoring and observability, specializing in providing rich visualizations and analytics for time series data. It integrates with various data sources, including Prometheus, to create dashboards that enable users to monitor and analyze metrics and logs from different systems.

### Installation of Prometheus and Grafana using Helm Chart

**Prerequisites:**
1. Ensure that the EKS Cluster is up and running.
2. Install Helm3 on your Windows machine.
3. Connect to your EKS cluster using `kubectl`.
4. Clone the Prometheus GitHub repository locally for custom configurations:
   - [Prometheus Helm Charts Repository](https://github.com/prometheus-community/helm-charts/blob/main/charts/kube-prometheus-stack/values.yaml)

**Implementation Steps:**

**Step 1: Add Helm Stable Charts**
```bash
helm repo add stable https://charts.helm.sh/stable
```

**Step 2: Add Prometheus Helm repository**
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
```

**Step 3: Explore available charts**
```bash
helm search repo prometheus-community
```

**Step 4: Create Prometheus namespace**
```bash
kubectl create namespace prometheus
```

**Step 5: Install kube-prometheus-stack**
```bash
# Install using default values
helm install prometheus-stack prometheus-community/kube-prometheus-stack -n prometheus

# Install with custom values.yaml (if applicable)
# helm install prometheus-stack prometheus-community/kube-prometheus-stack -n prometheus -f custom-values.yaml
```

**Step 6: Check Prometheus and Grafana pods**
```bash
kubectl get pods -n prometheus
```

**Step 7: Check Prometheus and Grafana services**
```bash
kubectl get svc -n prometheus
```

**Step 8: Enable external access (LoadBalancer or NodePort)**
```bash
# Edit the services to enable external access
kubectl edit svc prometheus-stack-kube-prom-prometheus -n prometheus
kubectl edit svc prometheus-stack-grafana -n prometheus
```

**Step 9: Confirm service changes and get Load Balancer URL**
```bash
kubectl get svc -n prometheus
```

**Step 10: Access Prometheus and Grafana using the Load Balancer**

- **Access Prometheus UI:**
  - URL: `http://loadbalancer-url:9090`

- **Access Grafana UI:**
  - URL: `http://loadbalancer-url:80`
  - **Login Credentials:**
    - Username: `admin`
    - Password: `prom-operator`

**Conclusion:**
Congratulations! You have successfully deployed Prometheus and Grafana on your EKS cluster using Helm. You can now start visualizing and monitoring your metrics.
