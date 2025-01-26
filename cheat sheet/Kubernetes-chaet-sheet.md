| **Kubernetes Object**       | **Command**                          | **Description**                               |
|--------------------|--------------------------------------|-----------------------------------------------|
| **Node Commands**   | `kubectl get nodes`                  | List all nodes in the cluster                |
|                    | `kubectl describe node <node-name>`  | Get detailed info about a specific node       |
|                    | `kubectl cordon <node-name>`         | Mark node as unschedulable                    |
|                    | `kubectl uncordon <node-name>`       | Mark node as schedulable                      |
| **Cluster Commands**| `kubectl cluster-info`               | Display cluster information                  |
|                    | `kubectl get clusterroles`           | List all cluster roles                       |
|                    | `kubectl describe clusterrole <role-name>` | Describe a specific cluster role              |
| **Cluster Connect**    | `kubectl config use-context <context-name>`                                 | Switch to a specific cluster context               |
|                       | `kubectl config get-contexts`                                               | List all available contexts in the kubeconfig file |
| **EKS Kubeconfig**     | `aws eks update-kubeconfig --region <region> --name <cluster-name>`         | Updates the kubeconfig file for AWS EKS clusters   |
| **Pod**                      | `kubectl get pods`                                      | Lists all pods in the current namespace.                                      |
|                             | `kubectl describe pod <pod-name>`                       | Provides detailed information about the specified pod.                        |
|                             | `kubectl logs <pod-name>`                               | Fetches the logs of the specified pod.                                        |
|                             | `kubectl delete pod <pod-name>`                         | Deletes the specified pod from the cluster.                                   |
| **Deployment**               | `kubectl get deployments`                              | Lists all deployments in the current namespace.                               |
|                             | `kubectl describe deployment <deployment-name>`         | Shows detailed information about the specified deployment.                   |
|                             | `kubectl rollout status deployment/<deployment-name>`   | Displays the rollout status of a deployment.                                  |
|                             | `kubectl scale deployment <deployment-name> --replicas=<num>` | Scales the deployment to the specified number of replicas.                 |
| **Service**                  | `kubectl get services`                                 | Lists all services in the current namespace.                                  |
|                             | `kubectl describe service <service-name>`               | Displays detailed information about the specified service.                   |
|                             | `kubectl expose pod <pod-name> --port=<port>`           | Exposes a pod by creating a service to access the pod via the specified port. |
| **ReplicaSet**               | `kubectl get replicasets`                              | Lists all replicasets in the current namespace.                              |
|                             | `kubectl describe replicaset <replicaset-name>`         | Provides detailed information about the specified replicaset.                |
|                             | `kubectl scale replicaset <replicaset-name> --replicas=<num>` | Scales the number of replicas for the replicaset.                           |
| **StatefulSet**              | `kubectl get statefulsets`                             | Lists all statefulsets in the current namespace.                             |
|                             | `kubectl describe statefulset <statefulset-name>`       | Shows detailed information about the specified statefulset.                  |
|                             | `kubectl scale statefulset <statefulset-name> --replicas=<num>` | Scales the number of replicas for the statefulset.                          |
| **DaemonSet**                | `kubectl get daemonsets`                               | Lists all daemonsets in the current namespace.                               |
|                             | `kubectl describe daemonset <daemonset-name>`           | Displays detailed information about the specified daemonset.                 |
|                             | `kubectl delete daemonset <daemonset-name>`             | Deletes the specified daemonset from the cluster.                            |
| **Job**                      | `kubectl get jobs`                                     | Lists all jobs in the current namespace.                                     |
|                             | `kubectl describe job <job-name>`                       | Provides detailed information about the specified job.                       |
|                             | `kubectl delete job <job-name>`                         | Deletes the specified job.                                                   |
|                             | `kubectl logs job/<job-name>`                           | Fetches logs from the pods created by the job.                               |
| **CronJob**                  | `kubectl get cronjobs`                                 | Lists all cronjobs in the current namespace.                                 |
|                             | `kubectl describe cronjob <cronjob-name>`               | Displays detailed information about the specified cronjob.                   |
|                             | `kubectl delete cronjob <cronjob-name>`                 | Deletes the specified cronjob.                                               |
| **Namespace**                | `kubectl get namespaces`                               | Lists all namespaces in the cluster.                                         |
|                             | `kubectl describe namespace <namespace-name>`           | Shows detailed information about the specified namespace.                    |
|                             | `kubectl delete namespace <namespace-name>`             | Deletes the specified namespace and its resources.                           |
| **ConfigMap**                | `kubectl get configmaps`                               | Lists all configmaps in the current namespace.                               |
|                             | `kubectl describe configmap <configmap-name>`           | Displays detailed information about the specified configmap.                 |
|                             | `kubectl delete configmap <configmap-name>`             | Deletes the specified configmap.                                             |
| **Secret**                   | `kubectl get secrets`                                  | Lists all secrets in the current namespace.                                  |
|                             | `kubectl describe secret <secret-name>`                 | Displays detailed information about the specified secret.                    |
|                             | `kubectl delete secret <secret-name>`                   | Deletes the specified secret.                                                |
| **PersistentVolume (PV)**    | `kubectl get pv`                                       | Lists all persistent volumes in the cluster.                                 |
|                             | `kubectl describe pv <pv-name>`                         | Displays detailed information about the specified persistent volume.          |
|                             | `kubectl delete pv <pv-name>`                           | Deletes the specified persistent volume.                                      |
| **PersistentVolumeClaim (PVC)** | `kubectl get pvc`                                     | Lists all persistent volume claims in the current namespace.                 |
|                             | `kubectl describe pvc <pvc-name>`                       | Displays detailed information about the specified PVC.                       |
|                             | `kubectl delete pvc <pvc-name>`                         | Deletes the specified PVC.                                                  |
| **Ingress**                  | `kubectl get ingress`                                   | Lists all ingresses in the current namespace.                                |
|                             | `kubectl describe ingress <ingress-name>`               | Displays detailed information about the specified ingress.                   |
|                             | `kubectl delete ingress <ingress-name>`                 | Deletes the specified ingress.                                              |
| **HorizontalPodAutoscaler (HPA)** | `kubectl get hpa`                                   | Lists all horizontal pod autoscalers in the current namespace.              |
|                             | `kubectl describe hpa <hpa-name>`                       | Displays detailed information about the specified HPA.                       |
|                             | `kubectl delete hpa <hpa-name>`                         | Deletes the specified HPA.                                                  |
| **PodDisruptionBudget (PDB)** | `kubectl get pdb`                                      | Lists all pod disruption budgets in the current namespace.                  |
|                             | `kubectl describe pdb <pdb-name>`                       | Displays detailed information about the specified pod disruption budget.     |
|                             | `kubectl delete pdb <pdb-name>`                         | Deletes the specified pod disruption budget.                                 |
| **NetworkPolicy**            | `kubectl get networkpolicies`                           | Lists all network policies in the current namespace.                         |
|                             | `kubectl describe networkpolicy <networkpolicy-name>`   | Displays detailed information about the specified network policy.           |
|                             | `kubectl delete networkpolicy <networkpolicy-name>`     | Deletes the specified network policy.                                        |
| **CustomResourceDefinition (CRD)** | `kubectl get crds`                                  | Lists all custom resource definitions in the cluster.                        |
|                             | `kubectl describe crd <crd-name>`                      | Provides detailed information about the specified CRD.                       |
|                             | `kubectl delete crd <crd-name>`                        | Deletes the specified CRD from the cluster.                                  |
| **ServiceAccount**           | `kubectl get serviceaccounts`                           | Lists all service accounts in the current namespace.                        |
|                             | `kubectl describe serviceaccount <serviceaccount-name>` | Displays detailed information about the specified service account.           |
|                             | `kubectl delete serviceaccount <serviceaccount-name>`   | Deletes the specified service account from the cluster.                      |
| **Role**                     | `kubectl get roles`                                    | Lists all roles in the current namespace.                                    |
|                             | `kubectl describe role <role-name>`                     | Displays detailed information about the specified role.                      |
|                             | `kubectl delete role <role-name>`                       | Deletes the specified role from the current namespace.                       |
| **RoleBinding**              | `kubectl get rolebindings`                             | Lists all role bindings in the current namespace.                            |
|                             | `kubectl describe rolebinding <rolebinding-name>`       | Displays detailed information about the specified role binding.              |
|                             | `kubectl delete rolebinding <rolebinding-name>`         | Deletes the specified role binding from the cluster.                         |
| **ClusterRole**              | `kubectl get clusterroles`                              | Lists all cluster roles in the cluster.                                      |
|                             | `kubectl describe clusterrole <clusterrole-name>`       | Displays detailed information about the specified cluster role.              |
|                             | `kubectl delete clusterrole <clusterrole-name>`         | Deletes the specified cluster role from the cluster.                         |
| **ClusterRoleBinding**       | `kubectl get clusterrolebindings`                       | Lists all cluster role bindings in the cluster.                              |
|                             | `kubectl describe clusterrolebinding <clusterrolebinding-name>` | Displays detailed information about the specified cluster role binding. |
|                             | `kubectl delete clusterrolebinding <clusterrolebinding-name>` | Deletes the specified cluster role binding from the cluster. |
| **Endpoint**                 | `kubectl get endpoints`                                 | Lists all endpoints in the current namespace.                                |
|                             | `kubectl describe endpoints <endpoints-name>`           | Displays detailed information about the specified endpoints.                 |
|                             | `kubectl delete endpoints <endpoints-name>`             | Deletes the specified endpoints from the cluster.                            |
| **Volume**                   | `kubectl get volumes`                                   | Lists all volumes in the cluster.                                            |
|                             | `kubectl describe volume <volume-name>`                 | Displays detailed information about the specified volume.                    |
|                             | `kubectl delete volume <volume-name>`                   | Deletes the specified volume from the cluster.                               |
| **HorizontalPodAutoscaler (HPA)** | `kubectl get hpa`                                   | Lists all horizontal pod autoscalers in the current namespace.              |
|                             | `kubectl describe hpa <hpa-name>`                       | Displays detailed information about the specified HPA.                       |
|                             | `kubectl delete hpa <hpa-name>`                         | Deletes the specified HPA.                                                  |
| **PodSecurityPolicy (PSP)**  | `kubectl get psp`                                      | Lists all pod security policies in the cluster.                              |
|                             | `kubectl describe psp <psp-name>`                       | Displays detailed information about the specified pod security policy.       |
|                             | `kubectl delete psp <psp-name>`                         | Deletes the specified pod security policy.                                   |
| **APIResource**              | `kubectl api-resources`                                | Lists all available API resources (objects) in the cluster.                  |
| **LimitRange**               | `kubectl get limitranges`                               | Lists all limit ranges in the current namespace.                             |
|                             | `kubectl describe limitrange <limitrange-name>`         | Displays detailed information about the specified limit range.              |
|                             | `kubectl delete limitrange <limitrange-name>`           | Deletes the specified limit range from the namespace.                        |
| **PriorityClass**            | `kubectl get priorityclass`                             | Lists all priority classes in the cluster.                                   |
|                             | `kubectl describe priorityclass <priorityclass-name>`   | Displays detailed information about the specified priority class.           |
|                             | `kubectl delete priorityclass <priorityclass-name>`     | Deletes the specified priority class from the cluster.                       |
| **ResourceQuota**            | `kubectl get resourcequotas`                            | Lists all resource quotas in the current namespace.                          |
|                             | `kubectl describe resourcequota <resourcequota-name>`   | Displays detailed information about the specified resource quota.           |
|                             | `kubectl delete resourcequota <resourcequota-name>`     | Deletes the specified resource quota from the namespace.                     |
| **ReplicaSet**               | `kubectl get replicasets`                              | Lists all replicasets in the current namespace.                              |
|                             | `kubectl describe replicaset <replicaset-name>`         | Provides detailed information about the specified replicaset.                |
|                             | `kubectl delete replicaset <replicaset-name>`           | Deletes the specified replicaset from the cluster.                           |
| **PodTemplate**              | `kubectl get podtemplates`                              | Lists all pod templates in the current namespace.                            |
|                             | `kubectl describe podtemplate <podtemplate-name>`       | Displays detailed information about the specified pod template.             |
|                             | `kubectl delete podtemplate <podtemplate-name>`         | Deletes the specified pod template from the cluster.                         |
| **NamespaceQuota**           | `kubectl get namespacequotas`                           | Lists all namespace quotas in the cluster.                                  |
|                             | `kubectl describe namespacequota <namespacequota-name>` | Displays detailed information about the specified namespace quota.          |
|                             | `kubectl delete namespacequota <namespacequota-name>`   | Deletes the specified namespace quota from the cluster.                      |
