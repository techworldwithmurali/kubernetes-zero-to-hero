### What is RBAC in Kubernetes?

RBAC stands for Role-Based Access Control. It is a Kubernetes feature that allows you to control access to the Kubernetes API resources based on roles assigned to users or groups.

### RBAC components:

1. **Roles**: A Role is a set of permissions that define actions a user or group can perform within a namespace.

2. **RoleBindings**: A RoleBinding binds a Role to a user or group within a namespace, granting the permissions defined in the Role.

3. **ClusterRoles**: Similar to Roles but are cluster-wide and can be used to grant permissions across all namespaces.

4. **ClusterRoleBindings**: Bind ClusterRoles to users or groups, granting cluster-wide permissions.

### What is Role and RoleBinding in Kubernetes

- **Role**: Defines a set of permissions within a namespace, specifying what actions can be performed on which resources.

- **RoleBinding**: Binds a Role to a user or group within a namespace, allowing them to perform the actions specified in the Role.

### Lab Session - Creating and testing Roles and RoleBindings

#### Step 1: Create a Role

Create a file named `pod-reader-role.yaml` with the following content:

```yaml
kind: Role
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  namespace: default
  name: pod-reader
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "list"]
```

Apply the Role:

```bash
kubectl apply -f pod-reader-role.yaml
```

#### Step 2: Create a RoleBinding

Create a file named `pod-reader-rolebinding.yaml` with the following content:

```yaml
kind: RoleBinding
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: pod-reader-binding
  namespace: default
subjects:
- kind: User
  name: <username>
  apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: Role
  name: pod-reader
  apiGroup: rbac.authorization.k8s.io
```

Replace `<username>` with the actual Kubernetes username.

Apply the RoleBinding:

```bash
kubectl apply -f pod-reader-rolebinding.yaml
```

#### Step 3: Test Role and RoleBinding

Verify that the user can list pods:

```bash
kubectl auth can-i list pods --as <username>
```

### What are ClusterRoles and ClusterRoleBindings

- **ClusterRoles**: Similar to Roles but apply across the entire Kubernetes cluster, not limited to a specific namespace.

- **ClusterRoleBindings**: Bind ClusterRoles to users or groups, granting them cluster-wide permissions.

### Lab Session - Creating and testing ClusterRoles and ClusterRoleBindings

#### Step 1: Create a ClusterRole

Create a file named `cluster-pod-reader-role.yaml` with the following content:

```yaml
kind: ClusterRole
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: cluster-pod-reader
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "list"]
```

Apply the ClusterRole:

```bash
kubectl apply -f cluster-pod-reader-role.yaml
```

#### Step 2: Create a ClusterRoleBinding

Create a file named `cluster-pod-reader-rolebinding.yaml` with the following content:

```yaml
kind: ClusterRoleBinding
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: cluster-pod-reader-binding
subjects:
- kind: User
  name: <username>
  apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: ClusterRole
  name: cluster-pod-reader
  apiGroup: rbac.authorization.k8s.io
```

Replace `<username>` with the actual Kubernetes username.

Apply the ClusterRoleBinding:

```bash
kubectl apply -f cluster-pod-reader-rolebinding.yaml
```

#### Step 3: Test ClusterRole and ClusterRoleBinding

Verify that the user can list pods across all namespaces:

```bash
kubectl auth can-i list pods --as <username> --all-namespaces
```

### Summary

RBAC in Kubernetes allows fine-grained control over access to API resources through Roles and ClusterRoles, bound to users or groups via RoleBindings and ClusterRoleBindings respectively. These lab sessions provide practical experience in creating, applying, and testing these RBAC components to manage access within Kubernetes clusters effectively.
