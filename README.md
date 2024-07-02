### What are Kubernetes Services?

In Kubernetes, Services are an abstraction layer that defines a logical set of Pods and a policy by which to access them. They enable network access to a set of Pods, providing a stable endpoint for communication within the Kubernetes cluster.

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
       name: nginx-nodeport-service
     spec:
       type: NodePort
       selector:
         app: nginx
       ports:
         - protocol: TCP
           port: 80
           targetPort: 80
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
