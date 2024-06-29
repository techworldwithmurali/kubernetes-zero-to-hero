# Installation of AWS CLI, kubectl CLI, and eksctl CLI

## AWS CLI

### Installation on Windows

1. **Download Installer:**
   - Download the MSI installer from [AWS CLI Downloads](https://aws.amazon.com/cli/) page.

2. **Run Installer:**
   - Run the downloaded installer and follow the installation wizard instructions.

3. **Verify Installation:**
   - Open Command Prompt (cmd) and type `aws --version` to verify the installation.

### Installation on Linux

1. **Install Using Package Manager:**
   - For Debian-based systems (like Ubuntu):
     ```bash
     sudo apt-get update
     sudo apt-get install awscli
     ```

   - For Red Hat-based systems (like CentOS, Fedora):
     ```bash
     sudo yum install aws-cli
     ```

2. **Verify Installation:**
   - Open a terminal and type `aws --version` to verify the installation.

### Creation of AWS IAM User

1. **Sign in to AWS Management Console:**
   - Navigate to the IAM service.

2. **Create IAM User:**
   - Follow the steps to create a new IAM user with appropriate permissions.

3. **Access Keys:**
   - Generate access keys for the IAM user to use with AWS CLI.

## kubectl CLI

### Installation on Windows

1. **Download Installer:**
   - Download the executable from [kubectl Releases](https://kubernetes.io/docs/tasks/tools/install-kubectl/) page.

2. **Add to PATH:**
   - Extract the executable and add the directory to the system PATH environment variable.

3. **Verify Installation:**
   - Open Command Prompt (cmd) and type `kubectl version --client` to verify the installation.

### Installation on Linux

1. **Download and Install:**
   - Download the binary using curl:
     ```bash
     curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
     ```

   - Make the kubectl binary executable:
     ```bash
     chmod +x ./kubectl
     sudo mv ./kubectl /usr/local/bin/kubectl
     ```

2. **Verify Installation:**
   - Open a terminal and type `kubectl version --client` to verify the installation.

## eksctl CLI

### Installation on Windows

1. **Download Installer:**
   - Download the Windows installer from [eksctl Releases](https://github.com/weaveworks/eksctl/releases) page.

2. **Run Installer:**
   - Run the installer executable and follow the installation instructions.

3. **Verify Installation:**
   - Open Command Prompt (cmd) and type `eksctl version` to verify the installation.

### Installation on Linux

1. **Download and Install:**
   - Download the binary using curl:
     ```bash
     curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
     ```

   - Move the binary to a directory in your PATH:
     ```bash
     sudo mv /tmp/eksctl /usr/local/bin
     ```

2. **Verify Installation:**
   - Open a terminal and type `eksctl version` to verify the installation.
