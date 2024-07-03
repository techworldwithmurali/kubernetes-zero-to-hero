## Kubernetes Troubleshooting Part 2
### 1. Pod is Stuck in Pending State

**Problem:**
A Pod in the `Pending` state indicates that Kubernetes cannot schedule the Pod onto a node.

**Steps to Troubleshoot and Resolve:**

1. **Check Pod Status:**
   ```sh
   kubectl get pods -n <namespace>
   ```

2. **Describe the Pod:**
   This command provides detailed information about the Pod, including events that might indicate why it's not scheduling.
   ```sh
   kubectl describe pod <pod-name> -n <namespace>
   ```

3. **Check Node Availability:**
   Ensure that there are available nodes that can satisfy the Pod's resource requests (CPU, memory).
   ```sh
   kubectl get nodes
   ```

4. **Check Resource Requests:**
   Verify that the Pod's resource requests are within the limits of available resources on the nodes.
   ```sh
   kubectl describe pod <pod-name> -n <namespace> | grep -i "resource requests"
   ```

5. **Check Node Selector and Affinity:**
   If the Pod has node affinity or a node selector, ensure that there are nodes that match the specified criteria.
   ```sh
   kubectl describe pod <pod-name> -n <namespace> | grep -i "node selector\|affinity"
   ```

6. **Check Taints and Tolerations:**
   Verify if there are node taints that might be preventing the Pod from scheduling and if the Pod has corresponding tolerations.
   ```sh
   kubectl describe node <node-name>
   kubectl describe pod <pod-name> -n <namespace> | grep -i "tolerations"
   ```

7. **Check PersistentVolumeClaims (PVCs):**
   If the Pod requires PVCs, ensure that the PVCs are available and not stuck in a pending state themselves.
   ```sh
   kubectl get pvc -n <namespace>
   ```

8. **Example Solution:**

   - **Issue:** The Pod has a node selector that doesn't match any available nodes.
   - **Solution:** Update the Pod spec to use a node selector that matches available nodes.

   **Updated Deployment YAML:**
   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: my-app
     namespace: default
   spec:
     replicas: 1
     selector:
       matchLabels:
         app: my-app
     template:
       metadata:
         labels:
           app: my-app
       spec:
         nodeSelector:
           kubernetes.io/hostname: node1
         containers:
         - name: my-app
           image: my-app-image
   ```

### 2. Container Image Pull is Failing with Image Not Found or Access Denied Errors

**Problem:**
The container image cannot be pulled due to image not found or access denied errors.

**Steps to Troubleshoot and Resolve:**

1. **Check Pod Status:**
   ```sh
   kubectl get pods -n <namespace>
   ```

2. **Describe the Pod:**
   This command provides detailed information about the image pull failure.
   ```sh
   kubectl describe pod <pod-name> -n <namespace>
   ```

3. **Check Image Name and Tag:**
   Verify that the image name and tag specified in the Pod spec are correct.
   ```sh
   kubectl describe pod <pod-name> -n <namespace> | grep -i "image"
   ```

4. **Check Image Registry and Access:**
   Ensure that the image exists in the specified registry and that the Kubernetes cluster has access to pull the image.
   ```sh
   # Check if the image exists in the registry
   curl -sSL https://registry.example.com/v2/<image-name>/tags/list | jq .
   
   # Check if Kubernetes has access (if using a private registry)
   kubectl get secrets -n <namespace>   # Look for image pull secrets
   ```

5. **Check Image Pull Secrets:**
   If the image is in a private registry, ensure that the correct image pull secret is specified in the Pod spec.
   ```sh
   kubectl get secrets -n <namespace>
   ```

6. **Example Solution:**

   - **Issue:** The Pod spec is referencing an incorrect image repository URL.
   - **Solution:** Correct the image repository URL in the Pod spec.

   **Updated Deployment YAML:**
   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: my-app
     namespace: default
   spec:
     replicas: 1
     selector:
       matchLabels:
         app: my-app
     template:
       metadata:
         labels:
           app: my-app
       spec:
         containers:
         - name: my-app
           image: registry.example.com/my-app-image:latest
           imagePullPolicy: Always   # Optional, depending on your needs
         imagePullSecrets:
         - name: myregistrykey
   ```
