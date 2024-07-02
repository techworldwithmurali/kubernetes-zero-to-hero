### What is a Kubernetes Namespace?

Kubernetes Namespace is a mechanism to divide cluster resources between multiple users or teams. It provides a way to create isolated environments within the same cluster, ensuring that resources do not conflict with each other and can be managed independently. Namespaces are especially useful in environments where multiple teams or projects share a single Kubernetes cluster.

### Lab Session: Creating and Deleting Kubernetes Namespace

#### Objectives:
- Learn how to create and delete Kubernetes Namespaces.
- Understand how to deploy applications in specific namespaces.

#### Steps:

1. **Set Up Your Environment:**
   - Ensure you have a Kubernetes cluster running and `kubectl` installed.

2. **Create a Namespace:**
   - Create a YAML file named `dev.yaml` with the following content:
     ```yaml
     apiVersion: v1
     kind: Namespace
     metadata:
       name: dev
     ```
   - Apply the YAML file to create the namespace:
     ```bash
     kubectl apply -f dev.yaml
     ```

3. **Verify Namespace Creation:**
   ```bash
   kubectl get namespaces
   ```

4. **Delete the Namespace:**
   ```bash
   kubectl delete namespace dev
   ```

5. **Create the Namespace Using `kubectl` Command:**
   ```bash
   kubectl create namespace dev
   ```

6. **Verify Namespace Creation:**
   ```bash
   kubectl get namespaces
   ```

7. **Delete the Namespace Using `kubectl` Command:**
   ```bash
   kubectl delete namespace dev
   ```

---

### Deploying a Sample Application in a Specific Namespace

#### Objectives:
- Learn how to deploy applications in a specific namespace.

#### Steps:

1. **Create a Namespace:**
   - Recreate the namespace if it was deleted:
     ```bash
     kubectl create namespace dev
     ```

2. **Create a Deployment YAML File:**
   - Create a file named `nginx-deployment.yaml` with the following content:
     ```yaml
     apiVersion: apps/v1
     kind: Deployment
     metadata:
       name: nginx-deployment
       namespace: dev
     spec:
       replicas: 3
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
             image: nginx:1.14.2
             ports:
             - containerPort: 80
     ```

3. **Deploy the Application:**
   ```bash
   kubectl apply -f nginx-deployment.yaml
   ```

4. **Verify Deployment:**
   ```bash
   kubectl get deployments -n dev
   kubectl get pods -n dev
   ```

5. **Delete the Deployment:**
   ```bash
   kubectl delete -f nginx-deployment.yaml
   ```

---

### What are Resource Quotas?

Resource Quotas are a way to manage the resource consumption of namespaces in Kubernetes. They ensure that a namespace does not exceed a specified amount of resource usage (e.g., CPU, memory, number of pods).

### Why Use Resource Quotas for Resource Management?

- **Prevent Resource Exhaustion**: Ensures no single namespace can consume all the resources, preventing denial of service to other namespaces.
- **Cost Management**: Helps in managing costs by controlling resource usage.
- **Multi-Tenancy**: Essential for environments with multiple users or teams sharing a single cluster.

### Resource Quotas vs. LimitRanges

- **Resource Quotas**: 
  - Enforce total resource limits within a namespace.
  - Examples: Total number of pods, total CPU, total memory.
  
- **LimitRanges**: 
  - Set default and maximum/minimum resource usage limits per pod/container within a namespace.
  - Examples: Minimum CPU per container, maximum memory per pod.

---

### Example: Setting Resource Quotas and LimitRanges

#### Creating Resource Quotas

1. **Create a YAML file named `resource-quota.yaml`** with the following content:
   ```yaml
   apiVersion: v1
   kind: ResourceQuota
   metadata:
     name: compute-resources
     namespace: dev
   spec:
     hard:
       pods: "10"
       requests.cpu: "4"
       requests.memory: "16Gi"
       limits.cpu: "8"
       limits.memory: "32Gi"
   ```

2. **Apply the Resource Quota:**
   ```bash
   kubectl apply -f resource-quota.yaml
   ```

#### Creating LimitRanges

1. **Create a YAML file named `limit-range.yaml`** with the following content:
   ```yaml
   apiVersion: v1
   kind: LimitRange
   metadata:
     name: limits
     namespace: dev
   spec:
     limits:
     - default:
         cpu: "500m"
         memory: "512Mi"
       defaultRequest:
         cpu: "250m"
         memory: "256Mi"
       type: Container
   ```

2. **Apply the LimitRange:**
   ```bash
   kubectl apply -f limit-range.yaml
   ```
