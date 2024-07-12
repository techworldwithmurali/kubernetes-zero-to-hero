#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

### What is a Kubernetes Namespace?

- Kubernetes Namespaces are a mechanism for creating multiple virtual clusters within a single physical Kubernetes cluster, providing a way to logically divide the cluster into isolated segments.
- Each namespace has its own set of resources, including pods, services, and storage, separate from those in other namespaces.

## Initial Namespaces in Kubernetes

Kubernetes starts with four initial namespaces:

### default
- **Purpose**: Allows users to start using their new cluster without creating a namespace first.
- **Characteristics**:
  - Regular namespace intended for most workloads and services in the cluster.
  - Resources created without specifying a namespace are placed here by default.
  - Used for logical separation of resources.
  - Commonly utilized to organize applications and services, such as separating environments (e.g., development, testing, production) or by teams/projects.

### kube-node-lease
- **Purpose**: Holds Lease objects associated with each node.
- **Characteristics**:
  - Node leases enable the kubelet to send heartbeats, allowing the control plane to detect node failures.
  
### kube-public
- **Purpose**: Reserved for resources that should be visible and readable publicly throughout the entire cluster.
- **Characteristics**:
  - Readable by all clients, including unauthenticated ones.
  - Mostly used for cluster-wide public information.
  
### kube-system
- **Purpose**: Reserved for objects created by the Kubernetes system.
- **Characteristics**:
  - Contains resources managed by Kubernetes, such as system processes and controllers.

## Benefits of Using Namespaces

- **Resource Isolation**: Ensures that resources in different namespaces do not interfere with each other.
- **Access Control**: Enables fine-grained access control to resources.
- **Resource Quotas**: Allows the application of resource quotas to limit the amount of resources a namespace can consume.
- **Environment Separation**: Facilitates the separation of environments (development, staging, production) within the same cluster.

Namespaces provide a way to manage complex Kubernetes clusters by organizing and isolating resources, thus enhancing security and maintainability.

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

**Create the Namespace Using `kubectl` Command:**
   ```bash
   kubectl create namespace dev
   ```

. **Verify Namespace Creation:**
   ```bash
   kubectl get namespaces
   ```

 **Delete the Namespace Using `kubectl` Command:**
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
  
## Example of a Resource Quotas
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

### Explanation of Fields

- **apiVersion: v1**
  - Specifies the version of the Kubernetes API.

- **kind: ResourceQuota**
  - Defines the type of Kubernetes object. In this case, it is a ResourceQuota.

- **metadata**
  - **name: compute-resources**
    - The name of the ResourceQuota object.
  - **namespace: dev**
    - The namespace to which this ResourceQuota applies.

- **spec**
  - Contains the specification of the ResourceQuota.

### ResourceQuota Specification (spec)

- **hard**
  - Specifies the hard limits for resource usage within the namespace. These limits are the maximum allowable usage for various resource types.

#### Resource Constraints

- **pods: "10"**
  - Limits the total number of pods in the `dev` namespace to 10.

- **requests.cpu: "4"**
  - Limits the total amount of CPU resources requested by all containers in the `dev` namespace to 4 CPU cores.

- **requests.memory: "16Gi"**
  - Limits the total amount of memory requested by all containers in the `dev` namespace to 16 GiB.

- **limits.cpu: "8"**
  - Limits the total amount of CPU resources that all containers in the `dev` namespace can use to 8 CPU cores.

- **limits.memory: "32Gi"**
  - Limits the total amount of memory that all containers in the `dev` namespace can use to 32 GiB.

### How ResourceQuota Works

- When a ResourceQuota is applied to a namespace, it enforces the defined resource limits and ensures that the sum of resource requests and limits across all pods and containers in the namespace does not exceed the specified values.
- If an attempt is made to create or update a resource (such as a pod) that would exceed these limits, the operation will be denied.

# LimitRange
- In Kubernetes, a **LimitRange** is a resource policy that you can apply to a namespace to enforce constraints on resource usage for containers and pods.
- LimitRanges are used to specify default resource limits and request values, as well as to set maximum and minimum constraints for resources such as CPU and memory.

## Purpose of LimitRange

- **Enforce Resource Limits**: Ensures that all containers and pods in a namespace have resource limits defined.
- **Prevent Resource Overcommitment**: Helps avoid situations where a namespace overuses resources, potentially impacting other namespaces.
- **Set Default Resource Requests and Limits**: Automatically applies default resource requests and limits to containers that do not have them specified.

## Key Concepts

- **Resource Requests**: The amount of CPU and memory guaranteed to a container.
- **Resource Limits**: The maximum amount of CPU and memory that a container is allowed to use.

## Example of a LimitRange

Here's an example of a LimitRange YAML configuration:

```yaml
apiVersion: v1
kind: LimitRange
metadata:
  name: limit-range
  namespace: dev
spec:
  limits:
  - max:
      cpu: "2"
      memory: "1Gi"
    min:
      cpu: "200m"
      memory: "6Mi"
    default:
      cpu: "500m"
      memory: "256Mi"
    defaultRequest:
      cpu: "300m"
      memory: "128Mi"
    type: Container
```

### Explanation of the Fields

- **max**: Specifies the maximum amount of resources a container can request.
  - `cpu: "2"`: The maximum CPU limit is 2 cores.
  - `memory: "1Gi"`: The maximum memory limit is 1 GiB.
  
- **min**: Specifies the minimum amount of resources a container can request.
  - `cpu: "200m"`: The minimum CPU request is 200 millicores.
  - `memory: "6Mi"`: The minimum memory request is 6 MiB.
  
- **default**: Sets the default resource limits if none are specified for a container.
  - `cpu: "500m"`: The default CPU limit is 500 millicores.
  - `memory: "256Mi"`: The default memory limit is 256 MiB.
  
- **defaultRequest**: Sets the default resource requests if none are specified for a container.
  - `cpu: "300m"`: The default CPU request is 300 millicores.
  - `memory: "128Mi"`: The default memory request is 128 MiB.
  
- **type**: Indicates the type of resource to which the limits apply. In this case, it is set to `Container`.
-----
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

