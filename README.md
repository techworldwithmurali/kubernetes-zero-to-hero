### What is eksctl?

`eksctl` is a simple command-line utility for creating and managing Kubernetes clusters on Amazon EKS (Elastic Kubernetes Service). It's written in Go and simplifies the process of cluster creation by allowing you to define your cluster configuration in a YAML file or directly from the command line. With `eksctl`, you can create a fully functioning EKS cluster with a single command, making it an essential tool for developers and DevOps engineers working with Kubernetes on AWS.

### Installation of eksctl on Linux

1. **Download eksctl:**
   ```sh
   curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
   ```

2. **Move eksctl to `/usr/local/bin`:**
   ```sh
   sudo mv /tmp/eksctl /usr/local/bin
   ```

3. **Verify the installation:**
   ```sh
   eksctl version
   ```

### Installation of eksctl on Windows

1. **Download the eksctl executable:**
   - Visit the [eksctl releases page](https://github.com/weaveworks/eksctl/releases).
   - Download the latest release for Windows.

2. **Extract the zip file:**
   - Extract the downloaded zip file to a directory of your choice.

3. **Add the directory to your PATH environment variable:**
   - Open Control Panel -> System and Security -> System -> Advanced system settings.
   - Click on "Environment Variables".
   - In the "System variables" section, find the `Path` variable and click "Edit".
   - Add the path to the directory where you extracted `eksctl`.

4. **Verify the installation:**
   ```cmd
   eksctl version
   ```

### Lab Session: Setting Up AWS EKS with eksctl

#### Prerequisites

- AWS CLI installed and configured with proper IAM permissions.
- eksctl installed on your local machine (Linux or Windows).

#### Step-by-Step Guide

1. **Create a Cluster Configuration File (optional):**
   ```yaml
   # cluster.yaml
   apiVersion: eksctl.io/v1alpha5
   kind: ClusterConfig

   metadata:
     name: my-cluster
     region: us-west-2

   nodeGroups:
     - name: ng-1
       instanceType: t3.medium
       desiredCapacity: 2
   ```

2. **Create an EKS Cluster:**

   **Using a Configuration File:**
   ```sh
   eksctl create cluster -f cluster.yaml
   ```

   **Using Command Line:**
   ```sh
   eksctl create cluster --name my-cluster --region us-west-2 --nodegroup-name standard-workers --node-type t3.medium --nodes 2
   ```

3. **Verify the Cluster:**
   ```sh
   eksctl get cluster --region us-west-2
   ```

4. **Update kubeconfig:**
   ```sh
   aws eks --region us-west-2 update-kubeconfig --name my-cluster
   ```

5. **Verify Kubernetes Nodes:**
   ```sh
   kubectl get nodes
   ```

6. **Deploy a Sample Application:**

   **Create a Deployment:**
   ```sh
   kubectl create deployment hello-world --image=k8s.gcr.io/echoserver:1.4
   ```

   **Expose the Deployment:**
   ```sh
   kubectl expose deployment hello-world --type=LoadBalancer --port=8080
   ```

7. **Get the External IP:**
   ```sh
   kubectl get services hello-world
   ```

   - Access the sample application using the external IP.

8. **Delete the Cluster (when done):**
   ```sh
   eksctl delete cluster --name my-cluster --region us-west-2
   ```
