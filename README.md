### Checklist for Preparing for an Amazon Elastic Kubernetes Service (EKS) Upgrade

Preparing for an EKS upgrade involves several critical steps to ensure a smooth transition. This checklist covers all the necessary preparations:

#### 1. Review EKS Release Notes
- **Action**: Read the release notes for the new EKS version to understand new features, bug fixes, and potential breaking changes.
- **Importance**: Helps in identifying changes that might impact your current setup.

#### 2. Backup Important Resources
- **Action**: Backup your Kubernetes manifests, configurations, and any persistent data.
- **Importance**: Ensures you can recover if something goes wrong during the upgrade.

#### 3. Review Customizations and Applications
- **Action**: Audit custom scripts, CRDs, and application configurations.
- **Importance**: Ensures compatibility with the new Kubernetes version.

#### 4. Check Node Groups and Launch Templates
- **Action**: Verify that your node groups and launch templates are up-to-date and compatible with the new EKS version.
- **Importance**: Ensures that worker nodes can be updated without issues.

#### 5. Test in a Non-Production Environment
- **Action**: Perform the upgrade in a staging or test environment first.
- **Importance**: Allows you to identify and fix issues without affecting production.

#### 6. Update eksctl or AWS CLI
- **Action**: Ensure that `eksctl` or AWS CLI is updated to the latest version.
- **Importance**: Ensures compatibility with the new EKS features and commands.

#### 7. Consider Cluster Autoscaler and HPA
- **Action**: Review and update the configurations for Cluster Autoscaler and Horizontal Pod Autoscaler (HPA).
- **Importance**: Ensures autoscaling functionalities are not disrupted.

#### 8. Update IAM Roles and Permissions
- **Action**: Check and update IAM roles and permissions to ensure they include any new policies required by the new EKS version.
- **Importance**: Prevents permission-related issues during and after the upgrade.

#### 9. Check Network Configurations
- **Action**: Verify network configurations such as VPC, subnets, and route tables.
- **Importance**: Ensures networking remains stable and secure.

#### 10. Review Security Groups and Firewalls
- **Action**: Ensure that security groups and firewall rules are correctly configured and compatible with the new EKS version.
- **Importance**: Maintains cluster security.

#### 11. Monitor Cluster Health
- **Action**: Monitor the current health of the cluster using tools like CloudWatch, Prometheus, and Grafana.
- **Importance**: Identifies existing issues before the upgrade.

#### 12. Communicate with the Team
- **Action**: Inform your team about the upgrade schedule and potential impacts.
- **Importance**: Ensures everyone is aware and prepared.

#### 13. Document the Upgrade Process
- **Action**: Document each step of the upgrade process.
- **Importance**: Provides a reference for troubleshooting and future upgrades.

#### 14. Rollback Plan
- **Action**: Prepare a rollback plan in case the upgrade fails.
- **Importance**: Ensures you can revert to the previous state if needed.

#### 15. Perform the Upgrade
- **Action**: Follow the documented steps to perform the upgrade.
- **Importance**: Executes the upgrade systematically.

#### 16. Post-Upgrade Testing
- **Action**: Conduct thorough testing of your applications and cluster components.
- **Importance**: Ensures everything is functioning correctly after the upgrade.

#### 17. Monitor and Optimize
- **Action**: Continuously monitor the cluster post-upgrade and optimize configurations as needed.
- **Importance**: Maintains cluster performance and stability.

### Lab Session - Upgrading AWS EKS

#### Step 1: Update EKS Control Plane

1. **Check Current Version**:
   ```bash
   aws eks describe-cluster --name <cluster-name> --query cluster.version --output text
   ```

2. **Update EKS Cluster**:
   - Initiate the update of the control plane to a new Kubernetes version. Replace `<cluster-name>` and `<new-k8s-version>` with appropriate values.

   ```bash
   aws eks update-cluster-version --name <cluster-name> --kubernetes-version <new-k8s-version>
   ```

3. **Monitor the Upgrade Process**:
   - The upgrade process can take some time. Monitor the status of the upgrade.

   ```bash
   aws eks describe-cluster --name <cluster-name> --query cluster.status --output text
   ```

4. **Verify Control Plane Upgrade**:
   - Once the control plane upgrade is complete, verify the new version.

   ```bash
   aws eks describe-cluster --name <cluster-name> --query cluster.version --output text
   ```

#### Step 2: Update Worker Nodes

1. **Update Node Group Configuration**:
   - Create a new Launch Template or update the existing one with the new AMI ID that corresponds to the new Kubernetes version.

2. **Update Managed Node Group**:
   - For managed node groups, initiate the update to use the new AMI.

   ```bash
   aws eks update-nodegroup-version --cluster-name <cluster-name> --nodegroup-name <nodegroup-name> --release-version <new-eks-release-version>
   ```

3. **Verify Node Group Update**:
   - Check the status of the node group update.

   ```bash
   aws eks describe-nodegroup --cluster-name <cluster-name> --nodegroup-name <nodegroup-name> --query updateStatus --output text
   ```

4. **Drain and Terminate Old Nodes**:
   - Drain the old nodes to move workloads to new nodes, then terminate the old nodes.

   ```bash
   kubectl drain <old-node-name> --ignore-daemonsets --delete-local-data
   aws autoscaling terminate-instance-in-auto-scaling-group --instance-id <instance-id> --should-decrement-desired-capacity
   ```

5. **Verify Node Replacement**:
   - Ensure new nodes are up and running, and workloads are running as expected.

   ```bash
   kubectl get nodes
   kubectl get pods --all-namespaces
   ```

#### Step 3: Validate the Upgrade

1. **Check Cluster Health**:
   - Ensure all nodes are in a ready state and no pods are in a crash loop or pending state.

   ```bash
   kubectl get nodes
   kubectl get pods --all-namespaces
   ```

2. **Run Functional Tests**:
   - Run your application tests to ensure that everything is working as expected after the upgrade.

### Conclusion

Upgrading an EKS cluster involves several steps, from updating the control plane to upgrading the worker nodes. Proper preparation and careful execution of each step will help ensure a smooth upgrade process. Make sure to monitor the cluster throughout the upgrade and validate the functionality of your applications post-upgrade.
