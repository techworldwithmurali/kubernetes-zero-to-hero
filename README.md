## Kubernetes Troubleshooting Part 1
### 1. Pod is in CrashLoopBackOff State

**Problem:**
A Pod in the `CrashLoopBackOff` state indicates that the container inside the Pod is repeatedly crashing and restarting.

**Steps to Troubleshoot and Resolve:**

1. **Check Pod Status:**
   ```sh
   kubectl get pod <pod-name> -n <namespace>
   ```

2. **Describe the Pod:**
   Detailed information, including events, helps identify why the Pod is crashing.
   ```sh
   kubectl describe pod <pod-name> -n <namespace>
   ```

3. **Check Pod Logs:**
   Logs provide insights into the error causing the crash.
   ```sh
   kubectl logs <pod-name> -n <namespace>
   ```

4. **Check Previous Pod Logs:**
   If the container has restarted, check the logs of the previous instance.
   ```sh
   kubectl logs <pod-name> -n <namespace> --previous
   ```

5. **Check Resource Limits:**
   Ensure the Pod has enough CPU and memory.
   ```sh
   kubectl describe pod <pod-name> -n <namespace> | grep -i limits -A 5
   ```

6. **Example Solution:**

   - **Issue:** The application inside the container is failing to start because of a missing configuration file.
   - **Solution:** Update the Pod spec to mount the required configuration file.

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
           image: my-app-image
           volumeMounts:
           - name: config-volume
             mountPath: /app/config
         volumes:
         - name: config-volume
           configMap:
             name: my-app-config
   ```

### 2. Service is Not Accessible Externally

**Problem:**
A Service of type `LoadBalancer` or `NodePort` is not accessible from outside the cluster.

**Steps to Troubleshoot:**

1. **Check Service Status:**
   ```sh
   kubectl get svc <service-name> -n <namespace>
   ```

2. **Describe the Service:**
   Detailed information about the Service can reveal configuration issues.
   ```sh
   kubectl describe svc <service-name> -n <namespace>
   ```

3. **Check Endpoint Availability:**
   Ensure the Service has endpoints and the Pods are correctly labeled.
   ```sh
   kubectl get endpoints <service-name> -n <namespace>
   ```

4. **Check Ingress Rules (if applicable):**
   If you're using an Ingress, ensure the rules are correct.
   ```sh
   kubectl get ingress -n <namespace>
   ```

5. **Check Firewall and Security Group Settings:**
   Ensure your cloud provider's security groups or firewalls allow traffic on the required ports.

6. **Example Solution:**

   - **Issue:** The Service type is `ClusterIP`, which is not accessible externally.
   - **Solution:** Change the Service type to `NodePort`.

   **Updated Service YAML:**
   ```yaml
   apiVersion: v1
   kind: Service
   metadata:
     name: my-service
     namespace: default
   spec:
     type: NodePort
     selector:
       app: my-app
     ports:
     - port: 80
       targetPort: 80
       nodePort: 30001
   ```

### 3. Node is Not Ready

**Problem:**
A Node in the `NotReady` state means it cannot schedule Pods.

**Steps to Investigate:**

1. **Check Node Status:**
   ```sh
   kubectl get nodes
   ```

2. **Describe the Node:**
   This provides detailed information about the Node, including events.
   ```sh
   kubectl describe node <node-name>
   ```

3. **Check Kubelet Logs:**
   Review logs on the affected Node for issues with the Kubelet.
   ```sh
   journalctl -u kubelet
   ```

4. **Check Disk Space and Memory:**
   Ensure the Node has sufficient resources.
   ```sh
   df -h
   free -m
   ```

5. **Check Network Connectivity:**
   Ensure the Node can communicate with the control plane and other nodes.
   ```sh
   ping <control-plane-ip>
   ```

6. **Check Node Conditions:**
   Verify conditions like `MemoryPressure`, `DiskPressure`, or `NetworkUnavailable`.
   ```sh
   kubectl describe node <node-name> | grep -i condition -A 10
   ```

7. **Example Solution:**

   - **Issue:** The Node is experiencing `DiskPressure`.
   - **Solution:** Free up disk space on the Node.

   **Steps to Free Up Disk Space:**
   - Remove unused Docker images.
     ```sh
     docker system prune -a
     ```
   - Clean up orphaned volumes.
     ```sh
     docker volume prune
     ```
