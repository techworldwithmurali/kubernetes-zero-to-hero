#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |


### Monitoring in Kubernetes

1. **Definition**: Monitoring in Kubernetes involves observing the state, health, and performance of applications, workloads, and infrastructure within a Kubernetes cluster.
   
2. **Purpose**:
   - Ensure reliability and availability of applications.
   - Optimize resource utilization.
   - Diagnose and troubleshoot issues.
   - Monitor overall cluster health and performance metrics.

3. **Key Components**:
   - Metrics: Collecting data on resource usage (CPU, memory), application health, and more.
   - Logs: Capturing application logs for debugging and auditing purposes.
   - Events: Recording Kubernetes events such as deployments, pod scheduling, and more.

4. **Tools and Technologies**:
   - Prometheus for metrics collection, storage, querying, and alerting.
   - Grafana for visualizing metrics and creating dashboards.
   - Logging solutions like Elasticsearch, Fluentd, and Kibana (EFK stack) for managing logs.

5. **Benefits**:
   - Proactive monitoring and alerting.
   - Faster issue detection and resolution.
   - Improved resource allocation and utilization.
   - Enhanced overall system performance and reliability.

### Prometheus

1. **Definition**: Prometheus is an open-source monitoring and alerting toolkit originally developed at SoundCloud, now maintained by the open-source community.

2. **Features**:
   - **Metrics Collection**: Scrapes metrics from instrumented jobs and applications.
   - **Storage**: Stores metrics in a time-series database.
   - **Querying**: Supports powerful queries using PromQL (Prometheus Query Language).
   - **Alerting**: Enables alerting based on predefined conditions.
   - **Scalability**: Designed to handle large-scale monitoring environments.

3. **Use Cases**:
   - Monitoring Kubernetes clusters, services, and applications.
   - Tracking resource usage (CPU, memory, network) and application performance metrics.
   - Alerting on abnormal behavior or thresholds exceeded.

4. **Integration**: Integrates well with Kubernetes for auto-discovery of services and applications to be monitored.

### Grafana

1. **Definition**: Grafana is an open-source platform specializing in visualization and analytics for time-series data.

2. **Features**:
   - **Visualization**: Creates visually appealing and interactive dashboards.
   - **Data Source Integration**: Connects with various data sources including Prometheus, Elasticsearch, InfluxDB, etc.
   - **Dashboarding**: Allows users to build custom dashboards to monitor metrics and logs.
   - **Alerting**: Provides alerting capabilities based on data thresholds.
   - **Templating**: Supports template variables for dynamic dashboards.

3. **Use Cases**:
   - Building monitoring dashboards for Kubernetes clusters and applications.
   - Visualizing metrics such as CPU usage, memory usage, pod health, etc.
   - Creating ad-hoc queries and exploring data trends.

4. **Integration**: Seamlessly integrates with Prometheus to leverage its metrics and create comprehensive monitoring solutions.

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

