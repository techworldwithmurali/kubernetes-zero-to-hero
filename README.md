### What are Kubernetes DaemonSets?

A **Kubernetes DaemonSet** ensures that a copy of a Pod runs on all (or some) nodes in the cluster. When new nodes are added to the cluster, DaemonSets automatically start the Pod on them. When nodes are removed from the cluster, the DaemonSet also removes the Pods running on those nodes.

### Purpose of DaemonSets

- **Log Collection**: Run a logging agent on every node to collect and ship logs.
- **Monitoring**: Deploy a monitoring agent on every node.
- **System Services**: Run system-level services, such as networking or storage management tools, on every node.
- **Security**: Ensure security agents are running on each node.

### Lab Session: Deploying DaemonSets

#### Objectives:
- Learn how to deploy a DaemonSet in Kubernetes.

#### Steps:

1. **Create a DaemonSet YAML File**:
   - Create a file named `fluentd-daemonset.yaml` with the following content:
     ```yaml
     apiVersion: apps/v1
     kind: DaemonSet
     metadata:
       name: fluentd
       labels:
         app: fluentd
     spec:
       selector:
         matchLabels:
           name: fluentd
       template:
         metadata:
           labels:
             name: fluentd
         spec:
           containers:
           - name: fluentd
             image: fluent/fluentd:v1.9.1-1.0
             resources:
               limits:
                 memory: "200Mi"
                 cpu: "100m"
               requests:
                 memory: "200Mi"
                 cpu: "100m"
             volumeMounts:
             - name: varlog
               mountPath: /var/log
             - name: varlibdockercontainers
               mountPath: /var/lib/docker/containers
               readOnly: true
           volumes:
           - name: varlog
             hostPath:
               path: /var/log
           - name: varlibdockercontainers
             hostPath:
               path: /var/lib/docker/containers
     ```

2. **Apply the DaemonSet**:
   ```bash
   kubectl apply -f fluentd-daemonset.yaml
   ```

3. **Verify DaemonSet Deployment**:
   ```bash
   kubectl get daemonsets
   ```

4. **Check Pods Running on Nodes**:
   ```bash
   kubectl get pods -o wide
   ```

### Lab Session: Clean up DaemonSets

1. **Delete the DaemonSet**:
   ```bash
   kubectl delete -f fluentd-daemonset.yaml
   ```

2. **Verify Deletion**:
   ```bash
   kubectl get daemonsets
   ```

---

### What is Kubernetes StatefulSets?

**Kubernetes StatefulSets** manage the deployment and scaling of a set of Pods, and provide guarantees about the ordering and uniqueness of these Pods. Unlike Deployments, StatefulSets are designed for applications that require stable, unique network identifiers and stable, persistent storage.

### Use Cases for StatefulSets

- **Databases**: Deploy stateful applications like MySQL, PostgreSQL, etc.
- **Distributed Systems**: Applications that require stable identity and persistent storage, like Apache Kafka or Cassandra.
- **Leader Election**: Applications that need to maintain leader-election among members.

### Lab Session: Kubernetes StatefulSets

#### Objectives:
- Learn how to deploy a StatefulSet in Kubernetes.

#### Steps:

1. **Create a StatefulSet YAML File**:
   - Create a file named `web-statefulset.yaml` with the following content:
     ```yaml
     apiVersion: apps/v1
     kind: StatefulSet
     metadata:
       name: web
     spec:
       selector:
         matchLabels:
           app: nginx
       serviceName: "nginx"
       replicas: 3
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
               name: web
             volumeMounts:
             - name: www
               mountPath: /usr/share/nginx/html
       volumeClaimTemplates:
       - metadata:
           name: www
         spec:
           accessModes: [ "ReadWriteOnce" ]
           resources:
             requests:
               storage: 1Gi
     ```

2. **Create a Headless Service for the StatefulSet**:
   - Create a file named `nginx-service.yaml` with the following content:
     ```yaml
     apiVersion: v1
     kind: Service
     metadata:
       name: nginx
     spec:
       ports:
       - port: 80
         name: web
       clusterIP: None
       selector:
         app: nginx
     ```

3. **Apply the Headless Service**:
   ```bash
   kubectl apply -f nginx-service.yaml
   ```

4. **Apply the StatefulSet**:
   ```bash
   kubectl apply -f web-statefulset.yaml
   ```

5. **Verify StatefulSet Deployment**:
   ```bash
   kubectl get statefulsets
   ```

6. **Check Pods**:
   ```bash
   kubectl get pods -o wide
   ```

7. **Delete the StatefulSet and Service**:
   ```bash
   kubectl delete -f web-statefulset.yaml
   kubectl delete -f nginx-service.yaml
   ```
