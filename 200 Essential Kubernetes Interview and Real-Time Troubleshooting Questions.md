


### 1. Question:  
Which Kubernetes object ensures a specified number of pod replicas are running?  
- **A. Deployment**  
- **B. Service**  
- **C. ReplicaSet**  
- **D. ConfigMap**  
**Correct Answer:** **C. ReplicaSet**  
**Explanation:** A ReplicaSet maintains the desired number of pod replicas. Deployments manage ReplicaSets internally.  

---

### 2. Question:  
What is the primary purpose of a Service in Kubernetes?  
- **A. Creating pods**  
- **B. Exposing pods to network traffic**  
- **C. Replicating containers**  
- **D. Storing configurations**  
**Correct Answer:** **B. Exposing pods to network traffic**  
**Explanation:** Services provide stable network endpoints to expose pods, allowing communication both internally and externally.  

---

### 3. Question:  
Which component schedules pods to nodes in Kubernetes?  
- **A. kube-apiserver**  
- **B. kube-scheduler**  
- **C. kube-controller-manager**  
- **D. kubelet**  
**Correct Answer:** **B. kube-scheduler**  
**Explanation:** The kube-scheduler is responsible for assigning pods to appropriate nodes based on resource requirements and constraints.  

---

### 4. Question:  
What command is used to view all running pods in the default namespace?  
- **A. kubectl get nodes**  
- **B. kubectl get services**  
- **C. kubectl get pods**  
- **D. kubectl get deployments**  
**Correct Answer:** **C. kubectl get pods**  
**Explanation:** The **kubectl get pods** command lists all pods in the current namespace.  

---

### 5. Question:  
What does the **kubectl describe pod** command display?  
- **A. Pod's YAML definition**  
- **B. Pod's logs**  
- **C. Detailed information about the pod**  
- **D. Node resource usage**  
**Correct Answer:** **C. Detailed information about the pod**  
**Explanation:** The **kubectl describe pod** command provides detailed information, including events, configurations, and resource limits.  

---

### 6. Question:  
Which command is used to delete a Kubernetes namespace?  
- **A. kubectl delete ns**  
- **B. kubectl delete namespace**  
- **C. kubectl remove namespace**  
- **D. kubectl rm ns**  
**Correct Answer:** **A. kubectl delete ns**  
**Explanation:** The shorthand **ns** is used for namespaces in **kubectl** commands.  

---

### 7. Question:  
What does the **kubelet** component do in a Kubernetes cluster?  
- **A. Schedules pods to nodes**  
- **B. Manages node-level pod lifecycle**  
- **C. Provides the API server for communication**  
- **D. Handles authentication**  
**Correct Answer:** **B. Manages node-level pod lifecycle**  
**Explanation:** Kubelet runs on every node and ensures that the containers are running in a pod as expected.  

---

### 8. Question:  
Which Kubernetes object provides external access to services?  
- **A. ConfigMap**  
- **B. PersistentVolumeClaim**  
- **C. Ingress**  
- **D. Pod**  
**Correct Answer:** **C. Ingress**  
**Explanation:** Ingress exposes HTTP/HTTPS routes to services and provides traffic routing.  

---

### 9. Question:  
What does a ConfigMap store in Kubernetes?  
- **A. Sensitive data like passwords**  
- **B. Non-sensitive configuration data**  
- **C. Container images**  
- **D. Resource requests and limits**  
**Correct Answer:** **B. Non-sensitive configuration data**  
**Explanation:** ConfigMaps store non-sensitive configuration data like environment variables and configuration files.  

---

### 10. Question:  
Which command lists all available Kubernetes contexts?  
- **A. kubectl config get-contexts**  
- **B. kubectl list contexts**  
- **C. kubectl config contexts**  
- **D. kubectl get contexts**  
**Correct Answer:** **A. kubectl config get-contexts**  
**Explanation:** This command lists all Kubernetes contexts configured on the system.  

---

### 11. Question:  
What is the role of the **kube-controller-manager**?  
- **A. Scheduling pods**  
- **B. Managing cluster state**  
- **C. Running all controllers for the cluster**  
- **D. Exposing services externally**  
**Correct Answer:** **C. Running all controllers for the cluster**  
**Explanation:** The **kube-controller-manager** runs various controllers, such as the replication controller and node controller, to manage cluster state.  

---

### 12. Question:  
Which object is used to automatically mount secrets into pods?  
- **A. PersistentVolumeClaim**  
- **B. ConfigMap**  
- **C. Volume**  
- **D. Secret**  
**Correct Answer:** **D. Secret**  
**Explanation:** Secrets store sensitive data (like passwords or tokens) and can be mounted into pods securely.  

---

### 13. Question:  
What type of Kubernetes Service provides a stable IP address and DNS name within the cluster?  
- **A. LoadBalancer**  
- **B. NodePort**  
- **C. ClusterIP**  
- **D. ExternalName**  
**Correct Answer:** **C. ClusterIP**  
**Explanation:** ClusterIP is the default service type, providing internal-only communication within the cluster.  

---

### 14. Question:  
Which command creates a Kubernetes Deployment?  
- **A. kubectl create service**  
- **B. kubectl create deployment**  
- **C. kubectl apply deployment**  
- **D. kubectl run deployment**  
**Correct Answer:** **B. kubectl create deployment**  
**Explanation:** The **kubectl create deployment** command creates a deployment object in the cluster.  

---

### 15. Question:  
How can you scale a deployment to 5 replicas?  
- **A. kubectl scale replicas=5 deployment <deployment-name>**  
- **B. kubectl scale deployment <deployment-name> --replicas=5**  
- **C. kubectl update replicas=5 deployment <deployment-name>**  
- **D. kubectl set deployment <deployment-name> --replicas=5**  
**Correct Answer:** **B. kubectl scale deployment <deployment-name> --replicas=5**  
**Explanation:** The **kubectl scale** command adjusts the number of replicas for a deployment.  

---

### 16. Question:  
What does the **kubectl logs** command retrieve?  
- **A. Pod resource details**  
- **B. Events for a pod**  
- **C. Logs from a container in a pod**  
- **D. Application metrics**  
**Correct Answer:** **C. Logs from a container in a pod**  
**Explanation:** **kubectl logs** retrieves logs from a specific container in a pod.  

---

### 17. Question:  
What is the main difference between a StatefulSet and a Deployment?  
- **A. StatefulSet manages ephemeral pods**  
- **B. StatefulSet provides stable network identities**  
- **C. StatefulSet does not support scaling**  
- **D. StatefulSet uses ReplicaSets**  
**Correct Answer:** **B. StatefulSet provides stable network identities**  
**Explanation:** StatefulSets are used for stateful applications requiring stable storage, persistent identity, or ordered deployment.  

---

### 18. Question:  
How do you delete a pod forcefully?  
- **A. kubectl delete pod <pod-name>**  
- **B. kubectl delete pod <pod-name> --grace-period=0 --force**  
- **C. kubectl remove pod <pod-name> --force**  
- **D. kubectl kill pod <pod-name>**  
**Correct Answer:** **B. kubectl delete pod <pod-name> --grace-period=0 --force**  
**Explanation:** Adding **--grace-period=0** and **--force** bypasses the normal termination process.  

---

### 19. Question:  
Which Kubernetes component provides the primary API entry point?  
- **A. kube-scheduler**  
- **B. kube-proxy**  
- **C. kube-apiserver**  
- **D. etcd**  
**Correct Answer:** **C. kube-apiserver**  
**Explanation:** The **kube-apiserver** exposes the Kubernetes API, serving as the central management point for all cluster interactions.  

---

### 20. Question:  
What does a **DaemonSet** ensure?  
- **A. All nodes run a copy of a specific pod**  
- **B. Pods are scaled to multiple replicas**  
- **C. Pods are exposed to external traffic**  
- **D. Pod logs are collected centrally**  
**Correct Answer:** **A. All nodes run a copy of a specific pod**  
**Explanation:** A **DaemonSet** ensures that a pod runs on every node in the cluster, often used for node-level services like logging or monitoring.  

---

### 21. Question:  
Which command is used to create a ConfigMap in Kubernetes?  
- **A. kubectl create configmap**  
- **B. kubectl create config**  
- **C. kubectl apply configmap**  
- **D. kubectl set configmap**  
**Correct Answer:** **A. kubectl create configmap**  
**Explanation:** The **kubectl create configmap** command creates a ConfigMap, which stores non-sensitive configuration data for pods.  

---

### 22. Question:  
What is the primary purpose of the **etcd** component in Kubernetes?  
- **A. Scheduling workloads**  
- **B. Storing cluster state and configuration data**  
- **C. Exposing services to the internet**  
- **D. Managing container images**  
**Correct Answer:** **B. Storing cluster state and configuration data**  
**Explanation:** **etcd** is a distributed key-value store that holds all cluster data, including configurations and secrets.  

---

### 23. Question:  
How do you expose a deployment using a LoadBalancer service?  
- **A. kubectl expose deployment <deployment-name> --type=ClusterIP**  
- **B. kubectl expose deployment <deployment-name> --type=NodePort**  
- **C. kubectl expose deployment <deployment-name> --type=LoadBalancer**  
- **D. kubectl create service loadbalancer <deployment-name>**  
**Correct Answer:** **C. kubectl expose deployment <deployment-name> --type=LoadBalancer**  
**Explanation:** The **--type=LoadBalancer** option creates a service that exposes the deployment externally using a cloud provider's load balancer.  

---

### 24. Question:  
Which field in a Pod specification defines the container image to use?  
- **A. name**  
- **B. image**  
- **C. command**  
- **D. args**  
**Correct Answer:** **B. image**  
**Explanation:** The **image** field specifies the container image to be pulled and used for the pod.  

---

### 25. Question:  
What is the purpose of a ResourceQuota in Kubernetes?  
- **A. Limit CPU and memory for individual containers**  
- **B. Limit the number of objects or resources in a namespace**  
- **C. Restrict access to secrets**  
- **D. Specify network policies**  
**Correct Answer:** **B. Limit the number of objects or resources in a namespace**  
**Explanation:** ResourceQuotas control the resource usage and object counts in a namespace.  

---

### 26. Question:  
How does Kubernetes handle pod restarts when a node fails?  
- **A. kube-apiserver restarts the pods**  
- **B. kube-controller-manager reschedules pods to other nodes**  
- **C. kube-scheduler restarts the pods on the same node**  
- **D. kubelet recreates the pods**  
**Correct Answer:** **B. kube-controller-manager reschedules pods to other nodes**  
**Explanation:** The **kube-controller-manager** detects node failures and reschedules pods on available nodes.  

---

### 27. Question:  
Which Kubernetes feature provides rolling updates for applications?  
- **A. ReplicaSet**  
- **B. StatefulSet**  
- **C. Deployment**  
- **D. Pod**  
**Correct Answer:** **C. Deployment**  
**Explanation:** Deployments manage rolling updates by gradually updating pod replicas without downtime.  

---

### 28. Question:  
What is the default namespace used in Kubernetes if none is specified?  
- **A. kube-system**  
- **B. kube-default**  
- **C. default**  
- **D. public**  
**Correct Answer:** **C. default**  
**Explanation:** Kubernetes uses the **default** namespace when no namespace is explicitly provided.  

---

### 29. Question:  
How can you access a pod’s shell interactively?  
- **A. kubectl get pod shell <pod-name>**  
- **B. kubectl exec -it <pod-name> -- /bin/sh**  
- **C. kubectl shell <pod-name>**  
- **D. kubectl describe pod shell <pod-name>**  
**Correct Answer:** **B. kubectl exec -it <pod-name> -- /bin/sh**  
**Explanation:** The **kubectl exec** command allows interactive access to a pod’s container shell.  

---

### 30. Question:  
What does the **kubectl apply -f <file>** command do?  
- **A. Deletes Kubernetes resources specified in the file**  
- **B. Creates or updates resources defined in the file**  
- **C. Lists resources defined in the file**  
- **D. Exports the resource configuration**  
**Correct Answer:** **B. Creates or updates resources defined in the file**  
**Explanation:** The **kubectl apply** command applies changes to Kubernetes resources described in a YAML/JSON file.  

---

### 31. Question:  
Which object is used to manage persistent storage in Kubernetes?  
- **A. ConfigMap**  
- **B. PersistentVolume**  
- **C. Secret**  
- **D. Node**  
**Correct Answer:** **B. PersistentVolume**  
**Explanation:** PersistentVolumes (PVs) provide a way to manage persistent storage resources independently of the lifecycle of pods.  

---

### 32. Question:  
What is a Namespace used for in Kubernetes?  
- **A. Providing isolation for network traffic**  
- **B. Grouping related resources logically**  
- **C. Enabling persistent storage**  
- **D. Creating replicas of pods**  
**Correct Answer:** **B. Grouping related resources logically**  
**Explanation:** Namespaces provide a way to logically isolate resources, enabling multi-tenancy in a cluster.  

---

### 33. Question:  
Which command is used to drain a node for maintenance?  
- **A. kubectl cordon <node-name>**  
- **B. kubectl taint nodes <node-name> key=value:NoExecute**  
- **C. kubectl drain <node-name>**  
- **D. kubectl delete <node-name>**  
**Correct Answer:** **C. kubectl drain <node-name>**  
**Explanation:** The **kubectl drain** command safely evicts all pods from a node before maintenance.  

---

### 34. Question:  
What is the purpose of **kube-proxy** in Kubernetes?  
- **A. Scheduling pods to nodes**  
- **B. Managing API requests**  
- **C. Enabling network communication between services**  
- **D. Storing cluster state**  
**Correct Answer:** **C. Enabling network communication between services**  
**Explanation:** The **kube-proxy** component handles networking and load balancing for services within the cluster.  

---

### 35. Question:  
Which Kubernetes object defines a network policy for a pod?  
- **A. NetworkPolicy**  
- **B. Ingress**  
- **C. Service**  
- **D. PodSpec**  
**Correct Answer:** **A. NetworkPolicy**  
**Explanation:** A **NetworkPolicy** defines rules for allowing or blocking traffic to and from pods based on labels and selectors.  

---

### 36. Question:  
Which command is used to label a node in Kubernetes?  
- **A. kubectl add label <node-name> <key>=<value>**  
- **B. kubectl apply label <node-name> <key>=<value>**  
- **C. kubectl label nodes <node-name> <key>=<value>**  
- **D. kubectl update label <node-name> <key>=<value>**  
**Correct Answer:** **C. kubectl label nodes <node-name> <key>=<value>**  
**Explanation:** The **kubectl label nodes** command adds or updates labels for a node, which can be used for scheduling.  

---

### 37. Question:  
What does the **Readiness Probe** check in Kubernetes?  
- **A. Whether the application in a pod is ready to serve traffic**  
- **B. If the pod's containers are running**  
- **C. The pod's health over time**  
- **D. The container image size**  
**Correct Answer:** **A. Whether the application in a pod is ready to serve traffic**  
**Explanation:** Readiness probes determine if a pod should receive traffic, ensuring the application is fully initialized.  

---

### 38. Question:  
How do you view the events of a Kubernetes cluster?  
- **A. kubectl logs events**  
- **B. kubectl get events**  
- **C. kubectl describe events**  
- **D. kubectl cluster-info events**  
**Correct Answer:** **B. kubectl get events**  
**Explanation:** The **kubectl get events** command retrieves events related to resource changes or cluster operations.  

---

### 39. Question:  
What type of volume is created when using an **emptyDir** in a pod specification?  
- **A. Temporary storage bound to the container**  
- **B. Persistent storage shared across nodes**  
- **C. Network-attached storage**  
- **D. Storage for logs only**  
**Correct Answer:** **A. Temporary storage bound to the container**  
**Explanation:** **emptyDir** provides ephemeral storage, deleted when the pod is removed.  

---

### 40. Question:  
Which Kubernetes object allows you to define CPU and memory limits for a container?  
- **A. ResourceQuota**  
- **B. PodSpec**  
- **C. ResourceRequests**  
- **D. Limits and Requests**  
**Correct Answer:** **D. Limits and Requests**  
**Explanation:** Resource limits and requests define the minimum and maximum CPU/memory a container can use.  

---

### 41. Question:  
How does a **RollingUpdate** deployment strategy minimize downtime?  
- **A. Deletes all old pods before creating new ones**  
- **B. Gradually replaces old pods with new pods**  
- **C. Scales up new pods before deleting old ones**  
- **D. Recreates all pods simultaneously**  
**Correct Answer:** **B. Gradually replaces old pods with new pods**  
**Explanation:** Rolling updates incrementally replace old pods with new ones, ensuring availability during deployment.  

---

### 42. Question:  
What happens if a Pod in a Deployment is manually deleted?  
- **A. It is permanently removed**  
- **B. The Deployment recreates the Pod**  
- **C. The ReplicaSet removes the Deployment**  
- **D. The Deployment scales down automatically**  
**Correct Answer:** **B. The Deployment recreates the Pod**  
**Explanation:** A Deployment uses its ReplicaSet to maintain the desired number of pods.  

---

### 43. Question:  
What does the **kubectl rollout undo** command do?  
- **A. Scales down a deployment**  
- **B. Restores the previous deployment state**  
- **C. Deletes all replicas in a deployment**  
- **D. Forces pod recreation**  
**Correct Answer:** **B. Restores the previous deployment state**  
**Explanation:** The **rollout undo** command reverts to the previous revision of a deployment.  

---

### 44. Question:  
What is the purpose of a **HorizontalPodAutoscaler** (HPA)?  
- **A. Scale nodes based on CPU usage**  
- **B. Scale pods automatically based on CPU/memory metrics**  
- **C. Balance traffic across services**  
- **D. Automatically deploy replicas on demand**  
**Correct Answer:** **B. Scale pods automatically based on CPU/memory metrics**  
**Explanation:** HPA adjusts the number of pod replicas dynamically based on observed resource usage.  

---

### 45. Question:  
Which command displays the YAML definition of a Kubernetes resource?  
- **A. kubectl show resource <resource-name>**  
- **B. kubectl describe resource <resource-name>**  
- **C. kubectl get <resource-name> -o yaml**  
- **D. kubectl explain <resource-name>**  
**Correct Answer:** **C. kubectl get <resource-name> -o yaml**  
**Explanation:** The **-o yaml** flag outputs the resource in YAML format, useful for configuration insights.  

---

### 46. Question:  
What type of Kubernetes Service assigns an external IP to expose the service?  
- **A. ClusterIP**  
- **B. NodePort**  
- **C. LoadBalancer**  
- **D. ExternalName**  
**Correct Answer:** **C. LoadBalancer**  
**Explanation:** The LoadBalancer type integrates with cloud provider services to assign external IPs.  

---

### 47. Question:  
What is the default port on which the Kubernetes API server runs?  
- **A. 443**  
- **B. 8080**  
- **C. 6443**  
- **D. 2379**  
**Correct Answer:** **C. 6443**  
**Explanation:** The Kubernetes API server listens on port 6443 by default for secure communication.  

---

### 48. Question:  
What is the main function of a **NodePort** service?  
- **A. Expose the service on a high port range on all cluster nodes**  
- **B. Provide an internal DNS name for the service**  
- **C. Scale pods based on node capacity**  
- **D. Enable communication between namespaces**  
**Correct Answer:** **A. Expose the service on a high port range on all cluster nodes**  
**Explanation:** NodePort exposes a service on a specific port on every node, enabling external access.  

---

### 49. Question:  
Which object manages containerized workloads with persistent identities and storage?  
- **A. Deployment**  
- **B. ReplicaSet**  
- **C. StatefulSet**  
- **D. DaemonSet**  
**Correct Answer:** **C. StatefulSet**  
**Explanation:** StatefulSets are used for stateful applications requiring stable storage and network identities.  

---

### 50. Question:  
What is the **kubeadm** tool primarily used for?  
- **A. Managing container runtimes**  
- **B. Creating Kubernetes clusters**  
- **C. Deploying Kubernetes applications**  
- **D. Monitoring pods and nodes**  
**Correct Answer:** **B. Creating Kubernetes clusters**  
**Explanation:** **kubeadm** simplifies setting up a Kubernetes cluster by initializing and configuring control plane components.  

---

### 51. Question:  
Which Kubernetes object ensures that a pod runs on every node in the cluster?  
- **A. ReplicaSet**  
- **B. DaemonSet**  
- **C. StatefulSet**  
- **D. Deployment**  
**Correct Answer:** **B. DaemonSet**  
**Explanation:** A DaemonSet ensures that a copy of a pod runs on all (or specified) nodes in the cluster.  

---

### 52. Question:  
How can you check the current context of your Kubernetes cluster?  
- **A. kubectl get context**  
- **B. kubectl show context**  
- **C. kubectl config current-context**  
- **D. kubectl list contexts**  
**Correct Answer:** **C. kubectl config current-context**  
**Explanation:** The **kubectl config current-context** command displays the current context in use.  

---

### 53. Question:  
What is the role of the **Ingress** object in Kubernetes?  
- **A. To expose services on a specific node port**  
- **B. To manage traffic routing to services based on URL paths or hostnames**  
- **C. To scale pods horizontally**  
- **D. To manage persistent storage volumes**  
**Correct Answer:** **B. To manage traffic routing to services based on URL paths or hostnames**  
**Explanation:** The Ingress object allows HTTP and HTTPS routing to services, often with advanced path and hostname rules.  

---

### 54. Question:  
What does the **kubectl logs <pod-name>** command do?  
- **A. Fetches logs from the cluster control plane**  
- **B. Displays the logs of the specified container or pod**  
- **C. Retrieves the event history of the pod**  
- **D. Outputs the YAML definition of the pod**  
**Correct Answer:** **B. Displays the logs of the specified container or pod**  
**Explanation:** The **kubectl logs** command retrieves the logs from a running pod’s container.  

---

### 55. Question:  
What is the purpose of **Taints and Tolerations** in Kubernetes?  
- **A. To prevent pods from running on specific nodes**  
- **B. To prioritize certain nodes for pod scheduling**  
- **C. To control node affinity for pods**  
- **D. To limit resource usage per namespace**  
**Correct Answer:** **A. To prevent pods from running on specific nodes**  
**Explanation:** Taints prevent pods from being scheduled on nodes unless they have matching tolerations.  

---

### 56. Question:  
Which Kubernetes object provides declarative updates for Pods and ReplicaSets?  
- **A. StatefulSet**  
- **B. Deployment**  
- **C. Job**  
- **D. CronJob**  
**Correct Answer:** **B. Deployment**  
**Explanation:** Deployments manage declarative updates and rollbacks for pods and their ReplicaSets.  

---

### 57. Question:  
How do you roll back a Kubernetes Deployment to a specific revision?  
- **A. kubectl rollout revert deployment <deployment-name>**  
- **B. kubectl rollout undo deployment <deployment-name> --to-revision=<revision-number>**  
- **C. kubectl deployment rollback <revision-number>**  
- **D. kubectl undo rollout <deployment-name>**  
**Correct Answer:** **B. kubectl rollout undo deployment <deployment-name> --to-revision=<revision-number>**  
**Explanation:** The **--to-revision** flag allows rolling back a deployment to a specific revision.  

---

### 58. Question:  
What is the primary use of the **kubectl get nodes** command?  
- **A. View the status of all nodes in the cluster**  
- **B. Create a new node in the cluster**  
- **C. Update the labels of a node**  
- **D. Drain a node for maintenance**  
**Correct Answer:** **A. View the status of all nodes in the cluster**  
**Explanation:** The **kubectl get nodes** command lists all nodes and their status.  

---

### 59. Question:  
Which object is used to define custom DNS entries in Kubernetes?  
- **A. ConfigMap**  
- **B. Service**  
- **C. Endpoint**  
- **D. HostAliases**  
**Correct Answer:** **D. HostAliases**  
**Explanation:** **HostAliases** provide a way to add custom DNS entries directly into a pod's **/etc/hosts** file.  

---

### 60. Question:  
What does the **kubectl describe** command provide?  
- **A. Outputs the YAML definition of a resource**  
- **B. Detailed information and events related to a resource**  
- **C. Deletes a resource from the cluster**  
- **D. Restarts all pods in a deployment**  
**Correct Answer:** **B. Detailed information and events related to a resource**  
**Explanation:** The **kubectl describe** command provides a detailed view of resource specifications and events.  

---

### 61. Question:  
What is the **kube-scheduler** responsible for?  
- **A. Scheduling pods to nodes based on resource requirements**  
- **B. Scaling deployments horizontally**  
- **C. Managing cluster configurations**  
- **D. Networking between services**  
**Correct Answer:** **A. Scheduling pods to nodes based on resource requirements**  
**Explanation:** The **kube-scheduler** assigns pods to nodes, considering resource availability and constraints.  

---

### 62. Question:  
What is a **ClusterRole** used for in Kubernetes?  
- **A. To assign permissions to a user or group globally across the cluster**  
- **B. To manage resources within a specific namespace**  
- **C. To define network policies**  
- **D. To create persistent storage resources**  
**Correct Answer:** **A. To assign permissions to a user or group globally across the cluster**  
**Explanation:** **ClusterRole** provides permissions at the cluster level, unlike **Role**, which is namespace-scoped.  

---

### 63. Question:  
Which Kubernetes object is best suited for batch or finite-duration tasks?  
- **A. Deployment**  
- **B. StatefulSet**  
- **C. Job**  
- **D. ReplicaSet**  
**Correct Answer:** **C. Job**  
**Explanation:** A Job ensures that a specified number of pods run to completion, making it ideal for batch tasks.  

---

### 64. Question:  
What command is used to scale a deployment?  
- **A. kubectl apply scale <deployment-name> <replicas>**  
- **B. kubectl update deployment <deployment-name> --replicas=<number>**  
- **C. kubectl scale deployment <deployment-name> --replicas=<number>**  
- **D. kubectl set replicas <deployment-name> <number>**  
**Correct Answer:** **C. kubectl scale deployment <deployment-name> --replicas=<number>**  
**Explanation:** The **kubectl scale** command adjusts the number of replicas for a deployment.  

---

### 65. Question:  
What is the purpose of the **kubectl top** command?  
- **A. Monitor resource usage of nodes and pods**  
- **B. Display the YAML configuration of resources**  
- **C. Show the events of the cluster**  
- **D. Retrieve logs from pods**  
**Correct Answer:** **A. Monitor resource usage of nodes and pods**  
**Explanation:** The **kubectl top** command provides real-time CPU and memory usage metrics for pods and nodes.  

---

### 66. Question:  
Which of the following is a key difference between **StatefulSet** and **Deployment** in Kubernetes?  
- **A. StatefulSet provides persistent storage for pods**  
- **B. Deployment can only manage stateless applications**  
- **C. StatefulSet cannot scale horizontally**  
- **D. StatefulSet requires more nodes to work**  
**Correct Answer:** **A. StatefulSet provides persistent storage for pods**  
**Explanation:** StatefulSets maintain stateful applications and provide persistent storage and stable identities for pods.  

---

### 67. Question:  
How do you expose a Kubernetes service internally in the cluster without a public IP?  
- **A. By setting the service type to ClusterIP**  
- **B. By setting the service type to NodePort**  
- **C. By using LoadBalancer type**  
- **D. By adding a static IP to the service**  
**Correct Answer:** **A. By setting the service type to ClusterIP**  
**Explanation:** ClusterIP exposes a service within the cluster, making it inaccessible externally.  

---

### 68. Question:  
What Kubernetes object is used to manage the configuration of pods and their environments?  
- **A. ConfigMap**  
- **B. Secret**  
- **C. Volume**  
- **D. Deployment**  
**Correct Answer:** **A. ConfigMap**  
**Explanation:** ConfigMaps store configuration data that can be consumed by pods as environment variables or mounted volumes.  

---

### 69. Question:  
What command would you use to view the logs of a specific container in a multi-container pod?  
- **A. kubectl logs <pod-name> --container=<container-name>**  
- **B. kubectl logs <container-name> <pod-name>**  
- **C. kubectl logs <pod-name> -c <container-name>**  
- **D. kubectl container logs <pod-name> <container-name>**  
**Correct Answer:** **C. kubectl logs <pod-name> -c <container-name>**  
**Explanation:** The **-c** flag specifies the container within a pod when there are multiple containers.  

---

### 70. Question:  
What is the role of the **kube-apiserver** in a Kubernetes cluster?  
- **A. To schedule pods onto nodes**  
- **B. To manage the control plane and expose the API**  
- **C. To handle networking between pods**  
- **D. To manage persistent storage**  
**Correct Answer:** **B. To manage the control plane and expose the API**  
**Explanation:** The **kube-apiserver** serves as the API server that handles REST requests for the cluster.  

---

### 71. Question:  
What is the default namespace for objects in Kubernetes if no namespace is specified?  
- **A. default**  
- **B. kube-system**  
- **C. kube-public**  
- **D. production**  
**Correct Answer:** **A. default**  
**Explanation:** The default namespace is used for objects when no other namespace is specified.  

---

### 72. Question:  
Which of the following is used for self-healing in Kubernetes to replace failed pods?  
- **A. ReplicaSet**  
- **B. StatefulSet**  
- **C. Deployment**  
- **D. DaemonSet**  
**Correct Answer:** **A. ReplicaSet**  
**Explanation:** A ReplicaSet ensures that the specified number of pod replicas are always running.  

---

### 73. Question:  
Which Kubernetes object is used to define network policies for pods?  
- **A. PodSecurityPolicy**  
- **B. NetworkPolicy**  
- **C. Ingress**  
- **D. Egress**  
**Correct Answer:** **B. NetworkPolicy**  
**Explanation:** NetworkPolicies control the communication between pods and services within a cluster, providing security.  

---

### 74. Question:  
What does a **PodDisruptionBudget** define?  
- **A. The number of disruptions allowed during node maintenance**  
- **B. The number of pod replicas required during a scaling operation**  
- **C. The time limit before a pod is terminated**  
- **D. The minimum number of pods to be available during voluntary disruptions**  
**Correct Answer:** **D. The minimum number of pods to be available during voluntary disruptions**  
**Explanation:** PodDisruptionBudgets prevent too many pods from being taken down simultaneously, maintaining availability.  

---

### 75. Question:  
Which of the following is the correct way to update the image used by a Deployment in Kubernetes?  
- **A. kubectl set image deployment/<deployment-name> <container-name>=<image-name>**  
- **B. kubectl update image <deployment-name> <container-name>=<image-name>**  
- **C. kubectl edit deployment <deployment-name>**  
- **D. kubectl patch deployment <deployment-name> --image <container-name>=<image-name>**  
**Correct Answer:** **A. kubectl set image deployment/<deployment-name> <container-name>=<image-name>**  
**Explanation:** The **kubectl set image** command allows you to update the image of a container in a deployment.  

---

### 76. Question:  
What is the purpose of the **kubectl drain** command in Kubernetes?  
- **A. To remove a node from the cluster permanently**  
- **B. To gracefully terminate pods on a node before maintenance**  
- **C. To reschedule pods on other nodes**  
- **D. To remove all services from the node**  
**Correct Answer:** **B. To gracefully terminate pods on a node before maintenance**  
**Explanation:** The **kubectl drain** command safely evicts pods from a node in preparation for maintenance.  

---

### 77. Question:  
What Kubernetes object is used to automate the management of scheduled tasks or cron jobs?  
- **A. Pod**  
- **B. CronJob**  
- **C. Job**  
- **D. StatefulSet**  
**Correct Answer:** **B. CronJob**  
**Explanation:** CronJobs manage time-based scheduled tasks within Kubernetes.  

---

### 78. Question:  
What command would you use to create a Kubernetes cluster?  
- **A. kubectl cluster create**  
- **B. kubeadm init**  
- **C. kubectl init cluster**  
- **D. kubeadm create cluster**  
**Correct Answer:** **B. kubeadm init**  
**Explanation:** **kubeadm init** is used to set up a Kubernetes control plane and initialize the cluster.  

---

### 79. Question:  
What is the primary function of the **kube-proxy** in Kubernetes?  
- **A. To route traffic between containers within a pod**  
- **B. To provide network policies for pods**  
- **C. To handle load balancing and routing for services**  
- **D. To manage ingress traffic to the cluster**  
**Correct Answer:** **C. To handle load balancing and routing for services**  
**Explanation:** **kube-proxy** manages network traffic and load balancing for services within the cluster.  

---

### 80. Question:  
What is the purpose of a **PersistentVolumeClaim** (PVC) in Kubernetes?  
- **A. To create a new pod with persistent storage**  
- **B. To request storage resources dynamically from a **PersistentVolume****  
- **C. To manage a set of storage devices**  
- **D. To attach a disk to a specific pod**  
**Correct Answer:** **B. To request storage resources dynamically from a **PersistentVolume****  
**Explanation:** A PVC requests specific storage resources from a **PersistentVolume**, which can be dynamically provisioned.  

---

### 81. Question:  
Which of the following commands can be used to get detailed information about a specific pod in a Kubernetes cluster?  
- **A. kubectl describe pod <pod-name>**  
- **B. kubectl inspect pod <pod-name>**  
- **C. kubectl get pod <pod-name>**  
- **D. kubectl pod info <pod-name>**  
**Correct Answer:** **A. kubectl describe pod <pod-name>**  
**Explanation:** The **kubectl describe pod** command provides detailed information about the pod, including its configuration, events, and status.  

---

### 82. Question:  
How can you perform a rolling update in Kubernetes for a deployment?  
- **A. kubectl rollout update <deployment-name>**  
- **B. kubectl scale <deployment-name>**  
- **C. kubectl set image <deployment-name> <container-name>=<new-image>**  
- **D. kubectl update deployment <deployment-name> --image <new-image>**  
**Correct Answer:** **C. kubectl set image <deployment-name> <container-name>=<new-image>**  
**Explanation:** A rolling update in Kubernetes can be performed by updating the deployment's image, which automatically updates the pods in a controlled manner.  

---

### 83. Question:  
What is the primary use of a Kubernetes **ConfigMap**?  
- **A. To store and manage sensitive information**  
- **B. To provide configuration data to applications**  
- **C. To manage persistent storage for pods**  
- **D. To scale a deployment**  
**Correct Answer:** **B. To provide configuration data to applications**  
**Explanation:** A **ConfigMap** is used to store non-sensitive configuration data that can be consumed by containers in pods.  

---

### 84. Question:  
Which object would you use to store sensitive information, such as passwords, in Kubernetes?  
- **A. ConfigMap**  
- **B. Secret**  
- **C. Volume**  
- **D. PersistentVolumeClaim**  
**Correct Answer:** **B. Secret**  
**Explanation:** **Secrets** store sensitive data like passwords and API keys in Kubernetes, ensuring the data is encrypted.  

---

### 85. Question:  
Which of the following is a key difference between a **Deployment** and a **StatefulSet**?  
- **A. StatefulSets maintain stable, unique network identities for pods**  
- **B. Deployments provide persistent storage for pods**  
- **C. StatefulSets cannot scale horizontally**  
- **D. Deployments manage stateful applications**  
**Correct Answer:** **A. StatefulSets maintain stable, unique network identities for pods**  
**Explanation:** StatefulSets are used for stateful applications and provide stable, unique identities and persistent storage.  

---

### 86. Question:  
Which command can be used to check the health status of the Kubernetes nodes?  
- **A. kubectl node health**  
- **B. kubectl get nodes**  
- **C. kubectl describe node <node-name>**  
- **D. kubectl check nodes**  
**Correct Answer:** **B. kubectl get nodes**  
**Explanation:** The **kubectl get nodes** command lists the nodes in the cluster and their health status, including Ready or NotReady.  

---

### 87. Question:  
What is the role of the **kubelet** in a Kubernetes cluster?  
- **A. It runs on every node and ensures that containers are running in pods**  
- **B. It schedules pods onto nodes**  
- **C. It provides networking between pods**  
- **D. It manages the control plane**  
**Correct Answer:** **A. It runs on every node and ensures that containers are running in pods**  
**Explanation:** The **kubelet** is an agent that runs on each node and makes sure the containers in the pods are running as expected.  

---

### 88. Question:  
What is the purpose of the **kubectl apply** command?  
- **A. To apply the configuration changes from a local YAML file to the cluster**  
- **B. To list the available resources in the cluster**  
- **C. To view the status of a resource in the cluster**  
- **D. To delete a resource in the cluster**  
**Correct Answer:** **A. To apply the configuration changes from a local YAML file to the cluster**  
**Explanation:** The **kubectl apply** command applies a configuration file to the cluster, either creating or updating resources based on the file.  

---

### 89. Question:  
What is the main advantage of using the **HorizontalPodAutoscaler** in Kubernetes?  
- **A. It automatically scales pods based on CPU usage or custom metrics**  
- **B. It ensures pods are always evenly distributed across nodes**  
- **C. It defines network policies for pods**  
- **D. It enables stateful applications to scale horizontally**  
**Correct Answer:** **A. It automatically scales pods based on CPU usage or custom metrics**  
**Explanation:** The **HorizontalPodAutoscaler** automatically adjusts the number of pod replicas based on resource utilization such as CPU and memory.  

---

### 90. Question:  
What command would you use to delete a specific pod in Kubernetes?  
- **A. kubectl delete pod <pod-name>**  
- **B. kubectl remove pod <pod-name>**  
- **C. kubectl stop pod <pod-name>**  
- **D. kubectl terminate pod <pod-name>**  
**Correct Answer:** **A. kubectl delete pod <pod-name>**  
**Explanation:** The **kubectl delete pod** command deletes a pod from the cluster. The pod will be recreated if it's managed by a higher-level controller like a Deployment.  

---

### 91. Question:  
What is the purpose of the **kube-controller-manager** in Kubernetes?  
- **A. To manage the lifecycle of Kubernetes resources and ensure the cluster state matches the desired state**  
- **B. To control the scheduling of pods**  
- **C. To provide networking services for pods**  
- **D. To monitor the health of nodes and pods**  
**Correct Answer:** **A. To manage the lifecycle of Kubernetes resources and ensure the cluster state matches the desired state**  
**Explanation:** The **kube-controller-manager** runs controllers that maintain the desired state of the cluster, such as creating, scaling, and deleting resources.  

---

### 92. Question:  
Which of the following is NOT a valid type for a Kubernetes **Service**?  
- **A. ClusterIP**  
- **B. NodePort**  
- **C. LoadBalancer**  
- **D. StatefulService**  
**Correct Answer:** **D. StatefulService**  
**Explanation:** Kubernetes supports **ClusterIP**, **NodePort**, and **LoadBalancer** as valid service types, but **StatefulService** is not a recognized type.  

---

### 93. Question:  
What is the **kubectl port-forward** command used for?  
- **A. Forward ports to a pod for local testing**  
- **B. Forward traffic between services**  
- **C. Forward a node’s traffic to a pod**  
- **D. Forward logs to an external system**  
**Correct Answer:** **A. Forward ports to a pod for local testing**  
**Explanation:** The **kubectl port-forward** command allows you to forward a port from a local machine to a pod in the cluster for debugging or testing.  

---

### 94. Question:  
What is the default scheduler used in Kubernetes to assign pods to nodes?  
- **A. DefaultScheduler**  
- **B. kube-scheduler**  
- **C. pod-scheduler**  
- **D. node-scheduler**  
**Correct Answer:** **B. kube-scheduler**  
**Explanation:** The **kube-scheduler** is the default component responsible for scheduling pods to nodes based on available resources.  

---

### 95. Question:  
How can you ensure that a pod in Kubernetes is scheduled to a specific node?  
- **A. By using node affinity or node selectors**  
- **B. By using pod labels**  
- **C. By using the **kubectl schedule** command**  
- **D. By manually specifying the node in the pod specification**  
**Correct Answer:** **A. By using node affinity or node selectors**  
**Explanation:** Node affinity and node selectors allow you to constrain which nodes your pod can be scheduled on based on labels or other criteria.  

---

### 96. Question:  
Which Kubernetes object is used to ensure that a specific number of pods are running at all times, even during maintenance?  
- **A. DaemonSet**  
- **B. Deployment**  
- **C. ReplicaSet**  
- **D. StatefulSet**  
**Correct Answer:** **C. ReplicaSet**  
**Explanation:** A **ReplicaSet** ensures that a specified number of identical pods are running at any time, ensuring fault tolerance.  

---

### 97. Question:  
What type of Kubernetes resource is used to expose a service externally to the internet?  
- **A. NodePort**  
- **B. ClusterIP**  
- **C. LoadBalancer**  
- **D. Ingress**  
**Correct Answer:** **C. LoadBalancer**  
**Explanation:** A **LoadBalancer** service type is used to expose a service externally, providing a stable IP address and routing traffic.  

---

### 98. Question:  
What is the main function of a **DaemonSet** in Kubernetes?  
- **A. To ensure a specific pod is running on every node**  
- **B. To scale the number of pods in a deployment**  
- **C. To manage the state of persistent volumes**  
- **D. To handle networking for services**  
**Correct Answer:** **A. To ensure a specific pod is running on every node**  
**Explanation:** A **DaemonSet** ensures that a copy of a specific pod is running on every node or a subset of nodes.  

---

### 99. Question:  
What is the role of the **kube-scheduler** in Kubernetes?  
- **A. To assign pods to available nodes based on resource requirements**  
- **B. To expose services to the internet**  
- **C. To monitor and log pod events**  
- **D. To manage persistent volumes for pods**  
**Correct Answer:** **A. To assign pods to available nodes based on resource requirements**  
**Explanation:** The **kube-scheduler** is responsible for scheduling pods onto appropriate nodes based on resource availability and other constraints.  

---

### 100. Question:  
What is the purpose of **PodSecurityPolicy** (PSP) in Kubernetes?  
- **A. To manage pod security and enforce security contexts**  
- **B. To provide encryption for sensitive data**  
- **C. To automatically patch vulnerabilities in pods**  
- **D. To monitor the health of pods**  
**Correct Answer:** **A. To manage pod security and enforce security contexts**  
**Explanation:** **PodSecurityPolicy** defines policies to control the security configuration of pods, such as permissions and privileges.  

---

### 101. Question:  
How can you perform a rollback to a previous version of a deployment in Kubernetes?  
- **A. kubectl revert deployment <deployment-name>**  
- **B. kubectl rollout undo deployment <deployment-name>**  
- **C. kubectl rollback deployment <deployment-name>**  
- **D. kubectl revert version <deployment-name>**  
**Correct Answer:** **B. kubectl rollout undo deployment <deployment-name>**  
**Explanation:** The **kubectl rollout undo** command allows you to rollback a deployment to its previous stable version.  

---

### 102. Question:  
Which of the following is NOT a valid state for a pod in Kubernetes?  
- **A. Pending**  
- **B. Running**  
- **C. Terminated**  
- **D. Stopped**  
**Correct Answer:** **D. Stopped**  
**Explanation:** Pods have states like Pending, Running, and Terminated, but **Stopped** is not a valid pod state.  

---

### 103. Question:  
What is the primary purpose of **kubectl get events**?  
- **A. To view logs from the Kubernetes control plane**  
- **B. To view recent events in the cluster**  
- **C. To show the status of all services in the cluster**  
- **D. To get detailed resource usage statistics**  
**Correct Answer:** **B. To view recent events in the cluster**  
**Explanation:** **kubectl get events** shows a list of recent events in the cluster, which can be useful for troubleshooting issues.  

---

### 104. Question:  
What is the default value for the **restartPolicy** field in a Kubernetes pod specification?  
- **A. Always**  
- **B. OnFailure**  
- **C. Never**  
- **D. OnDemand**  
**Correct Answer:** **A. Always**  
**Explanation:** The default **restartPolicy** for pods in Kubernetes is **Always**, meaning the pod will be restarted automatically if it fails.  

---

### 105. Question:  
Which of the following is the correct syntax for setting a label on a pod in Kubernetes?  
- **A. kubectl label pod <pod-name> key=value**  
- **B. kubectl add label pod <pod-name> key=value**  
- **C. kubectl set label pod <pod-name> key=value**  
- **D. kubectl apply label pod <pod-name> key=value**  
**Correct Answer:** **A. kubectl label pod <pod-name> key=value**  
**Explanation:** The **kubectl label** command is used to add or modify labels on Kubernetes resources like pods.  

---

### 106. Question:  
What is the use of a Kubernetes **Ingress** resource?  
- **A. To expose services to the internet with URL routing and SSL termination**  
- **B. To monitor the traffic to a service**  
- **C. To define network policies for services**  
- **D. To manage load balancing across nodes**  
**Correct Answer:** **A. To expose services to the internet with URL routing and SSL termination**  
**Explanation:** Ingress exposes HTTP and HTTPS routes from outside the cluster to services, providing features like SSL termination and URL path-based routing.  

---

### 107. Question:  
Which of the following is used to set resource limits for a container in Kubernetes?  
- **A. ResourceQuota**  
- **B. ResourceLimit**  
- **C. ResourceRequest**  
- **D. Limits**  
**Correct Answer:** **A. ResourceQuota**  
**Explanation:** **ResourceQuota** is used to set limits on the amount of resources that can be consumed by a namespace, while individual containers can use **requests** and **limits** in their resource definitions.  

---

### 108. Question:  
Which component in the Kubernetes control plane manages the API and serves it to clients?  
- **A. kube-controller-manager**  
- **B. kube-scheduler**  
- **C. kube-apiserver**  
- **D. etcd**  
**Correct Answer:** **C. kube-apiserver**  
**Explanation:** The **kube-apiserver** serves the Kubernetes API to clients and is the main entry point for interacting with the cluster.  

---

### 109. Question:  
Which command can be used to scale a deployment in Kubernetes?  
- **A. kubectl scale deployment <deployment-name> --replicas=<num-replicas>**  
- **B. kubectl set replicas <deployment-name> <num-replicas>**  
- **C. kubectl update deployment <deployment-name> --replicas=<num-replicas>**  
- **D. kubectl autoscale deployment <deployment-name> --replicas=<num-replicas>**  
**Correct Answer:** **A. kubectl scale deployment <deployment-name> --replicas=<num-replicas>**  
**Explanation:** The **kubectl scale** command allows you to change the number of replicas in a deployment to scale it up or down.  

---

### 110. Question:  
What is the purpose of a **PodAffinity** in Kubernetes?  
- **A. To ensure that pods are scheduled together on the same node**  
- **B. To prevent certain pods from being scheduled on specific nodes**  
- **C. To allow pods to run only in specific namespaces**  
- **D. To set pod labels for organizing pods**  
**Correct Answer:** **A. To ensure that pods are scheduled together on the same node**  
**Explanation:** **PodAffinity** allows you to influence scheduling decisions to ensure that certain pods are co-located on the same node based on labels.  

---

### 111. Question:  
What is the purpose of the **kubectl logs** command?  
- **A. To view the logs from a Kubernetes resource**  
- **B. To get detailed resource usage statistics**  
- **C. To show the event history of a resource**  
- **D. To view the current configuration of a resource**  
**Correct Answer:** **A. To view the logs from a Kubernetes resource**  
**Explanation:** The **kubectl logs** command is used to view the logs of a container in a pod, helping in troubleshooting and debugging.  

---

### 112. Question:  
Which of the following Kubernetes objects can be used to mount a persistent volume to a pod?  
- **A. PersistentVolumeClaim**  
- **B. StatefulSet**  
- **C. ReplicaSet**  
- **D. Deployment**  
**Correct Answer:** **A. PersistentVolumeClaim**  
**Explanation:** A **PersistentVolumeClaim** (PVC) is used by a pod to request storage resources from a **PersistentVolume**.  

---

### 113. Question:  
What type of service would you create to expose a pod on a specific port across all nodes in the cluster?  
- **A. ClusterIP**  
- **B. NodePort**  
- **C. LoadBalancer**  
- **D. Ingress**  
**Correct Answer:** **B. NodePort**  
**Explanation:** A **NodePort** service exposes the service on a static port across all nodes in the cluster, making it accessible externally via the node's IP.  

---

### 114. Question:  
Which command would you use to view the status of all the pods in a specific namespace?  
- **A. kubectl get pods --namespace=<namespace>**  
- **B. kubectl describe pods --namespace=<namespace>**  
- **C. kubectl pods --namespace=<namespace>**  
- **D. kubectl list pods --namespace=<namespace>**  
**Correct Answer:** **A. kubectl get pods --namespace=<namespace>**  
**Explanation:** The **kubectl get pods --namespace=<namespace>** command lists all the pods in the specified namespace.  

---

### 115. Question:  
Which of the following Kubernetes components stores all cluster data, including configurations and state?  
- **A. kube-apiserver**  
- **B. etcd**  
- **C. kube-controller-manager**  
- **D. kube-scheduler**  
**Correct Answer:** **B. etcd**  
**Explanation:** **etcd** is a distributed key-value store that holds all the cluster data, including configurations and the state of all resources in the cluster.  

---

### 116. Question:  
Which command would you use to update the image of a running deployment in Kubernetes?  
- **A. kubectl set image deployment <deployment-name> <container-name>=<new-image>**  
- **B. kubectl update deployment <deployment-name> --image <new-image>**  
- **C. kubectl deploy update <deployment-name> --image <new-image>**  
- **D. kubectl update container <container-name> --image <new-image>**  
**Correct Answer:** **A. kubectl set image deployment <deployment-name> <container-name>=<new-image>**  
**Explanation:** The **kubectl set image** command is used to update the image of a container in a deployment. This triggers a rolling update to the pods managed by the deployment.  

---

### 117. Question:  
Which Kubernetes object is used to ensure that a pod runs on every node in the cluster?  
- **A. DaemonSet**  
- **B. Deployment**  
- **C. ReplicaSet**  
- **D. StatefulSet**  
**Correct Answer:** **A. DaemonSet**  
**Explanation:** A **DaemonSet** ensures that a specific pod is running on every node in the cluster, which is useful for cluster-wide monitoring or logging.  

---

### 118. Question:  
What is the difference between a **ReplicaSet** and a **Deployment** in Kubernetes?  
- **A. A Deployment provides declarative updates, while a ReplicaSet ensures the desired number of replicas**  
- **B. A ReplicaSet manages stateful applications, while a Deployment is for stateless applications**  
- **C. A Deployment does not allow scaling, while a ReplicaSet does**  
- **D. A Deployment is used only for rolling updates, while a ReplicaSet cannot be updated**  
**Correct Answer:** **A. A Deployment provides declarative updates, while a ReplicaSet ensures the desired number of replicas**  
**Explanation:** A **Deployment** is a higher-level object that manages **ReplicaSets** and provides features like rolling updates, while a **ReplicaSet** ensures that a specific number of replicas of a pod are running at any time.  

---

### 119. Question:  
Which Kubernetes object would you use to store configuration data that can be consumed by multiple pods?  
- **A. Secret**  
- **B. ConfigMap**  
- **C. PersistentVolumeClaim**  
- **D. Deployment**  
**Correct Answer:** **B. ConfigMap**  
**Explanation:** **ConfigMap** is used to store non-sensitive configuration data that can be consumed by multiple pods within the cluster.  

---

### 120. Question:  
What is the purpose of **HorizontalPodAutoscaler** in Kubernetes?  
- **A. To automatically scale the number of pods based on resource usage like CPU or memory**  
- **B. To increase the number of nodes in the cluster based on workload**  
- **C. To balance the load between pods in the same deployment**  
- **D. To adjust the resource limits for each container in a pod**  
**Correct Answer:** **A. To automatically scale the number of pods based on resource usage like CPU or memory**  
**Explanation:** The **HorizontalPodAutoscaler** automatically adjusts the number of pod replicas in a deployment based on metrics like CPU or memory usage.  

---

### 121. Question:  
Which of the following commands can be used to apply a configuration file to create or update a resource in Kubernetes?  
- **A. kubectl create -f <file-name>**  
- **B. kubectl apply -f <file-name>**  
- **C. kubectl update -f <file-name>**  
- **D. kubectl set -f <file-name>**  
**Correct Answer:** **B. kubectl apply -f <file-name>**  
**Explanation:** The **kubectl apply -f** command is used to apply a configuration file to create or update a resource in the cluster.  

---

### 122. Question:  
Which type of service in Kubernetes is typically used when you need an external load balancer to route traffic to your services?  
- **A. ClusterIP**  
- **B. NodePort**  
- **C. LoadBalancer**  
- **D. Ingress**  
**Correct Answer:** **C. LoadBalancer**  
**Explanation:** A **LoadBalancer** service type provisions an external load balancer to route traffic to your service, typically used in cloud environments.  

---

### 123. Question:  
Which of the following commands will show detailed information about the nodes in your Kubernetes cluster?  
- **A. kubectl describe node**  
- **B. kubectl show node**  
- **C. kubectl get nodes -o wide**  
- **D. kubectl list nodes**  
**Correct Answer:** **A. kubectl describe node**  
**Explanation:** The **kubectl describe node** command shows detailed information about the nodes, including resource usage and status.  

---

### 124. Question:  
What is the main purpose of **PodSecurityPolicies** in Kubernetes?  
- **A. To control the security settings of pods, such as privileged access and host networking**  
- **B. To provide encryption for sensitive data**  
- **C. To monitor the health of pods**  
- **D. To manage user authentication and authorization**  
**Correct Answer:** **A. To control the security settings of pods, such as privileged access and host networking**  
**Explanation:** **PodSecurityPolicies** are used to control the security aspects of pods, such as whether they can run as privileged or access the host network.  

---

### 125. Question:  
What is the function of **kube-proxy** in Kubernetes?  
- **A. It manages network traffic between services in the cluster**  
- **B. It monitors pod health**  
- **C. It schedules pods to nodes**  
- **D. It controls the lifecycle of resources**  
**Correct Answer:** **A. It manages network traffic between services in the cluster**  
**Explanation:** **kube-proxy** manages network traffic to ensure that services are reachable within the cluster, handling tasks like load balancing and routing.  

---

### 126. Question:  
Which Kubernetes resource would you use to automate the management of a set of related pods that require persistent storage?  
- **A. StatefulSet**  
- **B. Deployment**  
- **C. ReplicaSet**  
- **D. DaemonSet**  
**Correct Answer:** **A. StatefulSet**  
**Explanation:** **StatefulSet** is used for managing stateful applications that require persistent storage, ensuring stable, unique network identifiers and persistent storage for each pod.  

---

### 127. Question:  
Which Kubernetes feature helps you to limit the resources that a pod can use?  
- **A. ResourceRequests and ResourceLimits**  
- **B. ResourceQuota**  
- **C. VerticalPodAutoscaler**  
- **D. PodSecurityPolicy**  
**Correct Answer:** **A. ResourceRequests and ResourceLimits**  
**Explanation:** **ResourceRequests** and **ResourceLimits** allow you to define the minimum and maximum resources (CPU, memory) a pod can request or consume, respectively.  

---

### 128. Question:  
What is the main difference between a **Deployment** and a **StatefulSet** in Kubernetes?  
- **A. A Deployment is for stateless applications, while a StatefulSet is for stateful applications**  
- **B. A Deployment can be used only for single pods, while a StatefulSet can manage multiple pods**  
- **C. A Deployment supports persistent storage, while a StatefulSet does not**  
- **D. A Deployment guarantees the order of pod creation, while a StatefulSet does not**  
**Correct Answer:** **A. A Deployment is for stateless applications, while a StatefulSet is for stateful applications**  
**Explanation:** A **Deployment** is for stateless applications where pod replicas can be replaced without affecting the service, while a **StatefulSet** is for managing stateful applications, preserving the identity and storage across pod restarts.  

---

### 129. Question:  
What is a **PodDisruptionBudget** used for in Kubernetes?  
- **A. To ensure that a certain number of pods in a deployment remain available during voluntary disruptions**  
- **B. To limit the number of pods that can be disrupted by non-voluntary events**  
- **C. To scale a pod based on its resource consumption**  
- **D. To enforce pod termination during maintenance windows**  
**Correct Answer:** **A. To ensure that a certain number of pods in a deployment remain available during voluntary disruptions**  
**Explanation:** A **PodDisruptionBudget** helps you specify the minimum number of pods that should be available during voluntary disruptions like node upgrades or pod deletions.  

---

### 130. Question:  
Which Kubernetes object would you use to schedule pods with specific constraints on node selection?  
- **A. NodeSelector**  
- **B. Affinity**  
- **C. Taints and Tolerations**  
- **D. All of the above**  
**Correct Answer:** **D. All of the above**  
**Explanation:** You can use **NodeSelector**, **Affinity**, or **Taints and Tolerations** to schedule pods with specific constraints on where they should run within the cluster.  

---

### 131. Question:  
What does the **kubectl rollout status** command do?  
- **A. It shows the status of a deployment or replica set during updates**  
- **B. It updates the resource version of a deployment**  
- **C. It shows the logs of a deployment’s rollout**  
- **D. It rolls back a deployment to its previous version**  
**Correct Answer:** **A. It shows the status of a deployment or replica set during updates**  
**Explanation:** The **kubectl rollout status** command shows the current state of the rollout of a deployment or replica set, helping to monitor the progress during updates.  

---

### 132. Question:  
What is the function of the **kube-controller-manager** in Kubernetes?  
- **A. It manages controllers that regulate the state of the cluster, like ReplicaSets and Deployments**  
- **B. It serves the API to clients**  
- **C. It runs the scheduler to place pods on nodes**  
- **D. It provides access control and policies**  
**Correct Answer:** **A. It manages controllers that regulate the state of the cluster, like ReplicaSets and Deployments**  
**Explanation:** The **kube-controller-manager** runs controllers that monitor the state of the cluster and perform actions to ensure that the desired state matches the actual state.  

---

### 133. Question:  
Which command can be used to list all the namespaces in a Kubernetes cluster?  
- **A. kubectl list namespaces**  
- **B. kubectl get namespaces**  
- **C. kubectl describe namespaces**  
- **D. kubectl show namespaces**  
**Correct Answer:** **B. kubectl get namespaces**  
**Explanation:** The **kubectl get namespaces** command lists all the namespaces in the cluster. You can use **kubectl get ns** as a shorthand.  

---

### 134. Question:  
What is the purpose of **kubectl exec** command in Kubernetes?  
- **A. To execute a command inside a container of a pod**  
- **B. To apply a configuration file to a resource**  
- **C. To scale the number of replicas of a deployment**  
- **D. To show logs from a container**  
**Correct Answer:** **A. To execute a command inside a container of a pod**  
**Explanation:** The **kubectl exec** command is used to run commands inside a running container within a pod, useful for debugging or interacting with the pod.  

---

### 135. Question:  
What is a **ConfigMap** used for in Kubernetes?  
- **A. To manage non-sensitive configuration data as key-value pairs**  
- **B. To store sensitive configuration data**  
- **C. To define resource requests and limits for a pod**  
- **D. To store data for persistent volumes**  
**Correct Answer:** **A. To manage non-sensitive configuration data as key-value pairs**  
**Explanation:** A **ConfigMap** is used to store non-sensitive configuration data, such as environment variables, in key-value pairs that can be consumed by pods or other resources.  

---

### 136. Question:  
What is the role of **kube-scheduler** in Kubernetes?  
- **A. To schedule pods onto nodes based on resource requirements and constraints**  
- **B. To manage the state of deployments**  
- **C. To monitor resource consumption in the cluster**  
- **D. To create new nodes as needed**  
**Correct Answer:** **A. To schedule pods onto nodes based on resource requirements and constraints**  
**Explanation:** The **kube-scheduler** is responsible for determining which node a pod should run on based on resource requests, constraints, and other factors like affinity or taints.  

---

### 137. Question:  
Which type of Kubernetes service is used to expose an application externally using HTTP and HTTPS routes?  
- **A. ClusterIP**  
- **B. NodePort**  
- **C. LoadBalancer**  
- **D. Ingress**  
**Correct Answer:** **D. Ingress**  
**Explanation:** **Ingress** allows HTTP and HTTPS traffic to be routed to services in the cluster based on hostnames and URL paths, often used for exposing applications externally.  

---

### 138. Question:  
Which of the following is a key difference between **Kubernetes Secrets** and **ConfigMaps**?  
- **A. Secrets are used to store sensitive data, while ConfigMaps store non-sensitive data**  
- **B. Secrets are used only for authentication, while ConfigMaps are used for configuration files**  
- **C. Secrets can only be stored in the cluster, while ConfigMaps can be stored in external sources**  
- **D. Secrets can be directly referenced by services, while ConfigMaps cannot**  
**Correct Answer:** **A. Secrets are used to store sensitive data, while ConfigMaps store non-sensitive data**  
**Explanation:** **Secrets** are used to store sensitive data, such as passwords or tokens, whereas **ConfigMaps** store non-sensitive configuration data.  

---

### 139. Question:  
How can you access a pod’s terminal directly without using **kubectl exec**?  
- **A. By port-forwarding a port to your local machine**  
- **B. By using the **kubectl attach** command**  
- **C. By accessing the pod’s logs**  
- **D. By accessing the pod through the Kubernetes dashboard**  
**Correct Answer:** **B. By using the **kubectl attach** command**  
**Explanation:** The **kubectl attach** command allows you to attach to a running container’s terminal for interactive use.  

---

### 140. Question:  
What is the purpose of **VerticalPodAutoscaler** in Kubernetes?  
- **A. To automatically adjust resource requests and limits for pods based on usage**  
- **B. To automatically scale the number of pods in a deployment based on load**  
- **C. To scale the size of a pod vertically by adding or removing containers**  
- **D. To create and manage persistent volumes**  
**Correct Answer:** **A. To automatically adjust resource requests and limits for pods based on usage**  
**Explanation:** **VerticalPodAutoscaler** automatically adjusts the CPU and memory resource requests and limits of containers in a pod based on observed usage.  

---

### 141. Question:  
Which Kubernetes object ensures that a specific number of identical pods are running at any given time, and can automatically create or delete pods to meet this requirement?  
- **A. Deployment**  
- **B. StatefulSet**  
- **C. ReplicaSet**  
- **D. DaemonSet**  
**Correct Answer:** **C. ReplicaSet**  
**Explanation:** A **ReplicaSet** ensures that a specified number of identical pods are running and takes care of creating and deleting pods to maintain that number. 

---

### 142. Question:  
Which command would you use to delete a Kubernetes deployment?  
- **A. kubectl delete deployment <deployment-name>**  
- **B. kubectl destroy deployment <deployment-name>**  
- **C. kubectl remove deployment <deployment-name>**  
- **D. kubectl kill deployment <deployment-name>**  
**Correct Answer:** **A. kubectl delete deployment <deployment-name>**  
**Explanation:** The **kubectl delete deployment** command is used to delete a deployment from the cluster, removing its associated pods and resources.  

---

### 143. Question:  
What does the **kubectl port-forward** command do?  
- **A. It forwards traffic from a local port to a port on a pod**  
- **B. It configures port forwarding in a service**  
- **C. It exposes a pod to external traffic**  
- **D. It scales the number of pods based on network traffic**  
**Correct Answer:** **A. It forwards traffic from a local port to a port on a pod**  
**Explanation:** The **kubectl port-forward** command is used to forward traffic from a local machine to a port on a pod, useful for accessing services running inside the cluster without exposing them externally.  

---

### 144. Question:  
What is a **Taint** in Kubernetes used for?  
- **A. To mark a node as unsuitable for certain pods to run on**  
- **B. To store configuration data that can be accessed by pods**  
- **C. To enforce pod security policies**  
- **D. To attach metadata to pods for easier management**  
**Correct Answer:** **A. To mark a node as unsuitable for certain pods to run on**  
**Explanation:** A **Taint** is applied to a node to prevent pods from being scheduled on that node unless they have a matching **Toleration**. This is useful for preventing certain workloads from running on nodes that are being used for special purposes.  

---

### 145. Question:  
How do you limit the resources (CPU, memory) that a container can consume in a pod?  
- **A. By setting **requests** and **limits** in the pod’s container specification**  
- **B. By using a **ResourceQuota****  
- **C. By setting limits on the node level**  
- **D. By using a **Deployment** object**  
**Correct Answer:** **A. By setting **requests** and **limits** in the pod’s container specification**  
**Explanation:** You can set **requests** (minimum resources required) and **limits** (maximum resources a container can use) in the container specification within a pod.  

---

### 146. Question:  
Which Kubernetes object can be used to ensure that a service is only accessible from within the cluster and not externally?  
- **A. ClusterIP**  
- **B. NodePort**  
- **C. LoadBalancer**  
- **D. Ingress**  
**Correct Answer:** **A. ClusterIP**  
**Explanation:** The **ClusterIP** service type makes the service accessible only within the Kubernetes cluster, not from outside the cluster.  

---

### 147. Question:  
Which command can be used to see the details of a specific pod in Kubernetes?  
- **A. kubectl describe pod <pod-name>**  
- **B. kubectl get pod <pod-name>**  
- **C. kubectl show pod <pod-name>**  
- **D. kubectl pod describe <pod-name>**  
**Correct Answer:** **A. kubectl describe pod <pod-name>**  
**Explanation:** The **kubectl describe pod <pod-name>** command provides detailed information about a pod, including its status, events, and the containers inside it.  

---

### 148. Question:  
What type of service is used to expose an application to the internet in a cloud environment, where an external load balancer is provisioned to route traffic to the service?  
- **A. LoadBalancer**  
- **B. NodePort**  
- **C. ClusterIP**  
- **D. Ingress**  
**Correct Answer:** **A. LoadBalancer**  
**Explanation:** A **LoadBalancer** service type provisions an external load balancer (in cloud environments) to route traffic to your service, making it accessible from outside the cluster.  

---

### 149. Question:  
Which of the following components in Kubernetes is responsible for ensuring that the desired state of the cluster matches the actual state?  
- **A. kube-apiserver**  
- **B. kube-controller-manager**  
- **C. kube-scheduler**  
- **D. kube-proxy**  
**Correct Answer:** **B. kube-controller-manager**  
**Explanation:** The **kube-controller-manager** runs controllers that make changes to bring the cluster’s actual state in line with its desired state, such as scaling deployments or handling pod failures.  

---

### 150. Question:  
What is the purpose of **kubectl apply** command in Kubernetes?  
- **A. To create or update resources based on a configuration file**  
- **B. To delete a resource from the cluster**  
- **C. To get information about a resource**  
- **D. To describe the state of a resource**  
**Correct Answer:** **A. To create or update resources based on a configuration file**  
**Explanation:** The **kubectl apply** command is used to create or update Kubernetes resources defined in a YAML configuration file, ensuring the desired state is applied.  

---

### 151. Question:  
What is the difference between **kubectl create** and **kubectl apply**?  
- **A. **kubectl create** creates resources, whereas **kubectl apply** ensures that the current state matches the desired state**  
- **B. **kubectl create** updates existing resources, whereas **kubectl apply** deletes resources**  
- **C. **kubectl create** is used for declarative management, while **kubectl apply** is for imperative management**  
- **D. There is no difference; both are used for creating resources**  
**Correct Answer:** **A. **kubectl create** creates resources, whereas **kubectl apply** ensures that the current state matches the desired state**  
**Explanation:** **kubectl create** is used to create resources for the first time, while **kubectl apply** can be used to both create and update resources, maintaining the desired state of the resource over time.

---

### 152. Question:  
What does the Kubernetes **kube-proxy** component do?  
- **A. It manages the API server**  
- **B. It enables communication between the master and worker nodes**  
- **C. It manages network rules for pod-to-pod and external-to-pod communication**  
- **D. It is responsible for scheduling pods to nodes**  
**Correct Answer:** **C. It manages network rules for pod-to-pod and external-to-pod communication**  
**Explanation:** **kube-proxy** manages the networking of services within Kubernetes, ensuring that network traffic is routed correctly, either between pods or to external services.

---

### 153. Question:  
What happens when you scale a **Deployment** in Kubernetes?  
- **A. Kubernetes creates new replicas of the pods and deletes old ones if necessary**  
- **B. It automatically increases CPU and memory allocation for each pod**  
- **C. It redistributes pods across nodes**  
- **D. It updates the pods with new container images**  
**Correct Answer:** **A. Kubernetes creates new replicas of the pods and deletes old ones if necessary**  
**Explanation:** Scaling a **Deployment** increases or decreases the number of pod replicas to match the specified count, ensuring the desired state is maintained.

---

### 154. Question:  
What does the **kubectl rollout undo** command do in Kubernetes?  
- **A. It rolls back a deployment to a previous state**  
- **B. It deletes a deployment’s last replica set**  
- **C. It updates the pod’s image to the previous version**  
- **D. It stops the current rollout process**  
**Correct Answer:** **A. It rolls back a deployment to a previous state**  
**Explanation:** The **kubectl rollout undo** command is used to revert a deployment to its previous state, often used when a deployment causes issues and needs to be reverted.

---

### 155. Question:  
Which of the following is the correct way to expose a pod externally in a Kubernetes cluster?  
- **A. Create a Service of type **ClusterIP****  
- **B. Create a Service of type **NodePort** or **LoadBalancer****  
- **C. Use **kubectl expose pod** with the **--external** flag**  
- **D. Use **kubectl expose** with a service account**  
**Correct Answer:** **B. Create a Service of type **NodePort** or **LoadBalancer****  
**Explanation:** To expose a pod externally, you typically create a **Service** of type **NodePort** or **LoadBalancer**, which will expose the pod to external traffic.

---

### 156. Question:  
In Kubernetes, what is the purpose of a **PodSecurityPolicy**?  
- **A. To define security controls for pod configurations and enforce them**  
- **B. To limit the number of replicas a pod can scale to**  
- **C. To specify the pod’s allowed resource usage**  
- **D. To define network policies for pods**  
**Correct Answer:** **A. To define security controls for pod configurations and enforce them**  
**Explanation:** A **PodSecurityPolicy** is a security feature in Kubernetes that defines a set of conditions that must be met for a pod to be created, such as restrictions on privilege escalation or running as root.

---

### 157. Question:  
Which component is responsible for performing health checks (liveness and readiness probes) on Kubernetes pods?  
- **A. kube-proxy**  
- **B. kube-apiserver**  
- **C. kubelet**  
- **D. kube-scheduler**  
**Correct Answer:** **C. kubelet**  
**Explanation:** The **kubelet** is responsible for managing containers and running health checks like liveness and readiness probes to ensure that pods are functioning correctly.

---

### 158. Question:  
Which Kubernetes resource allows you to set policies that restrict what pods can run on certain nodes?  
- **A. NodeSelector**  
- **B. Taints and Tolerations**  
- **C. PodDisruptionBudget**  
- **D. Affinity**  
**Correct Answer:** **B. Taints and Tolerations**  
**Explanation:** **Taints and Tolerations** allow nodes to repel certain pods unless they tolerate the taint, ensuring specific workloads are scheduled only on suitable nodes.

---

### 159. Question:  
What is the main benefit of using Kubernetes namespaces?  
- **A. To group related resources together for easier management**  
- **B. To apply security policies to the cluster**  
- **C. To enable multi-cluster communication**  
- **D. To enforce resource limits for all pods**  
**Correct Answer:** **A. To group related resources together for easier management**  
**Explanation:** Kubernetes namespaces allow you to organize resources in a cluster into separate logical groups, helping with management, access control, and resource isolation.

---

### 160. Question:  
How does Kubernetes handle node failures in a cluster?  
- **A. The scheduler reschedules the pods on other available nodes**  
- **B. Kubernetes automatically shuts down the cluster**  
- **C. The master node assumes control of all workloads**  
- **D. Kubernetes pauses the deployment until the node is available again**  
**Correct Answer:** **A. The scheduler reschedules the pods on other available nodes**  
**Explanation:** When a node fails, the Kubernetes scheduler attempts to reschedule the affected pods onto other available nodes, ensuring that the application remains available.

---

### 161. Question:  
What is the function of the **kube-apiserver** in Kubernetes?  
- **A. It serves as the API server, handling all requests from clients**  
- **B. It schedules pods to available nodes**  
- **C. It monitors the health of nodes and pods**  
- **D. It manages the lifecycle of containers**  
**Correct Answer:** **A. It serves as the API server, handling all requests from clients**  
**Explanation:** The **kube-apiserver** is the front-end to the Kubernetes control plane, handling all incoming requests and communicating with other components.

---

### 162. Question:  
What is a **DaemonSet** in Kubernetes used for?  
- **A. To run a copy of a pod on all (or some) nodes in a cluster**  
- **B. To ensure a set of pods is always running in a specific namespace**  
- **C. To allow pods to communicate with external services**  
- **D. To automatically delete pods when not needed**  
**Correct Answer:** **A. To run a copy of a pod on all (or some) nodes in a cluster**  
**Explanation:** A **DaemonSet** ensures that a specific pod is running on every node (or a subset of nodes) in the cluster, useful for services like logging, monitoring, or networking agents.

---

### 163. Question:  
What are **Kubernetes annotations** typically used for?  
- **A. To store configuration data that can be consumed by the pod**  
- **B. To store non-identifying metadata about resources**  
- **C. To define resource limits for a pod**  
- **D. To configure networking between pods**  
**Correct Answer:** **B. To store non-identifying metadata about resources**  
**Explanation:** Annotations are key-value pairs used to store non-identifying metadata for resources, such as timestamps, configuration details, or information for external tools.

---

### 164. Question:  
What is the purpose of **kubectl logs** in Kubernetes?  
- **A. To view the logs of containers in a pod**  
- **B. To monitor the resource usage of containers**  
- **C. To update the logs of a deployment**  
- **D. To check the status of the kubelet**  
**Correct Answer:** **A. To view the logs of containers in a pod**  
**Explanation:** The **kubectl logs** command is used to view the logs of a specific container in a pod, which helps in debugging and monitoring application behavior.

---

### 165. Question:  
What is the role of the **kube-scheduler** in Kubernetes?  
- **A. It schedules the pods to run on appropriate nodes based on resource availability and constraints**  
- **B. It monitors the health of the nodes**  
- **C. It serves API requests**  
- **D. It manages persistent volumes**  
**Correct Answer:** **A. It schedules the pods to run on appropriate nodes based on resource availability and constraints**  
**Explanation:** The **kube-scheduler** is responsible for selecting the node for a pod to run on, based on available resources, constraints, and other factors like affinity or taints.

---

### 166. Question:  
Which of the following best describes **Kubernetes ConfigMaps**?  
- **A. A storage solution for persistent volumes**  
- **B. A set of files that define the desired state of the cluster**  
- **C. A way to store and manage non-sensitive configuration data**  
- **D. A service for managing authentication across Kubernetes clusters**  
**Correct Answer:** **C. A way to store and manage non-sensitive configuration data**  
**Explanation:** **ConfigMaps** are used to store non-sensitive configuration data that can be accessed by containers or pods to allow for easier management of application configurations.

---

### 167. Question:  
How would you scale the number of replicas for a Kubernetes deployment?  
- **A. By using the **kubectl scale** command**  
- **B. By editing the deployment YAML file manually**  
- **C. By deleting and recreating the deployment**  
- **D. Both A and B**  
**Correct Answer:** **D. Both A and B**  
**Explanation:** You can scale the number of replicas either by using the **kubectl scale** command or by modifying the replica count in the deployment YAML file and applying the changes.

---

### 168. Question:  
In Kubernetes, what is the primary purpose of a **HorizontalPodAutoscaler** (HPA)?  
- **A. To adjust the number of pod replicas based on CPU or memory utilization**  
- **B. To adjust the resource limits of individual containers**  
- **C. To balance workloads across nodes**  
- **D. To manage persistent volume claims**  
**Correct Answer:** **A. To adjust the number of pod replicas based on CPU or memory utilization**  
**Explanation:** The **HorizontalPodAutoscaler** automatically adjusts the number of replicas for a deployment or replica set based on observed CPU or memory utilization, ensuring optimal scaling.

---

### 169. Question:  
Which Kubernetes object ensures that data is stored persistently across pod restarts?  
- **A. ConfigMap**  
- **B. PersistentVolumeClaim (PVC)**  
- **C. Service**  
- **D. PodDisruptionBudget**  
**Correct Answer:** **B. PersistentVolumeClaim (PVC)**  
**Explanation:** A **PersistentVolumeClaim** (PVC) is used to request persistent storage resources from the cluster, ensuring data persists even if a pod is restarted.

---

### 170. Question:  
Which Kubernetes object is used to define network policies for controlling traffic between pods?  
- **A. PodDisruptionBudget**  
- **B. NetworkPolicy**  
- **C. ServiceAccount**  
- **D. ResourceQuota**  
**Correct Answer:** **B. NetworkPolicy**  
**Explanation:** **NetworkPolicy** defines rules for controlling the communication between pods in the Kubernetes cluster, allowing traffic filtering based on namespaces, labels, and IP blocks.

---

### 171. Question:  
What is the difference between a **ReplicaSet** and a **Deployment** in Kubernetes?  
- **A. A Deployment provides higher-level functionality, such as rolling updates, while a ReplicaSet is responsible for managing the replica count**  
- **B. A ReplicaSet is used to manage persistent storage, while a Deployment manages compute resources**  
- **C. A Deployment runs in a pod, while a ReplicaSet runs in a node**  
- **D. There is no difference; they are interchangeable**  
**Correct Answer:** **A. A Deployment provides higher-level functionality, such as rolling updates, while a ReplicaSet is responsible for managing the replica count**  
**Explanation:** A **Deployment** uses a **ReplicaSet** to manage the number of replicas and includes features such as rolling updates, making it more flexible and easier to manage.

---

### 172. Question:  
What is the purpose of **kubectl get** command in Kubernetes?  
- **A. To retrieve detailed logs of a pod**  
- **B. To create or modify resources in the cluster**  
- **C. To get a list of resources such as pods, services, deployments, etc.**  
- **D. To delete resources in the cluster**  
**Correct Answer:** **C. To get a list of resources such as pods, services, deployments, etc.**  
**Explanation:** The **kubectl get** command is used to retrieve a list of resources in the cluster, including pods, services, deployments, and more.

---

### 173. Question:  
What is the primary function of the **kubelet** in a Kubernetes cluster?  
- **A. It monitors and manages the state of containers running on a node**  
- **B. It controls the overall cluster state**  
- **C. It provides API services to the users**  
- **D. It schedules pods to nodes based on resource usage**  
**Correct Answer:** **A. It monitors and manages the state of containers running on a node**  
**Explanation:** The **kubelet** is an agent running on each node in the Kubernetes cluster, responsible for ensuring that containers are running in the pods as expected.

---

### 174. Question:  
In Kubernetes, how does a **StatefulSet** differ from a **Deployment**?  
- **A. A **StatefulSet** maintains stable network identities and persistent storage for each pod**  
- **B. A **StatefulSet** is used only for stateless applications**  
- **C. A **StatefulSet** does not support scaling**  
- **D. A **StatefulSet** manages the scheduling of pods across nodes**  
**Correct Answer:** **A. A **StatefulSet** maintains stable network identities and persistent storage for each pod**  
**Explanation:** **StatefulSets** are used for stateful applications where each pod needs a stable, unique network identity and persistent storage, unlike **Deployments** that are better suited for stateless applications.

---

### 175. Question:  
Which of the following commands is used to expose a pod as a service in Kubernetes?  
- **A. kubectl expose pod <pod-name>**  
- **B. kubectl expose service <service-name>**  
- **C. kubectl expose deployment <deployment-name>**  
- **D. kubectl expose node <node-name>**  
**Correct Answer:** **A. kubectl expose pod <pod-name>**  
**Explanation:** The **kubectl expose pod <pod-name>** command is used to expose an individual pod to the network, typically for internal service discovery or testing purposes.

---

### 176. Question:  
What is the purpose of a **PodDisruptionBudget** in Kubernetes?  
- **A. To specify how much downtime is acceptable for a pod**  
- **B. To define how many replicas of a pod can be deleted during a disruption**  
- **C. To set resource usage limits for a pod**  
- **D. To enforce network policies for pods**  
**Correct Answer:** **B. To define how many replicas of a pod can be deleted during a disruption**  
**Explanation:** A **PodDisruptionBudget** ensures that a minimum number of replicas of a pod are available during voluntary disruptions, such as node maintenance or pod updates.

---

### 177. Question:  
Which command would you use to view the cluster-wide resources and their usage in Kubernetes?  
- **A. kubectl get cluster-info**  
- **B. kubectl top nodes**  
- **C. kubectl describe cluster**  
- **D. kubectl view resources**  
**Correct Answer:** **B. kubectl top nodes**  
**Explanation:** The **kubectl top nodes** command provides resource usage metrics for each node in the cluster, including CPU and memory.

---

### 178. Question:  
What is the primary purpose of a **ServiceAccount** in Kubernetes?  
- **A. To grant pods access to the API server with specific permissions**  
- **B. To manage user accounts within the cluster**  
- **C. To provide authentication for external services**  
- **D. To enforce quotas for namespace resources**  
**Correct Answer:** **A. To grant pods access to the API server with specific permissions**  
**Explanation:** A **ServiceAccount** is used by pods to authenticate to the Kubernetes API server and interact with resources based on the assigned permissions.

---

### 179. Question:  
Which feature of Kubernetes is used to control the maximum number of resources (CPU, memory, etc.) that a namespace can consume?  
- **A. ResourceQuota**  
- **B. LimitRange**  
- **C. PodDisruptionBudget**  
- **D. Taints and Tolerations**  
**Correct Answer:** **A. ResourceQuota**  
**Explanation:** **ResourceQuota** is used to limit the total amount of resources (like CPU, memory, or storage) that a namespace can use.

---

### 180. Question:  
What does the **kubectl apply -f** command do?  
- **A. Deletes the specified resource**  
- **B. Updates or creates resources based on the provided YAML/JSON file**  
- **C. Displays the current state of the resource**  
- **D. Exposes a resource to the network**  
**Correct Answer:** **B. Updates or creates resources based on the provided YAML/JSON file**  
**Explanation:** The **kubectl apply -f** command creates or updates resources in the cluster to match the specifications in the provided file.

---

### 181. Question:  
What is a **Job** in Kubernetes?  
- **A. A Kubernetes object that runs a containerized task to completion**  
- **B. A process that continuously manages replicas**  
- **C. A persistent volume claim for stateful workloads**  
- **D. A scheduler process for node selection**  
**Correct Answer:** **A. A Kubernetes object that runs a containerized task to completion**  
**Explanation:** A **Job** in Kubernetes ensures that a specified task runs to completion, which is useful for batch processing and one-time tasks.

---

### 182. Question:  
What is the default service type in Kubernetes if no type is specified?  
- **A. ClusterIP**  
- **B. NodePort**  
- **C. LoadBalancer**  
- **D. ExternalName**  
**Correct Answer:** **A. ClusterIP**  
**Explanation:** If no type is specified, Kubernetes creates a service of type **ClusterIP**, which exposes the service internally within the cluster.

---

### 183. Question:  
What is the purpose of a **Readiness Probe** in Kubernetes?  
- **A. To determine if a container is ready to start receiving traffic**  
- **B. To check if a container is alive and running**  
- **C. To restart a failed container automatically**  
- **D. To measure the performance of a container**  
**Correct Answer:** **A. To determine if a container is ready to start receiving traffic**  
**Explanation:** A **Readiness Probe** ensures that a container is ready to handle requests. If the probe fails, the container will not receive traffic through a service.

---

### 184. Question:  
Which of the following is a valid way to view events in a Kubernetes cluster?  
- **A. kubectl get events**  
- **B. kubectl describe events**  
- **C. kubectl list events**  
- **D. kubectl show events**  
**Correct Answer:** **A. kubectl get events**  
**Explanation:** The **kubectl get events** command retrieves a list of events in the cluster, such as pod creation, deletion, and other significant actions.

---

### 185. Question:  
What is the main advantage of using a **PersistentVolume** (PV) in Kubernetes?  
- **A. It allows data to persist across pod restarts and reschedules**  
- **B. It automatically backs up data in the cluster**  
- **C. It enables faster pod scaling**  
- **D. It improves pod networking performance**  
**Correct Answer:** **A. It allows data to persist across pod restarts and reschedules**  
**Explanation:** A **PersistentVolume** provides storage that is independent of the lifecycle of a pod, ensuring data persists even if the pod is restarted or rescheduled.

---

### 186. Question:  
Which of the following commands will delete all pods in a specific namespace?  
- **A. kubectl delete pods --namespace <namespace-name>**  
- **B. kubectl delete all --namespace <namespace-name>**  
- **C. kubectl delete pod -n <namespace-name>**  
- **D. kubectl delete namespace <namespace-name>**  
**Correct Answer:** **A. kubectl delete pods --namespace <namespace-name>**  
**Explanation:** The **kubectl delete pods** command deletes all pods in the specified namespace without affecting other resource types.

---

### 187. Question:  
What is the purpose of **Affinity** and **AntiAffinity** in Kubernetes?  
- **A. To manage storage claims for stateful applications**  
- **B. To control how pods are placed on nodes**  
- **C. To monitor pod-to-pod communication**  
- **D. To enforce resource quotas in a namespace**  
**Correct Answer:** **B. To control how pods are placed on nodes**  
**Explanation:** **Affinity** and **AntiAffinity** rules specify preferences for pod placement on nodes, such as ensuring pods are co-located or separated based on specific criteria.

---

### 188. Question:  
What is the default namespace in Kubernetes if none is specified?  
- **A. kube-system**  
- **B. default**  
- **C. kube-public**  
- **D. cluster-default**  
**Correct Answer:** **B. default**  
**Explanation:** If no namespace is specified, Kubernetes uses the **default** namespace.

---

### 189. Question:  
Which Kubernetes resource is used for automated secrets injection into pods?  
- **A. ConfigMap**  
- **B. Secret**  
- **C. ServiceAccount**  
- **D. PersistentVolumeClaim**  
**Correct Answer:** **B. Secret**  
**Explanation:** A **Secret** is used to store sensitive information, such as passwords or tokens, and can be injected into pods securely.

---

### 190. Question:  
What happens when you delete a **Deployment** in Kubernetes?  
- **A. All associated pods are deleted**  
- **B. Only the replica set is deleted**  
- **C. The Deployment is deleted but pods remain running**  
- **D. The cluster stops the deployment temporarily**  
**Correct Answer:** **A. All associated pods are deleted**  
**Explanation:** Deleting a **Deployment** will also delete the associated replica sets and their pods, removing the resources entirely.

---

### 191. Question:  
What is the purpose of a **DaemonSet** in Kubernetes?  
- **A. To ensure a copy of a pod runs on all (or selected) nodes**  
- **B. To schedule jobs that run to completion**  
- **C. To manage persistent volumes across nodes**  
- **D. To create services for external load balancers**  
**Correct Answer:** **A. To ensure a copy of a pod runs on all (or selected) nodes**  
**Explanation:** A **DaemonSet** ensures that a pod runs on all or a subset of nodes in the cluster, typically for cluster-wide services like logging or monitoring.

---

### 192. Question:  
Which of the following is NOT a valid service type in Kubernetes?  
- **A. ClusterIP**  
- **B. NodePort**  
- **C. ExternalIP**  
- **D. LoadBalancer**  
**Correct Answer:** **C. ExternalIP**  
**Explanation:** **ClusterIP**, **NodePort**, and **LoadBalancer** are valid Kubernetes service types. **ExternalIP** is not a recognized service type.

---

### 193. Question:  
What does the **kubectl exec** command do?  
- **A. It runs a command inside a running container**  
- **B. It creates a new container in a pod**  
- **C. It starts a new deployment**  
- **D. It displays resource usage metrics**  
**Correct Answer:** **A. It runs a command inside a running container**  
**Explanation:** The **kubectl exec** command is used to execute commands directly inside a running container, such as inspecting logs or troubleshooting.

---

### 194. Question:  
Which component in Kubernetes manages the API server authentication and authorization?  
- **A. kube-scheduler**  
- **B. kube-apiserver**  
- **C. kube-proxy**  
- **D. etcd**  
**Correct Answer:** **B. kube-apiserver**  
**Explanation:** The **kube-apiserver** is the central management component that handles authentication, authorization, and API requests.

---

### 195. Question:  
What is the function of **kube-proxy** in a Kubernetes cluster?  
- **A. To route traffic to the appropriate pod within the cluster**  
- **B. To monitor the health of pods**  
- **C. To store cluster data persistently**  
- **D. To schedule pods to nodes**  
**Correct Answer:** **A. To route traffic to the appropriate pod within the cluster**  
**Explanation:** The **kube-proxy** manages network rules to direct traffic to the correct pods based on services.

---

### 196. Question:  
Which Kubernetes resource allows you to set environment variables for a pod?  
- **A. ConfigMap**  
- **B. Secret**  
- **C. Deployment**  
- **D. ServiceAccount**  
**Correct Answer:** **A. ConfigMap**  
**Explanation:** A **ConfigMap** stores configuration data, such as environment variables, which can be injected into pods.

---

### 197. Question:  
What is a **Taint** in Kubernetes?  
- **A. A way to prevent certain pods from being scheduled on a node**  
- **B. A method for prioritizing pods during scaling**  
- **C. A label applied to a pod for selection**  
- **D. A limit on the number of pods a node can run**  
**Correct Answer:** **A. A way to prevent certain pods from being scheduled on a node**  
**Explanation:** **Taints** are applied to nodes to repel pods unless the pod has a matching **toleration**.

---

### 198. Question:  
What is the primary purpose of a **HorizontalPodAutoscaler** (HPA) in Kubernetes?  
- **A. To adjust the number of pod replicas based on resource usage**  
- **B. To balance traffic across services**  
- **C. To ensure pods restart automatically upon failure**  
- **D. To monitor inter-pod communication**  
**Correct Answer:** **A. To adjust the number of pod replicas based on resource usage**  
**Explanation:** HPA dynamically scales the number of pod replicas based on observed resource usage like CPU and memory.

---

### 199. Question:  
Which command is used to list all namespaces in a Kubernetes cluster?  
- **A. kubectl get namespaces**  
- **B. kubectl list namespaces**  
- **C. kubectl describe namespaces**  
- **D. kubectl view namespaces**  
**Correct Answer:** **A. kubectl get namespaces**  
**Explanation:** The **kubectl get namespaces** command lists all namespaces in the cluster.

---

### 200. Question:  
Which feature of Kubernetes ensures applications can survive node failures?  
- **A. ReplicaSet**  
- **B. StatefulSet**  
- **C. NodeSelector**  
- **D. HorizontalPodAutoscaler**  
**Correct Answer:** **A. ReplicaSet**  
**Explanation:** A **ReplicaSet** ensures that a specified number of pod replicas are running, allowing the application to remain available even if a node fails.
