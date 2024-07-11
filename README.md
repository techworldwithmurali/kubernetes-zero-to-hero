
### What is a Kubernetes Ingress Controller?

- A Kubernetes Ingress Controller is a specialized type of controller that manages the routing of external HTTP(S) traffic to services within a Kubernetes cluster.
- It implements the Ingress resource, which provides rules and configurations for routing traffic, enabling external access to internal services in a cluster.
- The Ingress Controller watches the Kubernetes API for changes to Ingress resources and updates its configuration accordingly.

### Features of a Kubernetes Ingress Controller:

1. **Load Balancing:**
   - Distributes incoming traffic across multiple backend services to ensure high availability and reliability.

2. **Path-Based and Host-Based Routing:**
   - Routes traffic to different services based on URL paths and host headers. For example, `/api` can be directed to one service, while `/app` is directed to another, and different domains can route to different services.

3. **SSL/TLS Termination:**
   - Handles SSL/TLS encryption and decryption, allowing secure HTTPS traffic to be routed to services within the cluster.

4. **Custom Rules and Annotations:**
   - Supports custom routing rules for advanced use cases and additional configuration through annotations on Ingress resources.

5. **Integration with External Load Balancers::**
   - Works with external load balancers (e.g., AWS ALB, GCP GLB) to provide additional capabilities and integration with cloud services..

6. **Health Checks and Monitoring:**
   - Monitors the health of backend services and routes traffic only to healthy instances, while also providing metrics and logs for monitoring traffic patterns, performance, and potential issues.
  
