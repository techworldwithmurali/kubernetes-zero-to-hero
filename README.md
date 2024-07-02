### What is Monitoring in Kubernetes

Monitoring in Kubernetes refers to the process of observing the state and performance of applications, workloads, and infrastructure within a Kubernetes cluster. It involves collecting metrics, logs, and events to gain insights into resource utilization, application health, and overall cluster performance.

### What is Prometheus

Prometheus is an open-source monitoring and alerting toolkit originally built at SoundCloud. It is now a standalone open-source project maintained independently of any company. Prometheus is designed for reliability, scalability, and to provide a single source of truth for monitoring data in a Kubernetes environment. It scrapes metrics from instrumented jobs, stores them efficiently, and supports powerful queries and alerting.

### What is Grafana?

Grafana is an open-source platform for monitoring and observability, specializing in providing rich visualizations and analytics for time series data. It integrates with various data sources, including Prometheus, to create dashboards that enable users to monitor and analyze metrics and logs from different systems.

### Installation of Prometheus and Grafana using Helm Chart

#### Step 1: Install Helm

Ensure you have Helm installed on your local machine and configured to connect to your Kubernetes cluster.

#### Step 2: Add Helm Chart Repositories

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
```

#### Step 3: Install Prometheus

Create a `values-prometheus.yaml` file with custom configuration for Prometheus:

```yaml
serverFiles:
  prometheus.yml:
    scrape_configs:
      - job_name: 'kubernetes-apiservers'
        kubernetes_sd_configs:
          - role: endpoints
        scheme: https
        tls_config:
          ca_file: /var/run/secrets/kubernetes.io/serviceaccount/ca.crt
        bearer_token_file: /var/run/secrets/kubernetes.io/serviceaccount/token
        relabel_configs:
          - source_labels: [__meta_kubernetes_namespace, __meta_kubernetes_service_name, __meta_kubernetes_endpoint_port_name]
            action: keep
            regex: default;kubernetes;https

alertmanagerFiles:
  alertmanager.yml:
    global:
      resolve_timeout: 5m
    route:
      group_by: ['alertname', 'namespace', 'service']
      group_wait: 30s
      group_interval: 5m
      repeat_interval: 3h
    receivers:
      - name: default-receiver
        webhook_configs:
          - url: http://alertmanager-webhook
```

Install Prometheus using Helm:

```bash
helm install prometheus prometheus-community/prometheus -f values-prometheus.yaml
```

#### Step 4: Install Grafana

Create a `values-grafana.yaml` file with custom configuration for Grafana:

```yaml
adminUser: admin
adminPassword: admin
datasources:
  datasources.yaml:
    apiVersion: 1
    datasources:
      - name: Prometheus
        type: prometheus
        url: http://prometheus-server
        access: proxy
        isDefault: true
dashboards:
  defaultDashboardsEnabled: true
  default:
    k8s:
      url: https://github.com/prometheus-operator/kube-prometheus/tree/main/manifests/grafana-dashboards
```

Install Grafana using Helm:

```bash
helm install grafana grafana/grafana -f values-grafana.yaml
```

#### Step 5: Access Prometheus and Grafana

Retrieve the Prometheus and Grafana URLs:

```bash
kubectl get svc prometheus-server -n default
kubectl get svc grafana -n default
```

Access Prometheus at `http://prometheus-server:<port>` and Grafana at `http://grafana:<port>`. Log in to Grafana using the credentials configured (`admin/admin` by default).

### Summary

Monitoring in Kubernetes involves observing and analyzing metrics and logs to ensure the health and performance of applications and infrastructure. Prometheus is used for metrics collection and storage, while Grafana provides visualization and analytics capabilities. Installing Prometheus and Grafana using Helm simplifies the setup process and allows for effective monitoring and observability within Kubernetes clusters.
