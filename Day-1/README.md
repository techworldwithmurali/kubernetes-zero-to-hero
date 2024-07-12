#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | [Tech World with Murali](https://www.techworldwithmurali.com/)               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

## What is Kubernetes?

- Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications.
- It was originally developed by Google and is now maintained by the Cloud Native Computing Foundation (CNCF).
- Kubernetes simplifies the management of complex distributed systems by providing a unified API to deploy, manage, and scale applications.


## Key Points

1. **Open-Source Platform**: Kubernetes is an open-source project, which means it is free to use and has a large community of contributors and users.
2. **Container Orchestration**: It automates the deployment, scaling, and management of containerized applications.
3. **Originally Developed by Google**: Kubernetes was initially created by Google engineers and is now managed by the CNCF.
4. **Unified API**: Provides a consistent API for deploying, managing, and scaling applications.
5. **Simplifies Management**: Makes it easier to manage complex distributed systems.
6. **Supports Multiple Cloud Providers**: Works across various cloud providers, enabling hybrid and multi-cloud environments.
7. **Extensible**: Highly customizable and can be extended with plugins and extensions.
8. **Resilient and Scalable**: Designed to ensure high availability and scalability of applications.

## Resources

- [Kubernetes Official Documentation](https://kubernetes.io/docs/)

## Why Kubernetes?

Kubernetes addresses the challenges associated with deploying and scaling containerized applications in production environments. Here are key reasons why organizations choose Kubernetes:

- **Portability**: Kubernetes provides a consistent environment across various infrastructure providers (public, private, hybrid clouds) and on-premises.
- **Scalability**: It allows automatic scaling of applications, handling increased traffic and workload demand efficiently.
- **Resource Efficiency**: Kubernetes optimizes resource usage by packing containers efficiently and utilizing resources based on application needs.
- **High Availability**: Ensures applications are highly available and resilient to failures with automated recovery mechanisms.
- **Developer Productivity**: Simplifies application deployment and management, allowing developers to focus more on coding rather than infrastructure concerns.
- **Ecosystem**: Kubernetes has a vibrant ecosystem with a wide range of tools and integrations, supporting CI/CD, logging, monitoring, and more.

## Advantages of Kubernetes

### Operational Advantages:
- **Automation**: Automates the deployment, scaling, and management of containerized applications.
- **Consistency**: Provides a consistent environment for development, testing, and production.
- **Flexibility**: Supports microservices architecture and application portability across environments.
- **Scalability**: Scales applications horizontally and vertically based on demand.
- **Fault Tolerance**: Ensures high availability with automated health checks and container restarts.

### Business Advantages:
- **Cost-Effective**: Optimizes resource usage, reducing infrastructure costs.
- **Faster Time to Market**: Speeds up application development and deployment cycles.
- **Competitive Edge**: Enables organizations to innovate faster and respond quickly to market changes.
- **Vendor Agnostic**: Works seamlessly across multiple cloud providers and on-premises environments.

## Kubernetes Architecture

![Kubernetes Architecture - Tech World with Murali - Moole Muralidhara Reddy.png](https://github.com/techworldwithmurali/kubernetes-zero-to-hero/blob/main/Day-1/images/Kubernetes%20Architecture%20-%20Tech%20World%20with%20Murali%20-%20Moole%20Muralidhara%20Reddy.png)
### Components of Kubernetes Architecture:
# Master Node Components

## API Server

- **Description**: The Kubernetes API Server acts as the control plane's frontend and is responsible for processing RESTful API requests, authentication, and authorization.
- **Role**: It's the entry point for administrators, developers, and other services.

## etcd

- **Description**: etcd is a distributed key-value store that stores the cluster's configuration data. It provides consistency and high availability.
- **Example**: If you update the number of replicas for a deployment, etcd stores this configuration change.

## Scheduler

- **Description**: The Scheduler is responsible for assigning pods to nodes based on resource requirements and constraints.
- **Example**: If you create a new pod without specifying a node, the scheduler selects an appropriate node to run it.

## kube-controller-manager

- **Description**: The kube-controller-manager is one of the core components of Kubernetes. It is responsible for running controller processes that regulate the state of the system to achieve the desired state specified by users.
- **Function**: Controllers are control loops that continuously watch the state of the cluster and make changes to move the current state closer to the desired state.

## cloud-controller-manager

- **Description**: When running Kubernetes on AWS using Amazon Elastic Kubernetes Service (EKS), the cloud-controller-manager interacts with AWS services to manage various resources and functionalities.

# Node Components

## Kubelet

- **Description**: Kubelet is an agent that runs on each node and is responsible for ensuring that containers are running in a pod.
- **Example**: If a pod definition specifies a container to run, Kubelet makes sure that the container is started and running on the node.

## Kube Proxy

- **Description**: Kube Proxy is responsible for network routing and load balancing within the cluster. It maintains network rules on each node.
- **Example**: If you create a Service resource, Kube Proxy ensures that traffic is correctly routed to the appropriate pods.

## Container Runtime

- **Description**: A container runtime, such as Docker or containerd, is responsible for running containers in pods.
- **Example**: When you specify a Docker image in a pod definition, the container runtime downloads and runs that image.

### Kubernetes Objects:
![Kubernetes Objects - Tech World with Murali - Moole Muralidhara Reddy.png](https://github.com/techworldwithmurali/kubernetes-zero-to-hero/blob/main/Day-1/images/Kubernetes%20Objects%20-%20Tech%20World%20with%20Murali%20-%20Moole%20Muralidhara%20Reddy.png)

- **Pods**: Smallest deployable units in Kubernetes, consisting of one or more containers.
- **Services**: Abstraction that defines a logical set of pods and a policy for accessing them.
- **Deployments**: Defines desired state for pods and manages rolling updates and rollbacks.
- **ReplicaSets**: Ensures a specified number of pod replicas are running at any given time.
- **Namespaces**: Virtual clusters that enable multiple users or teams to share the same Kubernetes cluster securely.
