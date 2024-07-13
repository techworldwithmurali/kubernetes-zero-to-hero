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

1. Update EKS Control Plane
2. Update the Worker node versions
3. Validate the both EKS cluster and worker nodes
4. Validate the Kubernetes add-ons running properly or not
5. Validate the metric server, cluster autoscaler pods are running or not 
6. Validate the applications are working as we expected or not
7. Inform to application to validate the applications therir end.
8. WE have to monitor couple of days and if we get any issue needs to fix it 
