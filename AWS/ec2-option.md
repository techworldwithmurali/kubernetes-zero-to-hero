### 1. What is the default size of an EBS volume when you launch an EC2 instance with the default settings?

A. 10 GB  
B. 20 GB  
C. 30 GB  
D. 50 GB  

**Correct Answer:** A. 10 GB  
**Explanation:** By default, EC2 instances are launched with a 10 GB EBS volume for the root device unless specified otherwise.

### 2. Which of the following is required to connect to an EC2 instance via SSH?

A. A public IP address  
B. An AWS IAM role  
C. A security group rule for inbound SSH access  
D. An EBS volume  

**Correct Answer:** C. A security group rule for inbound SSH access  
**Explanation:** To connect via SSH, you need a security group that allows inbound traffic on port 22.

### 3. What is the main function of Amazon EC2 Auto Scaling?

A. To automatically scale up the number of EC2 instances to handle increasing traffic  
B. To provide security for EC2 instances  
C. To monitor the health of EC2 instances  
D. To automatically provision the required storage for EC2 instances  

**Correct Answer:** A. To automatically scale up the number of EC2 instances to handle increasing traffic  
**Explanation:** Auto Scaling automatically adjusts the number of EC2 instances in response to traffic demands.

### 4. What is an EC2 instance's "public IP" used for?

A. It provides access to the EC2 instance only within the AWS network  
B. It allows access to the EC2 instance from the internet  
C. It secures the EC2 instance against unauthorized access  
D. It stores data for the EC2 instance  

**Correct Answer:** B. It allows access to the EC2 instance from the internet  
**Explanation:** The public IP enables access to the instance from outside the AWS network.

### 5. What is the EC2 instance metadata service used for?

A. Storing files for EC2 instances  
B. Providing real-time instance-specific data like instance ID, region, and AMI ID  
C. Allowing access to S3 buckets  
D. Providing DNS resolution  

**Correct Answer:** B. Providing real-time instance-specific data like instance ID, region, and AMI ID  
**Explanation:** The metadata service provides metadata to the running instance for retrieving details specific to that instance.

### 6. How can you ensure that an EC2 instance can automatically recover if it becomes impaired?

A. By using EC2 Auto Scaling  
B. By attaching an Elastic IP address  
C. By creating a CloudWatch Alarm and configuring Auto Recovery  
D. By attaching a new EBS volume  

**Correct Answer:** C. By creating a CloudWatch Alarm and configuring Auto Recovery  
**Explanation:** CloudWatch Alarms can be set to automatically recover impaired instances.

### 7. What does the EC2 "spot instance" pricing model allow you to do?

A. Purchase instances at a fixed price for long-term use  
B. Buy unused EC2 capacity at a reduced cost, with the risk of termination  
C. Automatically scale EC2 instances based on traffic  
D. Create and manage persistent storage  

**Correct Answer:** B. Buy unused EC2 capacity at a reduced cost, with the risk of termination  
**Explanation:** Spot instances are cheaper but can be terminated by AWS when there is higher demand for capacity.

### 8. Which EC2 instance type is designed to deliver the highest performance for memory-intensive workloads?

A. T3  
B. M5  
C. R5  
D. C5  

**Correct Answer:** C. R5  
**Explanation:** The R5 instance family is optimized for memory-intensive applications.

### 9. How would you assign a static IP address to an EC2 instance?

A. By creating an Elastic IP and associating it with the instance  
B. By using the instance's public IP  
C. By using AWS Route 53  
D. By configuring the EC2 instance's internal IP  

**Correct Answer:** A. By creating an Elastic IP and associating it with the instance  
**Explanation:** Elastic IP addresses are static IPs that can be associated with EC2 instances.

### 10. What is the purpose of EC2 instance "user data"?

A. It stores the operating system's data  
B. It allows the EC2 instance to retrieve metadata  
C. It is used for automating scripts and commands during instance launch  
D. It defines the root password for the EC2 instance  

**Correct Answer:** C. It is used for automating scripts and commands during instance launch  
**Explanation:** User data scripts are executed automatically when an EC2 instance is launched.


### 11. Which of the following is the correct way to stop an EC2 instance without terminating it?

A. By clicking "Terminate" in the EC2 console  
B. By disabling the instance's security group  
C. By selecting "Stop" in the EC2 console  
D. By deleting the instance from the EC2 dashboard  

**Correct Answer:** C. By selecting "Stop" in the EC2 console  
**Explanation:** Stopping the instance will shut it down temporarily, but the instance can be started again without data loss.

### 12. What is the primary function of Amazon EC2 Instance Store?

A. To provide persistent storage for EC2 instances  
B. To store operating system files only  
C. To provide temporary storage that is physically attached to the host machine  
D. To store backups of EC2 instances  

**Correct Answer:** C. To provide temporary storage that is physically attached to the host machine  
**Explanation:** Instance Store provides ephemeral storage that is lost if the instance is stopped or terminated.

### 13. When should you use EC2 Reserved Instances instead of On-Demand Instances?

A. When you need instances for short-term workloads  
B. When you need flexible instance types and pricing  
C. When you want to commit to using EC2 instances for a longer period (1 or 3 years)  
D. When you want instances to be automatically scaled based on demand  

**Correct Answer:** C. When you want to commit to using EC2 instances for a longer period (1 or 3 years)  
**Explanation:** Reserved Instances are best suited for long-term use cases, providing significant savings in exchange for a commitment to a term.

### 14. What is the default maximum number of EC2 instances you can launch per region?

A. 50  
B. 100  
C. 200  
D. 1000  

**Correct Answer:** B. 100  
**Explanation:** By default, you can launch up to 100 EC2 instances per region, but this limit can be increased by submitting a request to AWS.

### 15. How can you check if an EC2 instance is running low on disk space?

A. By viewing CloudWatch metrics for disk space usage  
B. By checking the EC2 instance's system logs  
C. By using the "df -h" command inside the EC2 instance  
D. All of the above  

**Correct Answer:** D. All of the above  
**Explanation:** You can check disk space usage using CloudWatch, instance logs, or by using Linux commands inside the instance.

### 16. Which EC2 instance lifecycle state is associated with an instance being provisioned and starting up?

A. Pending  
B. Running  
C. Stopped  
D. Shutting-down  

**Correct Answer:** A. Pending  
**Explanation:** "Pending" is the state when an instance is being provisioned and initialized before transitioning to the "Running" state.

### 17. Which AWS service can be used to monitor and manage the health of EC2 instances?

A. AWS CloudTrail  
B. AWS CloudWatch  
C. AWS Inspector  
D. AWS Lambda  

**Correct Answer:** B. AWS CloudWatch  
**Explanation:** CloudWatch provides monitoring for EC2 instances and other AWS resources, including health checks and metrics.

### 18. What happens when you terminate an EC2 instance?

A. The instance is stopped and can be restarted later  
B. The instance is permanently deleted, and all associated data is lost  
C. The instance is paused, but data is retained  
D. The instance is moved to a different availability zone  

**Correct Answer:** B. The instance is permanently deleted, and all associated data is lost  
**Explanation:** Terminating an EC2 instance will delete it permanently, and any data on the instance store will be lost.

### 19. What is the main benefit of using EC2's Elastic Load Balancer (ELB)?

A. It helps with auto-scaling EC2 instances  
B. It improves the security of EC2 instances  
C. It distributes incoming traffic across multiple EC2 instances  
D. It helps optimize EC2 instance costs  

**Correct Answer:** C. It distributes incoming traffic across multiple EC2 instances  
**Explanation:** ELB helps to distribute incoming application traffic across multiple instances to ensure high availability.

### 20. Which of the following best describes the "Elastic Block Store" (EBS) in EC2?

A. A temporary storage option for EC2 instances  
B. A storage solution for high-throughput, low-latency storage  
C. A network-attached storage that persists data independently of EC2 instance lifecycle  
D. A backup solution for EC2 instances  

**Correct Answer:** C. A network-attached storage that persists data independently of EC2 instance lifecycle  
**Explanation:** EBS provides persistent block storage that remains available even after an EC2 instance is stopped or terminated.

### 21. Which EC2 feature allows instances to automatically distribute traffic between them for load balancing?

A. Auto Scaling  
B. Elastic Load Balancing  
C. CloudFront  
D. Route 53  

**Correct Answer:** B. Elastic Load Balancing  
**Explanation:** ELB automatically distributes incoming application traffic across multiple instances.

### 22. What happens if you stop and start an EC2 instance that is using an instance store?

A. Data in the instance store is preserved  
B. Data in the instance store is lost  
C. The instance's data is automatically backed up  
D. The instance is moved to a different availability zone  

**Correct Answer:** B. Data in the instance store is lost  
**Explanation:** Instance store data is ephemeral and lost when the instance is stopped and started.

### 23. Which of the following is required to connect to an EC2 instance via Remote Desktop (RDP)?

A. A public IP address  
B. A key pair  
C. A security group rule allowing inbound RDP (port 3389)  
D. An Elastic IP  

**Correct Answer:** C. A security group rule allowing inbound RDP (port 3389)  
**Explanation:** RDP access requires a security group rule that allows inbound traffic on port 3389.

### 24. What is the best way to ensure an EC2 instance is highly available in case of failure?

A. Use EC2 Auto Scaling and place instances in multiple availability zones  
B. Use EC2 instances with a higher instance type  
C. Enable EC2 spot instances  
D. Use only t2.micro instance types  

**Correct Answer:** A. Use EC2 Auto Scaling and place instances in multiple availability zones  
**Explanation:** Auto Scaling and multi-AZ deployments help ensure high availability by distributing traffic and instances across multiple zones.


### 25. What is the best way to monitor an EC2 instance for performance bottlenecks?

A. Use Amazon S3 to store performance data  
B. Use CloudWatch to monitor metrics like CPU utilization and disk I/O  
C. Use AWS Lambda to automate performance monitoring  
D. Use Route 53 for DNS resolution  

**Correct Answer:** B. Use CloudWatch to monitor metrics like CPU utilization and disk I/O  
**Explanation:** CloudWatch allows you to track performance metrics and identify bottlenecks.

### 26. How do you ensure that a terminated EC2 instance cannot be restarted?

A. By creating a new security group for the instance  
B. By disabling the instance's Elastic IP  
C. By selecting the "Terminate" option when stopping the instance  
D. By deleting the instance's AMI and snapshot  

**Correct Answer:** C. By selecting the "Terminate" option when stopping the instance  
**Explanation:** Terminating the instance deletes it completely, and it cannot be restarted.

### 27. Which Amazon EC2 instance family is best suited for compute-intensive applications?

A. T3  
B. M5  
C. C5  
D. R5  

**Correct Answer:** C. C5  
**Explanation:** The C5 instance family is designed for compute-intensive workloads such as high-performance web servers and scientific modeling.

### 28. What can you do if your EC2 instance is stuck in the "stopping" state?

A. Wait for the instance to automatically recover  
B. Terminate the instance and create a new one  
C. Use CloudWatch to restart the instance  
D. Contact AWS support for assistance  

**Correct Answer:** D. Contact AWS support for assistance  
**Explanation:** If an EC2 instance is stuck in a state, AWS support may be needed to investigate and resolve the issue.

### 29. What happens when you modify the instance type of a running EC2 instance?

A. The instance stops, then restarts with the new instance type  
B. The instance continues running without any interruption  
C. The instance is terminated and a new instance with the modified type is created  
D. The instance requires a manual reboot for changes to take effect  

**Correct Answer:** A. The instance stops, then restarts with the new instance type  
**Explanation:** Modifying the instance type requires stopping and restarting the instance.

### 30. How can you increase the storage capacity of an existing EC2 instance?

A. By using Elastic Load Balancing to distribute storage  
B. By modifying the EBS volume size and extending the filesystem  
C. By deleting the existing instance and launching a new one  
D. By attaching additional storage using an S3 bucket  

**Correct Answer:** B. By modifying the EBS volume size and extending the filesystem  
**Explanation:** You can modify the size of an EBS volume and extend the filesystem to increase storage.

### 31. Which of the following is a way to prevent unauthorized access to an EC2 instance?

A. Use security groups and network ACLs  
B. Set up a public IP for the instance  
C. Use Route 53 for DNS security  
D. Enable the "root" user for all instances  

**Correct Answer:** A. Use security groups and network ACLs  
**Explanation:** Security groups and network ACLs allow you to control inbound and outbound traffic to protect the instance.

### 32. Which AWS service can be used to create a backup for your EC2 instance?

A. AWS CloudTrail  
B. Amazon S3  
C. AWS Backup or EC2 snapshots  
D. AWS Systems Manager  

**Correct Answer:** C. AWS Backup or EC2 snapshots  
**Explanation:** EC2 snapshots or AWS Backup can be used to create backups of EC2 instances.

### 33. What is the purpose of the "Elastic IP" in EC2?

A. It provides an additional network interface for EC2 instances  
B. It is a fixed IP address that can be associated with EC2 instances  
C. It stores instance metadata  
D. It increases the bandwidth available to an instance  

**Correct Answer:** B. It is a fixed IP address that can be associated with EC2 instances  
**Explanation:** Elastic IP is a static IPv4 address designed for dynamic cloud computing.

### 34. Which of the following is true about EC2 instance termination protection?

A. It prevents an instance from being stopped  
B. It prevents an instance from being terminated from the EC2 console or API  
C. It prevents instance backups from being created  
D. It protects the instance from unauthorized access  

**Correct Answer:** B. It prevents an instance from being terminated from the EC2 console or API  
**Explanation:** Termination protection prevents accidental termination of the EC2 instance.

### 35. What is the default behavior when an EC2 instance’s root device is an EBS volume and the instance is terminated?

A. The EBS volume is deleted  
B. The EBS volume is retained and can be reattached  
C. The EBS volume is encrypted automatically  
D. The EBS volume is detached and attached to a new instance  

**Correct Answer:** A. The EBS volume is deleted  
**Explanation:** By default, the root EBS volume is deleted when an EC2 instance is terminated.

### 36. What is the benefit of using EC2 "Auto Scaling"?

A. It provides automated backups for instances  
B. It helps adjust the instance count based on traffic  
C. It stores data across multiple EC2 instances  
D. It allows EC2 instances to run without requiring an internet connection  

**Correct Answer:** B. It helps adjust the instance count based on traffic  
**Explanation:** Auto Scaling automatically increases or decreases the number of EC2 instances based on predefined conditions.

### 37. What is the best practice for storing sensitive data on EC2 instances?

A. Use plaintext in environment variables  
B. Use Amazon S3 with public access  
C. Use EC2 instance metadata service  
D. Use AWS KMS to encrypt sensitive data  

**Correct Answer:** D. Use AWS KMS to encrypt sensitive data  
**Explanation:** AWS KMS (Key Management Service) is used for encrypting sensitive data to maintain security.

### 38. When would you use an EC2 Spot instance?

A. When you need guaranteed uptime for critical workloads  
B. For low-cost, fault-tolerant applications  
C. For high-performance computing workloads  
D. For instances that must be billed at a fixed rate  

**Correct Answer:** B. For low-cost, fault-tolerant applications  
**Explanation:** Spot instances are cost-effective but may be terminated by AWS, so they are ideal for fault-tolerant workloads.

### 39. What is the EC2 "Placement Group" used for?

A. To control the region in which EC2 instances are launched  
B. To group instances for high availability and low latency  
C. To specify the instance type for workloads  
D. To secure EC2 instances from unauthorized access  

**Correct Answer:** B. To group instances for high availability and low latency  
**Explanation:** Placement Groups enable EC2 instances to be placed together to optimize network performance or provide fault tolerance.

### 40. How can you ensure that your EC2 instance is accessible only from within a specific subnet?

A. By assigning a public IP address to the instance  
B. By configuring a VPC security group with specific rules  
C. By disabling the instance's security group  
D. By using AWS Systems Manager for management  

**Correct Answer:** B. By configuring a VPC security group with specific rules  
**Explanation:** Security groups can be configured to restrict access to instances based on IP ranges or other conditions.


### 41. What is the main difference between EC2 Spot Instances and EC2 On-Demand Instances?

A. Spot Instances are less expensive but can be terminated by AWS, while On-Demand Instances are more expensive and persistent  
B. On-Demand Instances are used for testing, while Spot Instances are used for production  
C. Spot Instances provide persistent storage, while On-Demand Instances do not  
D. There is no difference; both are the same pricing model  

**Correct Answer:** A. Spot Instances are less expensive but can be terminated by AWS, while On-Demand Instances are more expensive and persistent  
**Explanation:** Spot Instances offer lower cost but can be interrupted by AWS, while On-Demand Instances provide uninterrupted service at a higher price.

### 42. What happens if you launch an EC2 instance in an Availability Zone with insufficient capacity?

A. The instance will be automatically placed in a different zone with available capacity  
B. The instance will not launch and an error message will be returned  
C. The instance will be placed in a queue and launched when capacity is available  
D. The instance will automatically scale to handle the additional load  

**Correct Answer:** B. The instance will not launch and an error message will be returned  
**Explanation:** If there is insufficient capacity in the selected Availability Zone, the instance launch will fail.

### 43. How can you prevent the termination of an EC2 instance accidentally?

A. Enable termination protection for the instance  
B. Use a security group with restrictive access  
C. Enable CloudWatch monitoring for the instance  
D. Place the instance in a dedicated VPC  

**Correct Answer:** A. Enable termination protection for the instance  
**Explanation:** Termination protection can be enabled to prevent an EC2 instance from being accidentally terminated.

### 44. What is an EC2 instance’s "instance type"?

A. The public IP address of the EC2 instance  
B. The unique identifier for the EC2 instance  
C. The type of hardware configuration (CPU, memory, storage) for the instance  
D. The security group assigned to the instance  

**Correct Answer:** C. The type of hardware configuration (CPU, memory, storage) for the instance  
**Explanation:** The instance type determines the CPU, memory, and storage configurations of the EC2 instance.

### 45. How can you assign a secondary IP address to an EC2 instance?

A. By creating a new security group for the instance  
B. By creating and assigning an Elastic IP  
C. By adding an additional ENI (Elastic Network Interface)  
D. By modifying the instance's user data  

**Correct Answer:** C. By adding an additional ENI (Elastic Network Interface)  
**Explanation:** Secondary IP addresses are assigned by adding an additional ENI to the EC2 instance.

### 46. What is the purpose of EC2 "Elastic IP"?

A. To increase the instance’s CPU capacity  
B. To assign a static IPv4 address to an instance  
C. To create a backup of an EC2 instance  
D. To connect instances within a VPC  

**Correct Answer:** B. To assign a static IPv4 address to an instance  
**Explanation:** Elastic IP addresses are static IP addresses that are used to maintain persistent connections to instances, even if the instance is stopped and restarted.

### 47. How can you improve the network performance of an EC2 instance?

A. By using a larger instance type with higher CPU  
B. By attaching multiple EBS volumes to the instance  
C. By using enhanced networking with Elastic Network Adapter (ENA)  
D. By placing the instance in a different Availability Zone  

**Correct Answer:** C. By using enhanced networking with Elastic Network Adapter (ENA)  
**Explanation:** ENA provides higher bandwidth and lower latency network performance, improving overall networking for EC2 instances.

### 48. Which AWS service can you use to launch EC2 instances on dedicated hardware?

A. EC2 Spot Instances  
B. EC2 Reserved Instances  
C. EC2 Dedicated Hosts  
D. EC2 On-Demand Instances  

**Correct Answer:** C. EC2 Dedicated Hosts  
**Explanation:** EC2 Dedicated Hosts provide physical servers dedicated to your use, allowing you to launch instances on dedicated hardware.

### 49. What is the main benefit of using EC2 "Elastic Load Balancing" (ELB)?

A. It helps with auto-scaling EC2 instances  
B. It ensures high availability and fault tolerance by distributing traffic across multiple EC2 instances  
C. It automatically creates backups of EC2 instances  
D. It allows you to use EC2 instances in multiple regions  

**Correct Answer:** B. It ensures high availability and fault tolerance by distributing traffic across multiple EC2 instances  
**Explanation:** ELB distributes incoming traffic across multiple EC2 instances to ensure that applications remain highly available.

### 50. What is the default behavior when an EC2 instance is launched in a VPC with no public IP address?

A. The instance cannot be accessed from the internet  
B. The instance will automatically be assigned an Elastic IP  
C. The instance will be accessible only through SSH  
D. The instance will receive a private IP address but can still connect to the internet via a NAT Gateway  

**Correct Answer:** A. The instance cannot be accessed from the internet  
**Explanation:** If no public IP address is assigned to an EC2 instance in a VPC, it is not directly accessible from the internet, but it can communicate over the internet if a NAT Gateway is used.

### 51. How can you ensure your EC2 instance can be restored from failure?

A. By using EC2 Auto Scaling  
B. By creating an EC2 snapshot and storing it in Amazon S3  
C. By using CloudWatch to monitor instance health  
D. By enabling instance recovery through the EC2 console  

**Correct Answer:** B. By creating an EC2 snapshot and storing it in Amazon S3  
**Explanation:** Snapshots provide a backup of the EC2 instance and can be used to restore it in case of failure.

### 52. How do you enable SSH access to an EC2 instance?

A. By enabling the "ssh" rule in the security group for port 22  
B. By using EC2 Instance Connect  
C. By assigning a public IP address and configuring SSH keys  
D. All of the above  

**Correct Answer:** D. All of the above  
**Explanation:** To enable SSH access, you need a public IP address, security group allowing port 22, and an SSH key pair.

### 53. Which EC2 instance family is optimized for memory-intensive workloads?

A. T3  
B. M5  
C. R5  
D. C5  

**Correct Answer:** C. R5  
**Explanation:** The R5 instance family is optimized for memory-intensive applications, such as high-performance databases.

### 54. What happens if your EC2 instance’s root EBS volume runs out of space?

A. The instance will stop working until additional space is allocated  
B. The instance will automatically scale up to handle the additional load  
C. The instance will automatically delete non-essential files to free up space  
D. The instance will continue running, but new data cannot be written to the volume  

**Correct Answer:** D. The instance will continue running, but new data cannot be written to the volume  
**Explanation:** When the root volume runs out of space, the instance can continue running, but new writes will fail until space is freed or expanded.

### 55. What is the best way to secure an EC2 instance when it is part of a public subnet?

A. Use a security group with inbound rules for port 22 (SSH) and 80 (HTTP)  
B. Attach a public IP address and allow all inbound traffic  
C. Use Network ACLs to block all inbound and outbound traffic  
D. Only allow access to the instance via private IP addresses from trusted networks  

**Correct Answer:** D. Only allow access to the instance via private IP addresses from trusted networks  
**Explanation:** In a public subnet, you should control access using security groups and restrict inbound traffic to trusted sources.

### 56. How do you associate an EC2 instance with an Elastic Load Balancer (ELB)?

A. By using the EC2 instance's public IP  
B. By adding the instance to a target group for the ELB  
C. By modifying the security group of the EC2 instance  
D. By using EC2 Auto Scaling to automatically attach instances to ELB  

**Correct Answer:** B. By adding the instance to a target group for the ELB  
**Explanation:** EC2 instances are added to target groups, which are then linked to an Elastic Load Balancer to distribute traffic.

### 57. How can you determine which EC2 instance is causing a bottleneck in your system?

A. By monitoring instance CPU and memory usage through CloudWatch  
B. By using a third-party monitoring tool  
C. By inspecting the EC2 instance's root EBS volume  
D. By checking the VPC flow logs for unusual network traffic  

**Correct Answer:** A. By monitoring instance CPU and memory usage through CloudWatch  
**Explanation:** CloudWatch provides detailed metrics that can help identify performance issues such as CPU or memory bottlenecks.

### 58. What is the purpose of EC2 "User Data"?

A. It stores configuration information for the EC2 instance  
B. It provides metadata about the instance  
C. It contains startup scripts that are executed when the instance is launched  
D. It enables logging and monitoring for the instance  

**Correct Answer:** C. It contains startup scripts that are executed when the instance is launched  
**Explanation:** User Data allows you to specify initialization scripts that run when the EC2 instance is launched, such as software installation.

### 59. Which AWS service can you use to monitor EC2 instances and automatically restart them when they become unhealthy?

A. AWS CloudWatch  
B. AWS Config  
C. EC2 Auto Scaling  
D. AWS Lambda  

**Correct Answer:** C. EC2 Auto Scaling  
**Explanation:** EC2 Auto Scaling can automatically replace unhealthy instances based on predefined health checks.

### 60. How do you scale EC2 instances horizontally?

A. By changing the instance type to a larger one  
B. By launching more instances and distributing traffic across them using a Load Balancer  
C. By increasing the instance size  
D. By using AWS Lambda to scale instances  

**Correct Answer:** B. By launching more instances and distributing traffic across them using a Load Balancer  
**Explanation:** Horizontal scaling involves adding more instances to distribute the load, often using an Elastic Load Balancer.

### 61. How can you secure your EC2 instances against potential DDoS attacks?

A. Use a VPC with private subnets only  
B. Use AWS Shield and set up a WAF (Web Application Firewall)  
C. Increase the instance type to handle more traffic  
D. Block all inbound traffic using security groups  

**Correct Answer:** B. Use AWS Shield and set up a WAF (Web Application Firewall)  
**Explanation:** AWS Shield and WAF help protect your EC2 instances from DDoS attacks by filtering malicious traffic.

### 62. How can you reduce the cost of running EC2 instances for infrequent workloads?

A. Use EC2 Reserved Instances  
B. Use EC2 Spot Instances  
C. Use EC2 On-Demand Instances with auto-scaling  
D. Use EC2 Savings Plans  

**Correct Answer:** B. Use EC2 Spot Instances  
**Explanation:** Spot Instances allow you to bid for unused EC2 capacity at a lower price, making them ideal for infrequent or flexible workloads.

### 63. What happens when you delete an EC2 instance that is part of an Auto Scaling Group?

A. The instance is permanently deleted and cannot be recovered  
B. The Auto Scaling Group launches a new instance to replace the deleted one  
C. The instance is temporarily stopped and cannot be restarted  
D. The Auto Scaling Group will attempt to launch more instances to balance the load  

**Correct Answer:** B. The Auto Scaling Group launches a new instance to replace the deleted one  
**Explanation:** Auto Scaling ensures the desired number of instances is maintained. When an instance is deleted, the group automatically replaces it.

### 64. How do you enable EC2 instances to launch in a specific Availability Zone?

A. By selecting the Availability Zone when launching the instance  
B. By using EC2 Auto Scaling with AZ-specific scaling policies  
C. By modifying the security group to include the AZ  
D. By setting the region parameter during instance configuration  

**Correct Answer:** A. By selecting the Availability Zone when launching the instance  
**Explanation:** During the instance launch process, you can specify the Availability Zone to control where the instance is launched.

### 65. How do you automate the backup of an EC2 instance's EBS volume?

A. By using AWS Backup to create scheduled backups  
B. By taking snapshots manually from the EC2 console  
C. By using CloudWatch events to trigger an EBS snapshot  
D. By enabling EC2 Auto Scaling to perform regular backups  

**Correct Answer:** A. By using AWS Backup to create scheduled backups  
**Explanation:** AWS Backup can automate and schedule backups for EC2 instances, including EBS volumes.

### 66. How do you allow an EC2 instance to access a private subnet in a VPC?

A. Attach an Elastic IP to the EC2 instance  
B. Enable VPC Peering between the public and private subnets  
C. Assign a public IP address to the instance  
D. Use a NAT Gateway to allow outbound internet traffic from the private subnet  

**Correct Answer:** B. Enable VPC Peering between the public and private subnets  
**Explanation:** VPC Peering allows communication between instances in different subnets within a VPC, even if they are in different availability zones.

### 67. Which of the following actions can you automate with EC2 Auto Scaling?

A. Automatically terminate instances that are not being used  
B. Scale the number of instances based on CPU utilization or other metrics  
C. Automatically configure instance security groups  
D. Automatically back up instances every day  

**Correct Answer:** B. Scale the number of instances based on CPU utilization or other metrics  
**Explanation:** EC2 Auto Scaling allows you to adjust the number of running instances based on metrics like CPU utilization or custom CloudWatch alarms.

### 68. What is an EC2 "Security Group"?

A. A physical firewall that protects your EC2 instance  
B. A set of rules that control inbound and outbound traffic for EC2 instances  
C. A network device that provides encryption for EC2 instances  
D. A backup service for EC2 instances  

**Correct Answer:** B. A set of rules that control inbound and outbound traffic for EC2 instances  
**Explanation:** Security Groups are virtual firewalls that allow you to control access to EC2 instances based on IP address, port, and protocol.

### 69. What is the maximum number of EC2 instances that can be launched by default per region?

A. 20 instances  
B. 50 instances  
C. 100 instances  
D. It varies by instance type and region  

**Correct Answer:** D. It varies by instance type and region  
**Explanation:** The default limit on the number of EC2 instances varies based on the instance type and the region. AWS allows you to request increases if needed.

### 70. How can you improve the boot time of an EC2 instance?

A. By using a smaller instance type  
B. By optimizing the EC2 instance’s storage and configuration  
C. By using an EC2 instance with more CPU cores  
D. By disabling the instance’s Elastic IP address  

**Correct Answer:** B. By optimizing the EC2 instance’s storage and configuration  
**Explanation:** Optimizing storage, such as using General Purpose SSD (gp2) volumes and minimizing the number of services starting at boot, can improve boot times.
