### What are Kubernetes Services?

- In Kubernetes, Services are an abstraction layer that defines a logical set of Pods and a policy by which to access them.
- They enable network access to a set of Pods, providing a stable endpoint for communication within the Kubernetes cluster.

### Types of Kubernetes Services:

1. **ClusterIP**:
   - Exposes the Service on an internal IP address accessible only within the cluster.
   - Default type when not specified explicitly.

2. **NodePort**:
   - Exposes the Service on each Node's IP at a static port.
   - Makes the Service accessible from outside the cluster using `<NodeIP>:<NodePort>`.

3. **LoadBalancer**:
   - Creates an external load balancer in the cloud provider's network (if supported).
   - Routes external traffic to the Service.

4. **ExternalName**:
   - Maps a Service to a DNS name.
   - Used for integrating with external services via DNS.

### What is ClusterIP?

- **ClusterIP** is the default Kubernetes Service type.
- It assigns a stable IP address to the Service within the cluster.
- The Service is accessible only from within the Kubernetes cluster.

### Lab Session: ClusterIP

#### Objectives:
- Learn how to create a Kubernetes Service of type ClusterIP.

#### Steps:

1. **Create a Deployment:**
   - Create a deployment YAML file, e.g., `nginx-deployment.yaml`, to deploy a sample application (e.g., Nginx).
   - Apply the deployment:
     ```bash
     kubectl apply -f nginx-deployment.yaml
     ```

2. **Create a ClusterIP Service YAML:**
   - Create a file named `nginx-service.yaml` with the following content:
     ```yaml
     apiVersion: v1
     kind: Service
     metadata:
       name: nginx-service
     spec:
       type: ClusterIP
       selector:
         app: nginx
       ports:
         - protocol: TCP
           port: 80
           targetPort: 80
     ```

3. **Apply the ClusterIP Service:**
   ```bash
   kubectl apply -f nginx-service.yaml
   ```

4. **Verify Service Creation:**
   ```bash
   kubectl get services
   ```

5. **Access the Service Within the Cluster:**
   - Use the ClusterIP to access the deployed application:
     ```bash
     curl http://nginx-service:80
     ```
# What is Node Port 
- A **NodePort** is a type of Kubernetes Service that exposes a service on a specific port on each Node in the cluster, making it accessible from outside the cluster.
- This allows external traffic to access the service running inside the Kubernetes cluster.

### Key Concepts

- **NodePort Range**: By default, NodePort values range between 30000 and 32767.
- **Cluster IP**: NodePort services also get a ClusterIP, which allows them to be accessed from within the cluster.

### How NodePort Works

1. **Service Definition**: When you define a service with a `type: NodePort`, Kubernetes allocates a port from the NodePort range (or you can specify one).
2. **Node Exposure**: Kubernetes makes the service accessible on that port across all nodes in the cluster.
3. **External Access**: You can access the service from outside the cluster by sending a request to any Node's IP address at the allocated NodePort.

### Lab Session: NodePort

#### Objectives:
- Learn how to create a Kubernetes Service of type NodePort.

#### Steps:

1. **Create a NodePort Service YAML:**
   - Create a file named `nginx-nodeport-service.yaml` with the following content:
     ```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-app-service
  namespace: dev
spec:
  selector:
    app: my-app
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
    nodePort: 32500
  type: NodePort
     ```

2. **Apply the NodePort Service:**
   ```bash
   kubectl apply -f nginx-nodeport-service.yaml
   ```

3. **Verify Service Creation:**
   ```bash
   kubectl get services
   ```

4. **Access the Service Using NodePort:**
   - Get the NodePort allocated (let's assume `NodePort: 30080`):
     ```bash
     kubectl get services nginx-nodeport-service
     ```
   - Access the service from outside the cluster using `<NodeIP>:30080`.

# LoadBalancer
In Kubernetes, a **LoadBalancer** is a type of Service that automatically provisions and manages an external load balancer for routing external traffic to the pods within the cluster. This type of service abstracts the complexity of external load balancing and integrates it seamlessly with Kubernetes.

### Key Concepts

- **External Load Balancer**: A LoadBalancer service typically provisions an external load balancer from the cloud provider (e.g., AWS, GCP, Azure).
- **Automatic Configuration**: The service is automatically configured to distribute traffic to the appropriate pods.
- **External Access**: Provides a stable IP address (or DNS name) for accessing the service from outside the cluster.

### How LoadBalancer Works

1. **Service Definition**: When you define a service with `type: LoadBalancer`, Kubernetes provisions an external load balancer through the cloud provider.
2. **Traffic Routing**: The external load balancer routes incoming traffic to the service, which then forwards the traffic to the appropriate pods based on the service's selector.
3. **Stable Endpoint**: The external load balancer provides a stable IP address or DNS name for accessing the service.

### Lab Session: Load Balancer

#### Objectives:
- Learn how to create a Kubernetes Service of type LoadBalancer.

#### Steps:

1. **Create a LoadBalancer Service YAML:**
   - Create a file named `nginx-loadbalancer-service.yaml` with the following content:
     ```yaml
     apiVersion: v1
     kind: Service
     metadata:
       name: nginx-loadbalancer-service
     spec:
       type: LoadBalancer
       selector:
         app: nginx
       ports:
         - protocol: TCP
           port: 80
           targetPort: 80
     ```

2. **Apply the LoadBalancer Service:**
   ```bash
   kubectl apply -f nginx-loadbalancer-service.yaml
   ```

3. **Verify Service Creation:**
   ```bash
   kubectl get services
   ```

4. **Get the External IP Address (if applicable):**
   - Depending on your cloud provider, the external IP will be allocated.
   - Get the external IP using:
     ```bash
     kubectl get services nginx-loadbalancer-service
     ```

5. **Access the Service via Load Balancer:**
   - Use the external IP to access the deployed application.
