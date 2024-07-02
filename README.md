#### What are Taints and Tolerations?

**Taints** and **tolerations** work together to ensure that pods are not scheduled onto inappropriate nodes. Taints are applied to nodes, making the nodes repel pods that do not tolerate the taints.

- **Taints**: Applied to a node, a taint prevents any pod that does not have a matching toleration from being scheduled on that node.
  - Example: `kubectl taint nodes node1 key=value:NoSchedule`

- **Tolerations**: Allow pods to be scheduled on nodes with matching taints.
  - Example: A pod with the following toleration can tolerate the above taint:
    ```yaml
    tolerations:
    - key: "key"
      operator: "Equal"
      value: "value"
      effect: "NoSchedule"
    ```

### Lab Session - Applying Taints to Nodes

1. **List the Nodes**:
   ```bash
   kubectl get nodes
   ```

2. **Apply a Taint to a Node**:
   ```bash
   kubectl taint nodes <node-name> key=value:NoSchedule
   ```

3. **Verify the Taint**:
   ```bash
   kubectl describe node <node-name> | grep Taints
   ```

### Creating Toleration Specifications

1. **Create a Deployment YAML File**:
   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: toleration-deployment
   spec:
     replicas: 1
     selector:
       matchLabels:
         app: toleration-app
     template:
       metadata:
         labels:
           app: toleration-app
       spec:
         containers:
         - name: nginx
           image: nginx:latest
         tolerations:
         - key: "key"
           operator: "Equal"
           value: "value"
           effect: "NoSchedule"
   ```

2. **Deploy the YAML File**:
   ```bash
   kubectl apply -f toleration-deployment.yaml
   ```

3. **Verify the Pod is Running on the Tainted Node**:
   ```bash
   kubectl get pods -o wide
   ```

### Lab Session - Implementing Taints and Tolerations

1. **Apply a Taint to a Node**:
   ```bash
   kubectl taint nodes <node-name> key=value:NoSchedule
   ```

2. **Create a Deployment with a Matching Toleration**:
   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: tolerant-deployment
   spec:
     replicas: 1
     selector:
       matchLabels:
         app: tolerant-app
     template:
       metadata:
         labels:
           app: tolerant-app
       spec:
         containers:
         - name: nginx
           image: nginx:latest
         tolerations:
         - key: "key"
           operator: "Equal"
           value: "value"
           effect: "NoSchedule"
   ```

3. **Deploy the YAML File**:
   ```bash
   kubectl apply -f tolerant-deployment.yaml
   ```

4. **Verify the Pod is Scheduled on the Tainted Node**:
   ```bash
   kubectl get pods -o wide
   ```

### Node Affinity and Node Anti-Affinity in Kubernetes

**Node Affinity** and **Node Anti-Affinity** are used to control which nodes your pods can be scheduled on based on labels on the nodes.

- **Node Affinity**: Ensures that pods are scheduled on nodes with specific labels.
  - Example:
    ```yaml
    affinity:
      nodeAffinity:
        requiredDuringSchedulingIgnoredDuringExecution:
          nodeSelectorTerms:
          - matchExpressions:
            - key: "disktype"
              operator: In
              values:
              - ssd
    ```

- **Node Anti-Affinity**: Ensures that pods are not scheduled on nodes with specific labels.
  - Example:
    ```yaml
    affinity:
      nodeAffinity:
        requiredDuringSchedulingIgnoredDuringExecution:
          nodeSelectorTerms:
          - matchExpressions:
            - key: "disktype"
              operator: NotIn
              values:
              - hdd
    ```

### Lab Session - Implementing Node Affinity and Node Anti-Affinity

1. **Label a Node**:
   ```bash
   kubectl label nodes <node-name> disktype=ssd
   ```

2. **Create a Deployment with Node Affinity**:
   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: affinity-deployment
   spec:
     replicas: 1
     selector:
       matchLabels:
         app: affinity-app
     template:
       metadata:
         labels:
           app: affinity-app
       spec:
         affinity:
           nodeAffinity:
             requiredDuringSchedulingIgnoredDuringExecution:
               nodeSelectorTerms:
               - matchExpressions:
                 - key: "disktype"
                   operator: In
                   values:
                   - ssd
         containers:
         - name: nginx
           image: nginx:latest
   ```

3. **Deploy the YAML File**:
   ```bash
   kubectl apply -f affinity-deployment.yaml
   ```

4. **Verify the Pod is Scheduled on the Labeled Node**:
   ```bash
   kubectl get pods -o wide
   ```

5. **Create a Deployment with Node Anti-Affinity**:
   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: anti-affinity-deployment
   spec:
     replicas: 1
     selector:
       matchLabels:
         app: anti-affinity-app
     template:
       metadata:
         labels:
           app: anti-affinity-app
       spec:
         affinity:
           nodeAffinity:
             requiredDuringSchedulingIgnoredDuringExecution:
               nodeSelectorTerms:
               - matchExpressions:
                 - key: "disktype"
                   operator: NotIn
                   values:
                   - hdd
         containers:
         - name: nginx
           image: nginx:latest
   ```

6. **Deploy the YAML File**:
   ```bash
   kubectl apply -f anti-affinity-deployment.yaml
   ```

7. **Verify the Pod is Scheduled on a Node without the HDD Label**:
   ```bash
   kubectl get pods -o wide
   ```
