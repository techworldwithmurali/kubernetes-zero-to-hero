### 1. What is the primary purpose of Helm in Kubernetes?

A. To manage Docker containers  
B. To automate the installation and management of Kubernetes applications  
C. To monitor Kubernetes clusters  
D. To deploy servers

**Correct Answer:** B. To automate the installation and management of Kubernetes applications  
**Explanation:** Helm is used to define, install, and upgrade Kubernetes applications using Helm charts.

---

### 2. What is a Helm chart?

A. A collection of Kubernetes configurations packaged together  
B. A tool for managing Kubernetes services  
C. A specific type of Docker container  
D. A type of Kubernetes storage

**Correct Answer:** A. A collection of Kubernetes configurations packaged together  
**Explanation:** A Helm chart is a package of pre-configured Kubernetes resources, including deployments, services, and configuration files.

---

### 3. Which Helm command is used to install a chart?

A. helm deploy  
B. helm add  
C. helm install  
D. helm upgrade

**Correct Answer:** C. helm install  
**Explanation:** `helm install` is used to install a Helm chart onto a Kubernetes cluster.

---

### 4. How do you upgrade a release in Helm?

A. helm update  
B. helm upgrade  
C. helm modify  
D. helm apply

**Correct Answer:** B. helm upgrade  
**Explanation:** `helm upgrade` is used to upgrade a previously deployed Helm release to a new version.

---

### 5. What is the purpose of Helm’s values.yaml file?

A. To define which charts to install  
B. To configure global settings for Kubernetes clusters  
C. To provide default values for a Helm chart’s templates  
D. To define user permissions

**Correct Answer:** C. To provide default values for a Helm chart’s templates  
**Explanation:** The `values.yaml` file is used to define the configuration values for a Helm chart's templates.

---

### 6. How do you list all Helm releases in a Kubernetes cluster?

A. helm show releases  
B. helm list  
C. helm show charts  
D. helm status

**Correct Answer:** B. helm list  
**Explanation:** `helm list` shows all the Helm releases in the current Kubernetes cluster.

---

### 7. Which of the following best describes a Helm release?

A. A configuration file used by Helm  
B. An instance of a chart running in the cluster  
C. A container image used by Helm  
D. A Kubernetes pod deployment

**Correct Answer:** B. An instance of a chart running in the cluster  
**Explanation:** A Helm release is an instance of a Helm chart deployed to a Kubernetes cluster.

---

### 8. What does the Helm rollback command do?

A. Reverts a chart to a previous version  
B. Removes a deployed chart  
C. Restores the Helm configuration  
D. Updates the Kubernetes cluster

**Correct Answer:** A. Reverts a chart to a previous version  
**Explanation:** `helm rollback` reverts a Helm release to a previous version.

---

### 9. What is Helm’s Tiller component?

A. A Kubernetes extension for Helm  
B. A command-line tool used to manage Kubernetes resources  
C. A server-side component that manages Helm releases (deprecated in Helm 3)  
D. A tool for monitoring Helm charts

**Correct Answer:** C. A server-side component that manages Helm releases (deprecated in Helm 3)  
**Explanation:** Tiller was used in Helm 2 to manage releases, but it has been deprecated in Helm 3 in favor of direct client-side interactions.

---

### 10. Which command is used to delete a Helm release?

A. helm remove  
B. helm delete  
C. helm uninstall  
D. helm purge

**Correct Answer:** B. helm delete  
**Explanation:** `helm delete` is used to remove a deployed Helm release from a Kubernetes cluster.

---

### 11. Which of the following Helm commands helps you validate the templates of a Helm chart?

A. helm validate  
B. helm template  
C. helm check  
D. helm debug

**Correct Answer:** B. helm template  
**Explanation:** `helm template` renders the Helm chart templates locally and is useful for debugging and validating.

---

### 12. What is the purpose of the `helm repo` command?

A. To initialize a new Helm chart repository  
B. To manage Helm chart repositories  
C. To display Helm chart details  
D. To add a new release

**Correct Answer:** B. To manage Helm chart repositories  
**Explanation:** `helm repo` is used to add, list, and manage Helm chart repositories.

---

### 13. How do you package a Helm chart for distribution?

A. helm create  
B. helm generate  
C. helm bundle  
D. helm package

**Correct Answer:** D. helm package  
**Explanation:** `helm package` is used to package a Helm chart into a `.tgz` file for distribution.

---

### 14. Which command can be used to update Helm chart dependencies?

A. helm dependencies update  
B. helm chart upgrade  
C. helm upgrade dependencies  
D. helm repo update

**Correct Answer:** A. helm dependencies update  
**Explanation:** `helm dependencies update` is used to update any chart dependencies.

---

### 15. What file is typically used to define dependencies in a Helm chart?

A. charts.yaml  
B. dependencies.yaml  
C. Chart.yaml  
D. values.yaml

**Correct Answer:** C. Chart.yaml  
**Explanation:** `Chart.yaml` defines the metadata and dependencies of a Helm chart.

---

### 16. Which Helm command provides information about a specific release?

A. helm describe  
B. helm inspect  
C. helm show  
D. helm status

**Correct Answer:** D. helm status  
**Explanation:** `helm status` provides detailed information about a specific Helm release.

---

### 17. What is the purpose of the `helm lint` command?

A. To run a security scan on a Helm chart  
B. To list all charts in the local repository  
C. To check the syntax and validity of a Helm chart  
D. To install a chart into a Kubernetes cluster

**Correct Answer:** C. To check the syntax and validity of a Helm chart  
**Explanation:** `helm lint` is used to check the syntax and validity of a Helm chart before installing it.

---

### 18. How can you specify custom values for a Helm chart during installation?

A. helm install -f custom_values.yaml  
B. helm install --values custom_values.yaml  
C. helm install --config custom_values.yaml  
D. helm install -v custom_values.yaml

**Correct Answer:** B. helm install --values custom_values.yaml  
**Explanation:** `--values` or `-f` is used to specify custom values during chart installation.

---

### 19. Which of the following statements is true about Helm charts?

A. Helm charts are always written in YAML format  
B. Helm charts can only be used with Kubernetes  
C. Helm charts are used to create Docker images  
D. Helm charts are a collection of Kubernetes resource definitions

**Correct Answer:** D. Helm charts are a collection of Kubernetes resource definitions  
**Explanation:** Helm charts contain Kubernetes resource definitions that define how to deploy and manage applications.

---

### 20. What is the default namespace when deploying a Helm chart?

A. kube-system  
B. default  
C. helm  
D. kube-apps

**Correct Answer:** B. default  
**Explanation:** By default, Helm installs charts into the `default` namespace unless specified otherwise.

---

### 21. How do you retrieve the manifest of a Helm chart?

A. helm render  
B. helm show manifest  
C. helm get manifest  
D. helm template

**Correct Answer:** D. helm template  
**Explanation:** `helm template` generates and prints the manifest of a chart locally without installing it.

---

### 22. What is the purpose of the `helm upgrade --install` command?

A. It upgrades an existing release or installs the release if it doesn’t exist  
B. It only installs a chart  
C. It upgrades a chart but does not install it  
D. It installs a chart in a specific namespace

**Correct Answer:** A. It upgrades an existing release or installs the release if it doesn’t exist  
**Explanation:** `helm upgrade --install` allows you to upgrade an existing release, or install the release if it doesn’t exist.

---

### 23. What is a Helm repository?

A. A storage location for Helm charts  
B. A Kubernetes resource type  
C. A type of Kubernetes deployment  
D. A tool for monitoring Kubernetes applications

**Correct Answer:** A. A storage location for Helm charts  
**Explanation:** A Helm repository is a location where Helm charts are stored and can be downloaded for installation.

---

### 24. How do you add a new Helm chart repository?

A. helm add repository  
B. helm repo add  
C. helm chart add  
D. helm create repository

**Correct Answer:** B. helm repo add  
**Explanation:** `helm repo add` is used to add a new chart repository to Helm.

---

### 25. What is a chart template in Helm?

A. A pre-configured Helm installation script  
B. A reusable component to define Kubernetes resources  
C. A configuration file used for security policies  
D. A type of Kubernetes deployment object

**Correct Answer:** B. A reusable component to define Kubernetes resources  
**Explanation:** Chart templates in Helm define the Kubernetes resources that are deployed when the chart is installed.

---

### 26. Which command in Helm is used to view detailed information about a chart?

A. helm details  
B. helm show  
C. helm inspect  
D. helm get

**Correct Answer:** B. helm show  
**Explanation:** `helm show` displays detailed information about a Helm chart, including its contents and metadata.

---

### 27. Which command helps you search for charts in the Helm repository?

A. helm search  
B. helm lookup  
C. helm find  
D. helm locate

**Correct Answer:** A. helm search  
**Explanation:** `helm search` is used to search for available charts in the Helm repository.

---

### 28. Which of the following is a key feature of Helm?

A. Automating Kubernetes deployments  
B. Managing Docker containers  
C. Providing cloud infrastructure  
D. Creating Kubernetes clusters

**Correct Answer:** A. Automating Kubernetes deployments  
**Explanation:** Helm automates the deployment and management of applications on Kubernetes clusters.

---
### 29. How do you create a new Helm chart?

A. helm new  
B. helm create  
C. helm generate  
D. helm start

**Correct Answer:** B. helm create  
**Explanation:** `helm create` is used to create a new Helm chart with a default structure.

---

### 30. What command allows you to display information about a Helm chart repository?

A. helm repo show  
B. helm repo details  
C. helm repo list  
D. helm list repo

**Correct Answer:** C. helm repo list  
**Explanation:** `helm repo list` shows all the repositories added to Helm.

---

### 31. What is the purpose of a Helm release name?

A. It identifies the chart version  
B. It identifies the release of the chart in a Kubernetes cluster  
C. It defines the configuration file for the chart  
D. It specifies the deployment namespace

**Correct Answer:** B. It identifies the release of the chart in a Kubernetes cluster  
**Explanation:** The release name is a unique identifier for an instance of a Helm chart installed in a Kubernetes cluster.

---

### 32. How do you uninstall a release in Helm?

A. helm uninstall  
B. helm remove  
C. helm delete  
D. helm purge

**Correct Answer:** C. helm delete  
**Explanation:** `helm delete` is used to uninstall a release from the Kubernetes cluster.

---

### 33. How do you show detailed information about a specific Helm release?

A. helm release show  
B. helm get  
C. helm status  
D. helm describe

**Correct Answer:** C. helm status  
**Explanation:** `helm status` provides detailed information about a Helm release.

---

### 34. What is the role of `helm install --dry-run`?

A. Installs the chart without making any changes  
B. Simulates the installation to verify if it will succeed  
C. Creates a release without applying it  
D. Installs the chart but skips validating templates

**Correct Answer:** B. Simulates the installation to verify if it will succeed  
**Explanation:** `helm install --dry-run` simulates the installation to verify what changes would be applied without actually making them.

---

### 35. What file would you modify to override default chart values during installation?

A. Chart.yaml  
B. values.yaml  
C. config.yaml  
D. settings.yaml

**Correct Answer:** B. values.yaml  
**Explanation:** `values.yaml` is the configuration file where you can specify custom values for a chart during installation.

---

### 36. How do you check the status of a Helm release?

A. helm release status  
B. helm check  
C. helm status  
D. helm get status

**Correct Answer:** C. helm status  
**Explanation:** `helm status` is used to get the current status of a Helm release.

---

### 37. What is a Helm dependency?

A. A required chart that needs to be installed before the current chart  
B. A Kubernetes pod that Helm manages  
C. A specific container image needed by a chart  
D. A Helm command that installs other charts

**Correct Answer:** A. A required chart that needs to be installed before the current chart  
**Explanation:** Helm dependencies are charts that a current chart relies on in order to function properly.

---

### 38. What is the function of Helm’s `requirements.yaml` file?

A. It defines chart dependencies  
B. It stores values for configuration  
C. It specifies Kubernetes resources  
D. It describes the chart metadata

**Correct Answer:** A. It defines chart dependencies  
**Explanation:** The `requirements.yaml` file (deprecated in Helm 3, replaced with `Chart.yaml`) lists the dependencies for a Helm chart.

---

### 39. How do you remove a chart repository from Helm?

A. helm repo remove  
B. helm repo delete  
C. helm repo remove --name  
D. helm repo clean

**Correct Answer:** A. helm repo remove  
**Explanation:** `helm repo remove` removes a chart repository from Helm’s list of repositories.

---

### 40. What is the primary purpose of the `helm init` command?

A. To initialize the Helm client  
B. To install Helm Tiller (deprecated in Helm 3)  
C. To install a Helm chart  
D. To update Helm’s configuration

**Correct Answer:** B. To install Helm Tiller (deprecated in Helm 3)  
**Explanation:** `helm init` was used to install Tiller in Helm 2, but Helm 3 no longer uses Tiller.

---

### 41. How do you upgrade a Helm release to a specific version?

A. helm upgrade --version  
B. helm upgrade --to-version  
C. helm upgrade --set version  
D. helm upgrade --install <release_name> --version <version>

**Correct Answer:** D. helm upgrade --install <release_name> --version <version>  
**Explanation:** You can specify the version of a chart to upgrade to by using `helm upgrade --install <release_name> --version <version>`.

---

### 42. What does the `helm upgrade --force` command do?

A. Forces the upgrade even if there are errors  
B. Forces the reinstallation of the chart  
C. Forces a rollback of a Helm release  
D. Forces the deployment of a new chart version

**Correct Answer:** B. Forces the reinstallation of the chart  
**Explanation:** `helm upgrade --force` forces a reinstallation of the chart even if there are no changes in the chart.

---

### 43. How do you specify a custom namespace for Helm chart installation?

A. helm install --namespace  
B. helm install --set namespace  
C. helm install --namespace <namespace>  
D. helm install -n <namespace>

**Correct Answer:** C. helm install --namespace <namespace>  
**Explanation:** The `--namespace` flag is used to specify the namespace where the Helm chart should be installed.

---

### 44. Which Helm command will display the values of a specific Helm release?

A. helm values  
B. helm get values  
C. helm show values  
D. helm show release values

**Correct Answer:** B. helm get values  
**Explanation:** `helm get values` shows the configuration values of a deployed Helm release.

---

### 45. What is the use of `helm history`?

A. To view the history of Helm releases  
B. To view changes made to Helm charts  
C. To list all previous versions of a chart  
D. To list all Helm commands

**Correct Answer:** A. To view the history of Helm releases  
**Explanation:** `helm history` lists all previous versions of a Helm release and their associated metadata.

---

### 46. How can you get information about a specific Helm chart?

A. helm chart inspect  
B. helm get chart  
C. helm show chart  
D. helm search chart

**Correct Answer:** C. helm show chart  
**Explanation:** `helm show chart` displays detailed information about a specific Helm chart.

---

### 47. What is the significance of `Chart.yaml`?

A. It defines the dependencies for a Helm chart  
B. It provides the metadata and configuration for the Helm chart  
C. It stores Kubernetes resource definitions  
D. It holds custom user configurations

**Correct Answer:** B. It provides the metadata and configuration for the Helm chart  
**Explanation:** `Chart.yaml` contains the metadata and other information required for the Helm chart to function.

---

### 48. How do you add a new Helm chart version to an existing repository?

A. helm add version  
B. helm chart update  
C. helm repo update  
D. helm repo push

**Correct Answer:** C. helm repo update  
**Explanation:** `helm repo update` is used to refresh the repositories and add any new chart versions.

---

### 49. What does `helm dependency build` do?

A. Builds a Helm chart from its dependencies  
B. Installs chart dependencies  
C. Checks for missing chart dependencies  
D. Builds the Helm release

**Correct Answer:** B. Installs chart dependencies  
**Explanation:** `helm dependency build` installs the dependencies defined in the `Chart.yaml` file.

---

### 50. How do you view a list of all available Helm charts?

A. helm list charts  
B. helm search charts  
C. helm show charts  
D. helm list

**Correct Answer:** B. helm search charts  
**Explanation:** `helm search charts` lists all available charts in the Helm repositories.

---

### 51. How do you debug a Helm chart installation?

A. helm debug  
B. helm log  
C. helm install --debug  
D. helm check --debug

**Correct Answer:** C. helm install --debug  
**Explanation:** `helm install --debug` enables debug output during chart installation.

---

### 52. How do you install a Helm chart from a local directory?

A. helm install ./chart-name  
B. helm install local ./chart-name  
C. helm install chart ./chart-name  
D. helm install file ./chart-name

**Correct Answer:** A. helm install ./chart-name  
**Explanation:** `helm install ./chart-name` installs a Helm chart from a local directory.

---

### 53. Which of the following Helm commands is used to check the current configuration of a release?

A. helm get config  
B. helm status  
C. helm check  
D. helm values

**Correct Answer:** B. helm status  
**Explanation:** `helm status` provides details about the current configuration and state of a Helm release.

---

### 54. How can you specify a specific release version when upgrading?

A. helm upgrade --version <version>  
B. helm upgrade --release-version <version>  
C. helm upgrade --install <release_name> --version <version>  
D. helm upgrade <release_name> --version <version>

**Correct Answer:** C. helm upgrade --install <release_name> --version <version>  
**Explanation:** This command upgrades a Helm release to a specific version.

---

### 55. How do you retrieve a Helm chart’s source code?

A. helm show code  
B. helm get source  
C. helm pull  
D. helm fetch

**Correct Answer:** C. helm pull  
**Explanation:** `helm pull` retrieves a Helm chart’s source code or packaged chart.

---

### 56. How do you view the resources created by a Helm release?

A. helm show resources  
B. helm get resources  
C. helm status  
D. helm list resources

**Correct Answer:** C. helm status  
**Explanation:** `helm status` shows detailed information about the resources created by a specific Helm release.

---

### 57. What is the difference between `helm upgrade` and `helm install`?

A. `helm install` updates a release, while `helm upgrade` installs a new release  
B. `helm upgrade` applies changes to an existing release, while `helm install` installs a new release  
C. `helm install` creates a Helm chart, while `helm upgrade` installs the chart  
D. `helm upgrade` removes the existing release, while `helm install` installs it

**Correct Answer:** B. `helm upgrade` applies changes to an existing release, while `helm install` installs a new release  
**Explanation:** `helm upgrade` is used to modify an existing release, while `helm install` is used to deploy a new release.

---

### 58. How can you manually set values during the installation of a Helm chart?

A. helm install --set key=value  
B. helm set values --install  
C. helm values --set  
D. helm install --custom-values

**Correct Answer:** A. helm install --set key=value  
**Explanation:** The `--set` flag allows you to override values during chart installation.

---

### 59. How do you remove all Helm releases in a specific namespace?

A. helm delete --namespace <namespace>  
B. helm uninstall --namespace <namespace>  
C. helm purge --namespace <namespace>  
D. helm delete --all --namespace <namespace>

**Correct Answer:** A. helm delete --namespace <namespace>  
**Explanation:** `helm delete --namespace <namespace>` removes all releases in the specified namespace.

---

### 60. What command checks for updates to the Helm chart repositories?

A. helm update  
B. helm repo refresh  
C. helm repo update  
D. helm fetch --update

**Correct Answer:** C. helm repo update  
**Explanation:** `helm repo update` refreshes the Helm chart repositories to check for the latest charts and versions.

---

### 61. How can you specify a custom values file during chart installation?

A. helm install --values custom-values.yaml  
B. helm install --config custom-values.yaml  
C. helm install --file custom-values.yaml  
D. helm install -f custom-values.yaml

**Correct Answer:** D. helm install -f custom-values.yaml  
**Explanation:** The `-f` or `--values` flag is used to specify a custom values file.

---

### 62. What does the `helm show values` command do?

A. Displays the default values of a chart  
B. Displays the current configuration values for a release  
C. Displays detailed information about the chart  
D. Lists all possible values in the `values.yaml` file

**Correct Answer:** A. Displays the default values of a chart  
**Explanation:** `helm show values` displays the default values of a chart from the chart’s `values.yaml` file.

---

### 63. Which of the following is a valid Helm chart repository?

A. https://charts.helm.sh/stable  
B. https://helm-repos.local  
C. https://kubernetes-charts.io  
D. https://docker-charts.com

**Correct Answer:** A. https://charts.helm.sh/stable  
**Explanation:** `https://charts.helm.sh/stable` is the default Helm stable chart repository.

---

### 64. How do you display information about a Helm chart without installing it?

A. helm show  
B. helm info  
C. helm preview  
D. helm describe

**Correct Answer:** A. helm show  
**Explanation:** `helm show` displays information about a Helm chart without actually installing it.

---

### 65. How do you install a Helm chart from a specific version?

A. helm install --version <version>  
B. helm install --set version <version>  
C. helm install --version <chart_name>:<version>  
D. helm install <chart_name> --version <version>

**Correct Answer:** D. helm install <chart_name> --version <version>  
**Explanation:** You can specify the version of a chart to install by using `helm install <chart_name> --version <version>`.

---

### 66. What command is used to list all Helm repositories?

A. helm list repos  
B. helm repos  
C. helm repo list  
D. helm search repos

**Correct Answer:** C. helm repo list  
**Explanation:** `helm repo list` lists all the chart repositories added to Helm.

---

### 67. How can you set a timeout for a Helm release installation?

A. helm install --timeout <duration>  
B. helm install --wait --timeout <duration>  
C. helm set timeout <duration>  
D. helm install -t <duration>

**Correct Answer:** B. helm install --wait --timeout <duration>  
**Explanation:** `--wait` ensures that Helm waits until all resources are deployed, and `--timeout` specifies the time to wait before timing out.

---

### 68. What happens if you try to install a Helm release with a name that already exists?

A. Helm will overwrite the existing release  
B. Helm will throw an error  
C. Helm will ask for a confirmation to overwrite  
D. Helm will create a new release with a unique name

**Correct Answer:** B. Helm will throw an error  
**Explanation:** If you try to install a release with an existing name, Helm will throw an error unless you use `helm upgrade`.

---

### 69. How do you specify a value to be set in a Helm chart during an upgrade?

A. helm upgrade --set key=value  
B. helm upgrade --values custom-values.yaml  
C. helm upgrade --set <key>=<value>  
D. helm upgrade --config custom-values.yaml

**Correct Answer:** A. helm upgrade --set key=value  
**Explanation:** The `--set` flag is used during upgrades to specify values directly in the command.

---

### 70. How do you search for a specific Helm chart in a repository?

A. helm search charts <chart_name>  
B. helm find <chart_name>  
C. helm chart search <chart_name>  
D. helm search <chart_name>

**Correct Answer:** A. helm search charts <chart_name>  
**Explanation:** `helm search charts` followed by the chart name is used to search for a specific chart in the repository.

---

### 71. What is the purpose of `helm fetch`?

A. To download the latest chart version from a repository  
B. To install a chart from a repository  
C. To fetch a chart’s values.yaml  
D. To list all available charts

**Correct Answer:** A. To download the latest chart version from a repository  
**Explanation:** `helm fetch` downloads a chart, either from a remote repository or from a local directory.

---

### 72. How can you view the list of available Helm commands?

A. helm --help  
B. helm list commands  
C. helm help  
D. helm commands list

**Correct Answer:** C. helm help  
**Explanation:** `helm help` displays a list of available commands and their descriptions.

---

### 73. What is the purpose of the `helm install --dry-run` command?

A. To simulate the installation of a Helm chart  
B. To install the chart without applying any changes  
C. To install the chart without requiring a namespace  
D. To check for Helm configuration errors

**Correct Answer:** A. To simulate the installation of a Helm chart  
**Explanation:** `helm install --dry-run` simulates the installation of a Helm chart and shows what would happen without making changes.

---

### 74. Which command is used to view a Helm chart’s metadata?

A. helm show chart  
B. helm chart details  
C. helm metadata  
D. helm info

**Correct Answer:** A. helm show chart  
**Explanation:** `helm show chart` displays the metadata of a Helm chart.

---

### 75. How do you upgrade Helm to the latest version?

A. helm upgrade  
B. helm update  
C. helm repo update  
D. helm upgrade helm

**Correct Answer:** B. helm update  
**Explanation:** `helm update` is used to update the Helm CLI to the latest version.

---

### 76. How can you check if a Helm chart has been installed?

A. helm status <release_name>  
B. helm check <release_name>  
C. helm list --installed  
D. helm get <release_name>

**Correct Answer:** A. helm status <release_name>  
**Explanation:** `helm status <release_name>` checks the current status of a Helm release and confirms if it has been installed.

---

### 77. Which Helm command would you use to rollback a Helm release to a previous version?

A. helm rollback  
B. helm upgrade --rollback  
C. helm revert  
D. helm history

**Correct Answer:** A. helm rollback  
**Explanation:** `helm rollback` is used to revert a Helm release to a previous version.

---

### 78. How do you list the Helm releases in a specific namespace?

A. helm list --namespace <namespace>  
B. helm releases --namespace <namespace>  
C. helm list -n <namespace>  
D. helm list --ns <namespace>

**Correct Answer:** A. helm list --namespace <namespace>  
**Explanation:** `helm list --namespace <namespace>` lists all the Helm releases in the specified namespace.

---

### 79. How do you install a chart with specific values for a release?

A. helm install <release_name> --values <values_file>  
B. helm install --set <key>=<value>  
C. helm install --custom-values <values_file>  
D. helm install --config <values_file>

**Correct Answer:** A. helm install <release_name> --values <values_file>  
**Explanation:** `--values` or `-f` flag is used to specify a values file during chart installation.

---

### 80. How do you see all the available versions of a Helm chart?

A. helm search versions <chart_name>  
B. helm show versions <chart_name>  
C. helm chart list versions  
D. helm search <chart_name> --versions

**Correct Answer:** D. helm search <chart_name> --versions  
**Explanation:** `helm search <chart_name> --versions` shows all available versions of a Helm chart in the repository.

---

### 81. How can you check the history of a specific Helm release?

A. helm history <release_name>  
B. helm status <release_name>  
C. helm release history <release_name>  
D. helm list --history <release_name>

**Correct Answer:** A. helm history <release_name>  
**Explanation:** `helm history <release_name>` shows the history and versions of a particular Helm release.

---

### 82. How do you enable Helm to wait for resources to be fully deployed before completing installation?

A. helm install --wait  
B. helm install --deployment-wait  
C. helm install --check-status  
D. helm install --finalize

**Correct Answer:** A. helm install --wait  
**Explanation:** `--wait` ensures Helm waits for all resources to be deployed and become available before completing the installation.

---

### 83. What does the `helm repo index` command do?

A. Creates an index file for a Helm chart repository  
B. Lists all charts in a repository  
C. Adds a new chart to the index file  
D. Creates a Helm repository from a chart

**Correct Answer:** A. Creates an index file for a Helm chart repository  
**Explanation:** `helm repo index` is used to generate or update the index file for a Helm chart repository.

---

### 84. How do you specify a namespace for a Helm release if you are using Helm 3?

A. helm install --namespace <namespace>  
B. helm set namespace=<namespace>  
C. helm install --set namespace=<namespace>  
D. helm release --namespace <namespace>

**Correct Answer:** A. helm install --namespace <namespace>  
**Explanation:** Helm 3 uses `--namespace` to specify the namespace where the release will be deployed.

---

### 85. What does the `helm package` command do?

A. Packages a Helm chart into a compressed tarball  
B. Installs a packaged Helm chart  
C. Packages multiple charts into one  
D. Updates an existing Helm chart package

**Correct Answer:** A. Packages a Helm chart into a compressed tarball  
**Explanation:** `helm package` creates a `.tgz` package of a chart from its source directory.

---

### 86. How do you display the list of all installed Helm charts?

A. helm list  
B. helm show installed  
C. helm chart list  
D. helm search installed

**Correct Answer:** A. helm list  
**Explanation:** `helm list` shows all installed Helm releases in the cluster.

---

### 87. How can you modify a Helm chart's values without modifying the original `values.yaml` file?

A. Use `--values` to pass a custom values file  
B. Use `--set` to override specific values  
C. Use `--config` to provide custom configuration  
D. Both A and B

**Correct Answer:** D. Both A and B  
**Explanation:** You can use `--values` to specify a custom file or `--set` to override specific values on the command line.

---

### 88. How do you update the values of a running Helm release?

A. helm upgrade <release_name> --set key=value  
B. helm upgrade <release_name> --values <new_values_file>  
C. helm update <release_name> --set key=value  
D. Both A and B

**Correct Answer:** D. Both A and B  
**Explanation:** Both `--set` and `--values` can be used to update the values of a running Helm release.

---

### 89. Which Helm command is used to initialize Helm in a Kubernetes cluster?

A. helm setup  
B. helm init  
C. helm install  
D. helm deploy

**Correct Answer:** B. helm init  
**Explanation:** `helm init` was used in Helm 2 to initialize Helm and install Tiller. In Helm 3, Tiller is removed, and `helm init` is not needed.

---

### 90. How do you create a Helm chart from scratch?

A. helm generate  
B. helm new  
C. helm create  
D. helm init

**Correct Answer:** C. helm create  
**Explanation:** `helm create` generates a new chart with a basic structure and default files.

---

### 91. What is the purpose of the `values.yaml` file in a Helm chart?

A. It defines default values for a chart  
B. It stores Kubernetes resource definitions  
C. It provides metadata for the chart  
D. It contains instructions for Helm to run

**Correct Answer:** A. It defines default values for a chart  
**Explanation:** `values.yaml` is used to define default configuration values for a Helm chart that can be overridden during installation.

---

### 92. What is the main role of the Helm chart repository?

A. To store packaged charts and their metadata  
B. To store Kubernetes resource definitions  
C. To store Helm CLI tools  
D. To provide Helm Tiller support

**Correct Answer:** A. To store packaged charts and their metadata  
**Explanation:** Helm chart repositories are used to store Helm charts, their versions, and metadata.

---

### 93. What does the `helm template` command do?

A. It generates Kubernetes resource definitions from a Helm chart  
B. It installs the Helm chart into a Kubernetes cluster  
C. It displays the templates used in a Helm chart  
D. It packages a Helm chart for deployment

**Correct Answer:** A. It generates Kubernetes resource definitions from a Helm chart  
**Explanation:** `helm template` renders Kubernetes resources from a Helm chart without deploying them.

---

### 94. How do you specify a specific repository for a Helm chart?

A. helm install <chart_name> --repo <repository_url>  
B. helm install --repo <repository_url> <chart_name>  
C. helm add repo <repository_url> <chart_name>  
D. helm install <chart_name> --from <repository_url>

**Correct Answer:** B. helm install --repo <repository_url> <chart_name>  
**Explanation:** The `--repo` flag specifies the repository URL from which the chart should be installed.

---

### 95. How do you update the local repository cache?

A. helm repo refresh  
B. helm update cache  
C. helm repo update  
D. helm fetch --refresh

**Correct Answer:** C. helm repo update  
**Explanation:** `helm repo update` updates the cache for all repositories.

---

### 96. How can you install a Helm chart from a GitHub repository?

A. helm install --github <github_repo_url>  
B. helm install <chart_name> --url <github_repo_url>  
C. helm install --repo <github_repo_url>  
D. helm install <chart_name> --from <github_repo_url>

**Correct Answer:** C. helm install --repo <github_repo_url>  
**Explanation:** You can install a Helm chart from a GitHub repository by using the `--repo` flag with the repository URL.

---

### 97. What is the Helm Tiller component used for?

A. It stores the Helm charts  
B. It manages the deployment of Helm charts (deprecated in Helm 3)  
C. It helps in chart creation  
D. It serves as the chart repository

**Correct Answer:** B. It manages the deployment of Helm charts (deprecated in Helm 3)  
**Explanation:** Tiller was a server-side component in Helm 2 that managed the installation of Helm charts. Helm 3 has removed Tiller.

---

### 98. How can you remove a Helm chart repository from your configuration?

A. helm remove <repo_name>  
B. helm delete <repo_name>  
C. helm repo remove <repo_name>  
D. helm repo delete <repo_name>

**Correct Answer:** C. helm repo remove <repo_name>  
**Explanation:** `helm repo remove` removes a chart repository from your Helm configuration.

---

### 99. What does the `helm rollback` command do?

A. Reverts a Helm release to a previous configuration  
B. Uninstalls a release  
C. Reinstalls a release  
D. Upgrades a Helm release

**Correct Answer:** A. Reverts a Helm release to a previous configuration  
**Explanation:** `helm rollback` reverts the specified release to an earlier version.

---

### 100. How do you set the version of a Helm chart repository?

A. helm repo version <repo_name> --set <version>  
B. helm repo add <repo_name> --version <version>  
C. helm repo update --version <version>  
D. helm repo add <repo_name> <repo_url> --version <version>

**Correct Answer:** B. helm repo add <repo_name> --version <version>  
**Explanation:** You can specify a version when adding a repository using `helm repo add` followed by `--version`.

---

### 101. What does the `helm lint` command do?

A. Lints the chart's Kubernetes resources for syntax errors  
B. Lints the values.yaml file for invalid keys  
C. Lints the Helm chart to check for chart structure and formatting issues  
D. Lints a Helm release after installation

**Correct Answer:** C. Lints the Helm chart to check for chart structure and formatting issues  
**Explanation:** `helm lint` checks a Helm chart for any common errors or issues in its structure before installing it.

---

### 102. How do you test a Helm chart?

A. helm test <release_name>  
B. helm run test <chart_name>  
C. helm chart test <chart_name>  
D. helm verify <chart_name>

**Correct Answer:** A. helm test <release_name>  
**Explanation:** `helm test` runs any test hooks defined in a chart to validate its deployment after installation.

---

### 103. What is the purpose of Helm hooks?

A. To manage release dependencies  
B. To trigger actions at specific points in a release lifecycle  
C. To define custom values for a chart  
D. To manage Helm chart repositories

**Correct Answer:** B. To trigger actions at specific points in a release lifecycle  
**Explanation:** Helm hooks allow you to trigger certain actions at defined points in the release lifecycle, such as before installation, after upgrade, etc.

---

### 104. How do you ensure a Helm release is only deployed once?

A. helm install --unique  
B. helm install --one-time  
C. helm install --wait  
D. helm install --atomic

**Correct Answer:** D. helm install --atomic  
**Explanation:** The `--atomic` flag ensures that the release is only deployed once, and if any error occurs, the entire release is rolled back.

---

### 105. How can you get detailed information about a failed Helm release?

A. helm logs <release_name>  
B. helm describe <release_name>  
C. helm status <release_name>  
D. helm get logs <release_name>

**Correct Answer:** C. helm status <release_name>  
**Explanation:** `helm status <release_name>` provides detailed information about a release, including the reason for failure if the release failed.

---

### 106. What is the function of `helm history`?

A. Shows the history of installed charts  
B. Shows the history of Helm releases, including previous versions  
C. Lists the previous charts installed in a cluster  
D. Tracks the history of Helm repositories

**Correct Answer:** B. Shows the history of Helm releases, including previous versions  
**Explanation:** `helm history` shows the revision history of a specific release, including previous versions and any changes made.

---

### 107. How do you install a chart with specific values from a URL?

A. helm install <release_name> --url <chart_url>  
B. helm install <release_name> --repo <repo_url>  
C. helm install <release_name> --values <url_to_values_file>  
D. helm install --set-url <chart_url> <chart_name>

**Correct Answer:** C. helm install <release_name> --values <url_to_values_file>  
**Explanation:** You can specify a values file from a URL during installation using `--values`.

---

### 108. How do you list all the Helm charts available in a specific repository?

A. helm repo list <repo_name>  
B. helm search <repo_name>  
C. helm repo list  
D. helm search repo <repo_name>

**Correct Answer:** B. helm search <repo_name>  
**Explanation:** `helm search <repo_name>` searches for charts within a specific repository.

---

### 109. Can you install a Helm chart from a local directory?

A. Yes, using `helm install <chart_name> ./path_to_chart`  
B. No, charts can only be installed from a repository  
C. Yes, using `helm install <chart_name> --local <path_to_chart>`  
D. Yes, using `helm install --path <path_to_chart>`

**Correct Answer:** A. Yes, using `helm install <chart_name> ./path_to_chart`  
**Explanation:** You can install a Helm chart directly from a local directory by specifying the path to the chart.

---

### 110. How can you debug a Helm chart installation?

A. helm debug <release_name>  
B. helm install --debug  
C. helm install --verbose  
D. helm chart debug <chart_name>

**Correct Answer:** B. helm install --debug  
**Explanation:** The `--debug` flag provides detailed logs and information to help debug the installation process of a Helm chart.

---

### 111. How do you get the Helm chart's default values?

A. helm default values <chart_name>  
B. helm show default-values <chart_name>  
C. helm show values <chart_name>  
D. helm values <chart_name>

**Correct Answer:** C. helm show values <chart_name>  
**Explanation:** `helm show values <chart_name>` displays the default values for a Helm chart from the `values.yaml` file.

---

### 112. How can you view all the available releases for a specific namespace?

A. helm list --namespace <namespace>  
B. helm releases --namespace <namespace>  
C. helm list -n <namespace>  
D. helm releases -n <namespace>

**Correct Answer:** C. helm list -n <namespace>  
**Explanation:** `helm list -n <namespace>` lists all the releases in a given namespace.

---

### 113. How do you update the local Helm chart repository index?

A. helm repo update  
B. helm update repo  
C. helm sync repo  
D. helm fetch --index

**Correct Answer:** A. helm repo update  
**Explanation:** `helm repo update` updates the local repository cache, ensuring you have the latest chart versions.

---

### 114. How can you set a global value for all charts in a Helm release?

A. helm install --global <key>=<value>  
B. helm install --set-global <key>=<value>  
C. helm install --set <key>=<value>  
D. helm upgrade --global <key>=<value>

**Correct Answer:** C. helm install --set <key>=<value>  
**Explanation:** The `--set` flag is used to set values, and it can be used to set global values within the release.

---

### 115. What is the significance of the `Chart.yaml` file in a Helm chart?

A. It contains the values for the chart installation  
B. It defines the metadata for the chart  
C. It defines the Kubernetes resources  
D. It contains default values for the release

**Correct Answer:** B. It defines the metadata for the chart  
**Explanation:** `Chart.yaml` contains the metadata for a Helm chart, such as name, version, dependencies, etc.

---

### 116. Can you use Helm to install Kubernetes manifests directly?

A. Yes, using `helm install` with `--dry-run`  
B. No, Helm is only used for charts  
C. Yes, using `helm install` with `--manifest`  
D. Yes, using `helm template` to generate the manifest and then applying it manually

**Correct Answer:** D. Yes, using `helm template` to generate the manifest and then applying it manually  
**Explanation:** `helm template` renders Kubernetes manifests from a Helm chart without deploying them, which can then be applied directly.

---

### 117. How can you uninstall a Helm release and delete the associated Kubernetes resources?

A. helm delete --purge <release_name>  
B. helm uninstall <release_name>  
C. helm remove <release_name>  
D. helm delete --remove-resources <release_name>

**Correct Answer:** B. helm uninstall <release_name>  
**Explanation:** `helm uninstall` removes a release and the associated resources from the cluster. The `--purge` flag is deprecated as of Helm 3.

---

### 118. What is the difference between `helm upgrade` and `helm install`?

A. `helm upgrade` is used to install charts, while `helm install` is used to upgrade them  
B. `helm install` installs new charts, while `helm upgrade` updates existing charts  
C. `helm install` can only be used once, while `helm upgrade` can be used multiple times  
D. There is no difference, both perform the same task

**Correct Answer:** B. `helm install` installs new charts, while `helm upgrade` updates existing charts  
**Explanation:** `helm install` is used to deploy a new chart, whereas `helm upgrade` is used to upgrade an existing release to a new version of the chart.

---

### 119. How can you validate that your Helm chart is properly formatted and ready for deployment?

A. helm verify  
B. helm lint  
C. helm validate  
D. helm check

**Correct Answer:** B. helm lint  
**Explanation:** `helm lint` is used to check the chart for common issues, errors, and formatting problems before deploying it.

---

### 120. What happens if you use `helm upgrade` on a release with no changes?

A. The release will be downgraded  
B. The release will be rolled back  
C. The release will not be upgraded, and an error will be shown  
D. The release will be redeployed with the same configuration

**Correct Answer:** D. The release will be redeployed with the same configuration  
**Explanation:** `helm upgrade` will redeploy the release with the same configuration if no changes are made.

---

### 121. What is the Helm `--dry-run` option used for?

A. It simulates the chart installation without actually installing anything  
B. It installs the chart in a test environment  
C. It checks the validity of a Helm chart without installing it  
D. It temporarily applies changes without committing them

**Correct Answer:** A. It simulates the chart installation without actually installing anything  
**Explanation:** The `--dry-run` option allows you to preview the changes that would be made by installing or upgrading a release without actually making any changes to the cluster.

---

### 122. How do you enable Helm's debug mode for troubleshooting?

A. helm install --debug  
B. helm install --verbose  
C. helm debug --install  
D. helm install --trace

**Correct Answer:** A. helm install --debug  
**Explanation:** `--debug` provides detailed logs and extra information during the Helm chart installation process, which can help with troubleshooting.

---

### 123. How do you change the values of an already-installed Helm release?

A. helm modify <release_name> --set <key>=<value>  
B. helm change <release_name> --values <values_file>  
C. helm upgrade <release_name> --set <key>=<value>  
D. helm update <release_name> --values <values_file>

**Correct Answer:** C. helm upgrade <release_name> --set <key>=<value>  
**Explanation:** `helm upgrade` allows you to modify the values of an already installed release by using the `--set` or `--values` flags.

---

### 124. What is a Helm chart dependency?

A. A chart that relies on another chart to function  
B. A chart that installs other charts automatically  
C. A chart that modifies the configuration of other charts  
D. A chart that provides additional Kubernetes resources to a cluster

**Correct Answer:** A. A chart that relies on another chart to function  
**Explanation:** A Helm chart can declare dependencies on other charts, which must be installed together as part of the release process.

---

### 125. How do you view the Kubernetes resources associated with a specific Helm release?

A. helm get <release_name>  
B. kubectl get helm <release_name>  
C. helm show resources <release_name>  
D. helm list --resources <release_name>

**Correct Answer:** A. helm get <release_name>  
**Explanation:** `helm get` shows the configuration and resources associated with a specific Helm release.

---

### 126. What does the `helm upgrade --install` command do?

A. Upgrades a release if it exists, otherwise installs it  
B. Installs a new release and upgrades it  
C. Installs a new release and fails if the release already exists  
D. Upgrades all releases in the namespace

**Correct Answer:** A. Upgrades a release if it exists, otherwise installs it  
**Explanation:** The `--install` flag ensures that `helm upgrade` installs the chart if the release does not exist yet, otherwise, it upgrades the existing release.

---

### 127. How do you remove a chart repository from Helm?

A. helm delete repo <repo_name>  
B. helm remove repo <repo_name>  
C. helm repo remove <repo_name>  
D. helm repo delete <repo_name>

**Correct Answer:** C. helm repo remove <repo_name>  
**Explanation:** `helm repo remove` removes a chart repository from your local Helm configuration.

---

### 128. How can you install a Helm chart from a specific GitHub release?

A. helm install <release_name> --github <github_url>  
B. helm install --repo <github_url> <chart_name>  
C. helm install <release_name> <github_repo_url> --version <version>  
D. helm install --version <version> <github_repo_url>

**Correct Answer:** C. helm install <release_name> <github_repo_url> --version <version>  
**Explanation:** You can install a chart from a GitHub release by specifying the repository URL and version in the `helm install` command.

---

### 129. What is a Helm "values file"?

A. A file that contains the metadata for a chart  
B. A file that specifies the default values for the chart  
C. A file that defines Kubernetes resources  
D. A file that contains the chart dependencies

**Correct Answer:** B. A file that specifies the default values for the chart  
**Explanation:** The `values.yaml` file provides the default configuration values for a chart, which can be overridden at install time using the `--values` or `--set` flags.

---

### 130. How can you apply changes to the Helm release after you modify the `values.yaml` file?

A. helm upgrade <release_name>  
B. helm apply <release_name>  
C. helm update <release_name>  
D. helm modify <release_name>

**Correct Answer:** A. helm upgrade <release_name>  
**Explanation:** Once you modify the `values.yaml` file, you can apply the changes to the running release using `helm upgrade`.

---

### 131. How do you list all available Helm charts in a repository?

A. helm list <repo_name>  
B. helm search repo <repo_name>  
C. helm show charts <repo_name>  
D. helm list charts <repo_name>

**Correct Answer:** B. helm search repo <repo_name>  
**Explanation:** `helm search repo` searches for available charts in a specific chart repository.

---

### 132. What does the `helm fetch` command do?

A. Downloads a Helm chart from a repository without installing it  
B. Fetches a Helm chart from a local directory  
C. Installs a Helm chart from the repository  
D. Fetches the history of a Helm release

**Correct Answer:** A. Downloads a Helm chart from a repository without installing it  
**Explanation:** `helm fetch` is used to download a Helm chart from a repository to your local machine, without installing it.

---

### 133. How do you install a specific version of a Helm chart?

A. helm install <release_name> --version <version>  
B. helm install <chart_name> --set version=<version>  
C. helm install <release_name> <chart_name>@<version>  
D. helm install --version <version> <release_name> <chart_name>

**Correct Answer:** A. helm install <release_name> --version <version>  
**Explanation:** You can install a specific version of a Helm chart using the `--version` flag during installation.

---

### 134. What is a Helm "chart archive"?

A. A compressed file containing the Helm chart and its dependencies  
B. A collection of Helm charts stored in a repository  
C. A backup of a Helm release  
D. A Helm chart that is no longer maintained

**Correct Answer:** A. A compressed file containing the Helm chart and its dependencies  
**Explanation:** A Helm chart archive is a `.tgz` file containing the chart and its associated files, used for distribution.

---

### 135. How do you view the rendered Kubernetes manifest of a Helm chart without installing it?

A. helm template <chart_name>  
B. helm show <chart_name>  
C. helm get <chart_name>  
D. helm render <chart_name>

**Correct Answer:** A. helm template <chart_name>  
**Explanation:** `helm template` renders the Kubernetes manifest files from a chart without installing it, allowing you to inspect the final Kubernetes resources.

---

### 136. How can you specify a custom namespace when installing a Helm chart?

A. helm install <release_name> --namespace <namespace>  
B. helm install --namespace <namespace> <chart_name>  
C. helm install <chart_name> -n <namespace>  
D. helm install <namespace> <chart_name>

**Correct Answer:** B. helm install --namespace <namespace> <chart_name>  
**Explanation:** You can specify a custom namespace using the `--namespace` flag when installing a Helm chart.

---

### 137. What command can you use to generate the Kubernetes manifest for a chart without actually deploying it?

A. helm generate  
B. helm template  
C. helm manifest  
D. helm render

**Correct Answer:** B. helm template  
**Explanation:** `helm template` generates the Kubernetes manifest without applying or installing the chart, giving you the final output that will be deployed.

---

### 138. What does the `helm status <release_name>` command do?

A. Shows the current status of the release  
B. Installs the Helm release  
C. Upgrades the Helm release  
D. Lists all Helm releases in the current namespace

**Correct Answer:** A. Shows the current status of the release  
**Explanation:** `helm status` displays information about a release, including its current state, resources, and history.

---

### 139. How do you remove the Helm release from the cluster and preserve its data?

A. helm uninstall --retain-data <release_name>  
B. helm delete --preserve <release_name>  
C. helm uninstall <release_name>  
D. helm delete --keep-data <release_name>

**Correct Answer:** C. helm uninstall <release_name>  
**Explanation:** `helm uninstall` deletes the release and its associated resources, but any persistent data (like volumes) are not automatically deleted unless explicitly configured.

---

### 140. How do you upgrade a Helm release while ensuring that the release is only applied if all resources are successfully deployed?

A. helm upgrade --atomic <release_name>  
B. helm upgrade --confirm <release_name>  
C. helm upgrade --apply <release_name>  
D. helm upgrade --rollback <release_name>

**Correct Answer:** A. helm upgrade --atomic <release_name>  
**Explanation:** The `--atomic` flag ensures that the upgrade either fully succeeds or is completely rolled back if there’s a failure, preventing partial deployments.

---

### 141. How can you customize a Helm chart with your own values during installation?

A. helm install <release_name> --set <key>=<value>  
B. helm install --custom <values_file>  
C. helm install <release_name> --values <values_file>  
D. helm customize <release_name> --values <values_file>

**Correct Answer:** C. helm install <release_name> --values <values_file>  
**Explanation:** The `--values` flag allows you to specify a custom `values.yaml` file to customize the chart installation.

---

### 142. How do you fetch the Helm chart archive (tarball) from a repository?

A. helm fetch <chart_name> --repo <repo_url>  
B. helm download <chart_name> --repo <repo_url>  
C. helm get <chart_name> --repo <repo_url>  
D. helm pull <chart_name> --repo <repo_url>

**Correct Answer:** D. helm pull <chart_name> --repo <repo_url>  
**Explanation:** `helm pull` downloads the chart archive from a Helm chart repository without installing it.

---

### 143. How do you install a chart from a local file path?

A. helm install <release_name> <path_to_chart>  
B. helm install <path_to_chart> --local  
C. helm install --path <path_to_chart>  
D. helm install --repo <path_to_chart>

**Correct Answer:** A. helm install <release_name> <path_to_chart>  
**Explanation:** You can install a Helm chart from a local directory by specifying the path to the chart.

---

### 144. How can you rollback to a previous revision of a Helm release?

A. helm rollback <release_name> --revision <revision_number>  
B. helm downgrade <release_name> --revision <revision_number>  
C. helm upgrade --rollback <release_name>  
D. helm install <release_name> --revision <revision_number>

**Correct Answer:** A. helm rollback <release_name> --revision <revision_number>  
**Explanation:** `helm rollback` allows you to roll back to a specific revision of a release by specifying the revision number.

---

### 145. What is the default namespace used by Helm if no namespace is specified?

A. default  
B. helm  
C. kube-system  
D. mynamespace

**Correct Answer:** A. default  
**Explanation:** Helm installs charts to the `default` namespace unless you specify a custom namespace.

---

### 146. How can you display a Helm chart's metadata and dependencies?

A. helm show chart <chart_name>  
B. helm display <chart_name>  
C. helm info <chart_name>  
D. helm show <chart_name>

**Correct Answer:** D. helm show <chart_name>  
**Explanation:** `helm show` displays various metadata, including dependencies and other chart details.

---

### 147. How do you get the list of all installed Helm charts?

A. helm list  
B. helm show releases  
C. helm charts  
D. helm installed

**Correct Answer:** A. helm list  
**Explanation:** `helm list` lists all the installed releases in the current namespace.

---

### 148. What does the `helm status` command provide for a release?

A. Shows the resources, status, and revision information for the release  
B. Installs the release  
C. Rolls back the release  
D. Shows detailed logs for a failed release

**Correct Answer:** A. Shows the resources, status, and revision information for the release  
**Explanation:** `helm status` provides detailed information about the release, including its current state and associated resources.

---

### 149. What is a Helm chart’s "values.yaml" file primarily used for?

A. To define dependencies between charts  
B. To specify the metadata for the chart  
C. To provide default configuration values for the chart  
D. To store the Kubernetes manifests

**Correct Answer:** C. To provide default configuration values for the chart  
**Explanation:** The `values.yaml` file defines the default configuration for the chart, which can be overridden during installation.

---

### 150. What does `helm repo index` do?

A. Creates a repository index file for Helm charts  
B. Adds a new chart to the Helm repository  
C. Displays the list of available charts in a repository  
D. Downloads charts from a repository

**Correct Answer:** A. Creates a repository index file for Helm charts  
**Explanation:** `helm repo index` generates or updates the `index.yaml` file for a local Helm chart repository, which Helm uses to discover charts.

---
