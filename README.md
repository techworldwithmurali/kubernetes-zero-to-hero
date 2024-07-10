### What is  Kubernetes DaemonSet?

- A **Kubernetes DaemonSet** ensures that a copy of a Pod runs on all (or some) nodes in the cluster.
- When new nodes are added to the cluster, DaemonSets automatically start the Pod on them. When nodes are removed from the cluster, the DaemonSet also removes the Pods running on those nodes.

### Purpose of DaemonSet

- **Log Collection**: Run a logging agent on every node to collect and ship logs.
- **Monitoring**: Deploy a monitoring agent on every node.
- **System Services**: Run system-level services, such as networking or storage management tools, on every node.
- **Security**: Ensure security agents are running on each node.

### Lab Session: Deploying DaemonSet

#### Objectives:
- Learn how to deploy a DaemonSet in Kubernetes.

#### Steps:

1. **Create a DaemonSet YAML File**:
   - Create a file named `daemonset.yaml` with the following content:
```yaml
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: nginx-daemonset
  labels:
    app: nginx
spec:
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
 ```

2. **Apply the DaemonSet**:
   ```bash
   kubectl apply -f daemonset.yaml
   ```

3. **Verify DaemonSet Deployment**:
   ```bash
   kubectl get daemonsets
   ```

4. **Check Pods Running on Nodes**:
   ```bash
   kubectl get pods -o wide
   ```

### Lab Session: Clean up DaemonSet

1. **Delete the DaemonSet**:
   ```bash
   kubectl delete -f daemonset.yaml
   ```

2. **Verify Deletion**:
   ```bash
   kubectl get daemonsets
   ```

---

### What is Kubernetes StatefulSets?

- **Kubernetes StatefulSets** manage the deployment and scaling of a set of Pods, and provide guarantees about the ordering and uniqueness of these Pods.
- Unlike Deployments, StatefulSets are designed for applications that require stable, unique network identifiers and stable, persistent storage.

## Use Cases for StatefulSets

StatefulSets in Kubernetes are ideal for managing stateful applications that require stable identities and persistent storage. Here are some common use cases:

1. **Databases**:
   StatefulSets are commonly used to manage databases such as MySQL, PostgreSQL, Cassandra, and MongoDB. Each database pod has its persistent storage volume and a stable network identity.

2. **Message Brokers**:
   Message brokers like Apache Kafka or RabbitMQ can benefit from StatefulSets. Pods can be managed with predictable names and storage volumes to ensure data persistence.

3. **NoSQL Databases**:
   Distributed NoSQL databases like Elasticsearch or Apache Cassandra often use StatefulSets to ensure that each node has stable storage and a unique network identity.

4. **Key-Value Stores**:
   StatefulSets are suitable for distributed key-value stores like etcd or Consul, where each pod plays a role in maintaining the cluster's consistency.

5. **Monitoring and Logging**:
   StatefulSets can be used for monitoring agents or logging agents, where each pod is responsible for collecting, processing, or aggregating data, and predictable naming is important.

6. **Custom Applications**:
   Any custom application with stateful requirements can leverage StatefulSets to manage its pods with stable network identities and persistent storage.

### Lab Session: Kubernetes StatefulSets

#### Objectives:
- Learn how to deploy a StatefulSet in Kubernetes.

#### Steps:

1. **Create a configmap for the StatefulSet**:
   - Create a file named `configmap.yaml` with the following content:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: webapp-config
  namespace: dev
data:
  APP_COLOR: blue
 ```

3. **Apply the configmap**:
   ```bash
   kubectl apply -f configmap.yaml
   ```

4. **Apply the configmap**:
   ```bash
   kubectl apply -f configmap.yaml
   ```

5. **Verify configmap configmap**:
   ```bash
   kubectl get configmap
   ```
2. **Create a StatefulSet YAML File**:
   - Create a file named `statefulset.yaml` with the following content:
```yaml
apiVersion: apps/v1
kind: StatefulSet
metadata:
  name: webapp
  namespace: dev
spec:
  replicas: 2
  selector:
    matchLabels:
      app: webapp
  template:
    metadata:
      labels:
        app: webapp
    spec:
      containers:
      - name: webapp-container
        image: nginx:latest
        ports:
        - containerPort: 80
        envFrom:
        - configMapRef:
            name: webapp-config

```

3. **Apply the statefulset**:
   ```bash
   kubectl apply -f statefulset.yaml
   ```

5. **Verify statefulset**:
   ```bash
   kubectl get statefulset
   ```

6. **Check Pods**:
   ```bash
   kubectl get pods -n dev-o wide
   ```

7. **Delete the StatefulSet and Service**:
   ```bash
   kubectl delete -f configmap.yaml
   kubectl delete -f statefulset.yaml
   ```
