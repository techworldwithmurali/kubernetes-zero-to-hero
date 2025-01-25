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

### 71. How do you migrate an EC2 instance from one region to another?

A. By using EC2 Image Builder to create a new instance in the target region  
B. By creating an Amazon Machine Image (AMI) and copying it to the target region  
C. By modifying the instance’s region setting in the AWS Console  
D. By creating a CloudFormation template to deploy the instance in the target region  

**Correct Answer:** B. By creating an Amazon Machine Image (AMI) and copying it to the target region  
**Explanation:** You can create an AMI of the instance and then copy it to another region to launch a new instance.

### 72. What is the maximum number of EC2 security groups an instance can be associated with?

A. 5  
B. 10  
C. 15  
D. 5 per interface  

**Correct Answer:** D. 5 per interface  
**Explanation:** An EC2 instance can be associated with up to five security groups per network interface.

### 73. What is the primary benefit of using EC2 "Auto Scaling"?

A. It allows for automated software patching  
B. It reduces the overall cost of instances by automatically terminating unused instances  
C. It helps maintain application availability by automatically adjusting the number of instances  
D. It provides instant access to all EC2 instance types in any region  

**Correct Answer:** C. It helps maintain application availability by automatically adjusting the number of instances  
**Explanation:** Auto Scaling ensures that the application maintains the required number of instances to handle traffic load.

### 74. What are EC2 "Dedicated Hosts"?

A. EC2 instances that are hosted on dedicated physical hardware  
B. EC2 instances that have increased network throughput  
C. A tool for managing EC2 instance lifecycle  
D. EC2 instances that only support specific OS versions  

**Correct Answer:** A. EC2 instances that are hosted on dedicated physical hardware  
**Explanation:** EC2 Dedicated Hosts provide physical servers that are fully dedicated to your use, allowing you to meet licensing requirements and control instance placement.

### 75. What should you use to store persistent data that needs to survive even if the EC2 instance is terminated?

A. Elastic Load Balancer (ELB)  
B. Amazon S3  
C. Amazon EBS (Elastic Block Store)  
D. EC2 Instance Store  

**Correct Answer:** C. Amazon EBS (Elastic Block Store)  
**Explanation:** Amazon EBS provides persistent block-level storage that survives beyond instance termination and can be used as a boot volume or for storing data.

### 76. How can you connect an EC2 instance in a private subnet to the internet?

A. By assigning a public IP address to the EC2 instance  
B. By using a NAT Gateway or NAT instance in a public subnet  
C. By enabling VPC Peering between public and private subnets  
D. By creating an Elastic IP for the EC2 instance  

**Correct Answer:** B. By using a NAT Gateway or NAT instance in a public subnet  
**Explanation:** A NAT Gateway or NAT instance in a public subnet allows EC2 instances in private subnets to access the internet.

### 77. Which EC2 instance type is designed for compute-intensive applications?

A. T3  
B. C5  
C. R5  
D. M5  

**Correct Answer:** B. C5  
**Explanation:** The C5 instance type is optimized for compute-intensive applications and provides high-performance processors.

### 78. What is an EC2 "placement group"?

A. A logical grouping of EC2 instances to ensure low-latency network performance  
B. A way to group instances for cost optimization  
C. A grouping of EC2 instances that share a single EBS volume  
D. A logical grouping of EC2 instances for monitoring purposes  

**Correct Answer:** A. A logical grouping of EC2 instances to ensure low-latency network performance  
**Explanation:** Placement groups are used to control the placement of instances to meet specific needs for high network throughput or low latency.

### 79. What is the difference between EC2 "Spot Instances" and EC2 "Reserved Instances"?

A. Spot Instances are more expensive than Reserved Instances  
B. Spot Instances can be terminated by AWS, whereas Reserved Instances are not terminated  
C. Spot Instances are billed for a fixed term, while Reserved Instances are billed hourly  
D. Reserved Instances are only available in the US East region  

**Correct Answer:** B. Spot Instances can be terminated by AWS, whereas Reserved Instances are not terminated  
**Explanation:** Spot Instances allow you to bid for unused capacity at lower prices but can be terminated by AWS, whereas Reserved Instances provide a commitment for a term with discounted pricing.

### 80. What does EC2 "Instance Metadata" provide?

A. Information about the instance’s health and performance metrics  
B. Security credentials for accessing AWS services  
C. Data storage options for the instance  
D. Instance-specific configuration data, such as instance ID and AMI ID  

**Correct Answer:** D. Instance-specific configuration data, such as instance ID and AMI ID  
**Explanation:** Instance metadata provides access to configuration details such as instance ID, AMI ID, and other instance-related information.

### 81. How do you attach an EBS volume to a running EC2 instance?

A. Use the EC2 console to attach the EBS volume to the instance  
B. Manually connect the EBS volume to the instance using SSH  
C. Use CloudFormation to create a new instance and attach the volume  
D. Attach the EBS volume using EC2 Auto Scaling  

**Correct Answer:** A. Use the EC2 console to attach the EBS volume to the instance  
**Explanation:** You can attach an EBS volume to a running EC2 instance via the EC2 console, AWS CLI, or SDKs.

### 82. What is EC2 "instance metadata" commonly used for?

A. To store backup data from EC2 instances  
B. To query dynamic configuration information about the instance  
C. To enable automatic scaling of instances based on workload  
D. To automate EC2 instance termination  

**Correct Answer:** B. To query dynamic configuration information about the instance  
**Explanation:** Instance metadata allows EC2 instances to access information such as instance ID, public IP, and region, which can be used for automation and configuration purposes.

### 83. What can you use to manage EC2 instance lifecycle and configuration as code?

A. EC2 Auto Scaling  
B. AWS CloudFormation  
C. Amazon Inspector  
D. AWS Lambda  

**Correct Answer:** B. AWS CloudFormation  
**Explanation:** AWS CloudFormation allows you to define and manage EC2 instances, as well as other AWS resources, through code templates.

### 84. What is a key benefit of EC2 "On-Demand Instances"?

A. You can prepay for the instance’s lifetime  
B. You can access instances at a fixed price for long-term usage  
C. You can pay for the compute capacity by the second or hour without a long-term commitment  
D. You can get unlimited storage with EC2 On-Demand Instances  

**Correct Answer:** C. You can pay for the compute capacity by the second or hour without a long-term commitment  
**Explanation:** On-Demand Instances offer flexibility to pay for compute capacity based on usage, without requiring a long-term commitment.

### 85. How do you prevent an EC2 instance from being accidentally terminated?

A. By attaching an Elastic IP to the instance  
B. By enabling "termination protection" on the EC2 instance  
C. By using a private subnet for the instance  
D. By placing the instance inside an EC2 Auto Scaling group  

**Correct Answer:** B. By enabling "termination protection" on the EC2 instance  
**Explanation:** Termination protection prevents an EC2 instance from being terminated via the AWS console or API.


### 86. What is the primary purpose of EC2 "Elastic IP"?

A. To provide static IP addresses for EC2 instances that are associated with a specific region  
B. To allocate additional IP addresses to EC2 instances for better routing  
C. To provide dynamic IP addresses to EC2 instances  
D. To provide auto-scaling capabilities for EC2 instances  

**Correct Answer:** A. To provide static IP addresses for EC2 instances that are associated with a specific region  
**Explanation:** Elastic IPs allow you to associate a static IP address with your EC2 instance, which is useful for situations where you need a fixed public IP.

### 87. Which of the following is a benefit of using EC2 "Auto Scaling" with CloudWatch?

A. It automatically patches your instances  
B. It reduces the cost by scaling down unused instances based on real-time metrics  
C. It distributes traffic evenly across all EC2 instances  
D. It secures your EC2 instances against unauthorized access  

**Correct Answer:** B. It reduces the cost by scaling down unused instances based on real-time metrics  
**Explanation:** Auto Scaling, when integrated with CloudWatch, helps in scaling instances based on specific metrics like CPU usage, which ensures you only pay for what you use.

### 88. What is the purpose of "EC2 Instance Store"?

A. It provides persistent block-level storage for EC2 instances  
B. It provides temporary storage that is physically attached to the host computer  
C. It acts as a backup solution for EC2 instances  
D. It provides a network-based file system for EC2 instances  

**Correct Answer:** B. It provides temporary storage that is physically attached to the host computer  
**Explanation:** Instance Store is a temporary storage option that is physically attached to the host computer, which gets lost when the instance is stopped or terminated.

### 89. What type of Amazon EBS volume would you use for high-performance transactional workloads that require low latency?

A. Cold HDD (sc1)  
B. General Purpose SSD (gp2)  
C. Provisioned IOPS SSD (io1)  
D. Throughput Optimized HDD (st1)  

**Correct Answer:** C. Provisioned IOPS SSD (io1)  
**Explanation:** Provisioned IOPS SSD (io1) is designed for high-performance transactional workloads that require low latency and high throughput.

### 90. How would you ensure that an EC2 instance automatically recovers from failure?

A. By using EC2 Auto Scaling to replace the instance  
B. By using EC2 Instance Recovery feature to automatically recover from impaired states  
C. By creating an EC2 Backup schedule  
D. By enabling EC2 Instance Termination Protection  

**Correct Answer:** B. By using EC2 Instance Recovery feature to automatically recover from impaired states  
**Explanation:** The EC2 Instance Recovery feature automatically recovers instances from certain failure states such as instance reachability issues.

### 91. How do you increase the storage capacity of an EC2 instance’s EBS volume without downtime?

A. Detach the EBS volume, resize it, and reattach it  
B. Increase the EBS volume size from the EC2 console, then extend the filesystem  
C. Replace the EC2 instance with a larger instance  
D. Attach a new larger EBS volume and copy data from the old one  

**Correct Answer:** B. Increase the EBS volume size from the EC2 console, then extend the filesystem  
**Explanation:** You can increase the size of an EBS volume and then extend the filesystem without taking the instance offline.

### 92. What should you do if an EC2 instance is experiencing slow disk performance?

A. Increase the instance size to a larger type  
B. Attach additional EBS volumes and distribute load across them  
C. Migrate the EC2 instance to a different Availability Zone  
D. Disable EC2 instance monitoring to improve performance  

**Correct Answer:** B. Attach additional EBS volumes and distribute load across them  
**Explanation:** Attaching additional EBS volumes can help distribute the I/O load and improve disk performance for the EC2 instance.

### 93. How can you monitor EC2 instance performance over time?

A. By using EC2 CloudWatch metrics to track CPU, memory, and disk usage  
B. By using EC2 instance logs  
C. By manually inspecting the instance’s resource usage  
D. By using EC2 Auto Scaling metrics  

**Correct Answer:** A. By using EC2 CloudWatch metrics to track CPU, memory, and disk usage  
**Explanation:** AWS CloudWatch provides detailed performance metrics for EC2 instances, including CPU usage, memory, disk usage, and network activity.

### 94. What action is required if an EC2 instance is not accessible via SSH due to security group misconfiguration?

A. Restart the EC2 instance  
B. Modify the security group to allow SSH (port 22) access from your IP  
C. Terminate the EC2 instance and launch a new one  
D. Attach an Elastic IP to the instance to ensure connectivity  

**Correct Answer:** B. Modify the security group to allow SSH (port 22) access from your IP  
**Explanation:** If the security group is blocking SSH access, you can modify the inbound rules to allow access from your IP address.

### 95. What is the difference between EC2 "On-Demand Instances" and "Reserved Instances"?

A. On-Demand Instances have lower cost compared to Reserved Instances  
B. Reserved Instances provide savings for long-term use and require up-front payment  
C. Reserved Instances automatically scale with load  
D. On-Demand Instances require a minimum contract term  

**Correct Answer:** B. Reserved Instances provide savings for long-term use and require up-front payment  
**Explanation:** Reserved Instances offer a discount compared to On-Demand pricing in exchange for a one- or three-year commitment.

### 96. What is the default security group behavior for EC2 instances?

A. By default, EC2 instances can communicate with any IP address  
B. By default, EC2 instances can only communicate with instances in the same security group  
C. By default, EC2 instances can only communicate with other EC2 instances within the same VPC  
D. By default, EC2 instances are restricted from all inbound and outbound traffic  

**Correct Answer:** D. By default, EC2 instances are restricted from all inbound and outbound traffic  
**Explanation:** By default, a security group allows no inbound traffic and allows all outbound traffic.

### 97. How do you reduce latency in a multi-region EC2 architecture?

A. Use AWS Direct Connect to link regions  
B. Deploy EC2 instances in multiple regions and use a global Load Balancer  
C. Use EC2 Spot Instances in each region  
D. Use only EC2 instances in one region and scale vertically  

**Correct Answer:** B. Deploy EC2 instances in multiple regions and use a global Load Balancer  
**Explanation:** Deploying instances across multiple regions and utilizing a global load balancer can help reduce latency for users worldwide.

### 98. How do you protect sensitive data on an EC2 instance?

A. Encrypt the instance’s storage using Amazon EBS encryption  
B. Use EC2 Instance Metadata for secure storage  
C. Install a third-party encryption software on the instance  
D. Use only private IP addresses for communication  

**Correct Answer:** A. Encrypt the instance’s storage using Amazon EBS encryption  
**Explanation:** EBS encryption helps protect sensitive data stored on EC2 instances by encrypting data at rest.

### 99. How do you ensure that an EC2 instance can always access its metadata?

A. Disable instance metadata service on the EC2 instance  
B. Use a NAT Gateway to route requests to the instance metadata  
C. Ensure that the EC2 instance's security group allows access to the metadata endpoint  
D. Enable the instance metadata service on the instance’s IAM role  

**Correct Answer:** B. Use a NAT Gateway to route requests to the instance metadata  
**Explanation:** Using a NAT Gateway allows EC2 instances to access their metadata even when located in a private subnet.

### 100. Which tool can you use to automate the deployment of EC2 instances in a standardized and repeatable way?

A. AWS CloudFormation  
B. AWS Lambda  
C. AWS Systems Manager  
D. AWS Elastic Beanstalk  

**Correct Answer:** A. AWS CloudFormation  
**Explanation:** AWS CloudFormation allows you to define and deploy EC2 instances using infrastructure-as-code templates, ensuring repeatable and standardized deployments.

### 101. What feature of EC2 allows you to automatically distribute incoming application traffic across multiple instances?

A. EC2 Auto Scaling  
B. Elastic Load Balancing (ELB)  
C. EC2 Security Groups  
D. AWS CloudWatch  

**Correct Answer:** B. Elastic Load Balancing (ELB)  
**Explanation:** Elastic Load Balancing (ELB) automatically distributes incoming application traffic across multiple EC2 instances, ensuring high availability.

### 102. How can you monitor EC2 instance health and performance in real-time?

A. By using EC2 CloudWatch metrics and alarms  
B. By analyzing EC2 instance logs  
C. By accessing the EC2 dashboard directly  
D. By connecting the instance to AWS Lambda for performance updates  

**Correct Answer:** A. By using EC2 CloudWatch metrics and alarms  
**Explanation:** AWS CloudWatch provides real-time metrics on EC2 performance and allows you to set alarms for various instance health and performance parameters.

### 103. What happens when you stop and then start an EC2 instance?

A. The instance is moved to a different physical host  
B. The instance’s data stored on instance store volumes is lost  
C. The instance’s Elastic IP is automatically reassigned  
D. The instance configuration changes automatically  

**Correct Answer:** B. The instance’s data stored on instance store volumes is lost  
**Explanation:** Stopping and starting an EC2 instance results in the loss of data stored on instance store volumes. However, data on EBS volumes remains intact.

### 104. Which EC2 instance type is best suited for memory-intensive applications?

A. T3  
B. M5  
C. R5  
D. C5  

**Correct Answer:** C. R5  
**Explanation:** R5 instances are optimized for memory-intensive applications, providing a high memory-to-CPU ratio for workloads like databases and in-memory caches.

### 105. Which tool can help you automate the provisioning and management of EC2 instances at scale?

A. AWS Elastic Beanstalk  
B. AWS CloudFormation  
C. Amazon S3  
D. AWS Systems Manager  

**Correct Answer:** B. AWS CloudFormation  
**Explanation:** AWS CloudFormation automates the provisioning of EC2 instances and other AWS resources by defining them in infrastructure-as-code templates.

### 106. What is the maximum number of Elastic IP addresses that can be associated with a single AWS account?

A. 5  
B. 10  
C. 20  
D. 50  

**Correct Answer:** A. 5  
**Explanation:** By default, each AWS account can have up to five Elastic IP addresses. Additional Elastic IPs may require a request to AWS.

### 107. How can you improve the network performance of EC2 instances in your VPC?

A. By using EC2 instances with enhanced networking features like Elastic Network Adapter (ENA)  
B. By increasing the instance size to a larger type  
C. By disabling instance monitoring  
D. By attaching more EBS volumes to the instance  

**Correct Answer:** A. By using EC2 instances with enhanced networking features like Elastic Network Adapter (ENA)  
**Explanation:** Enhanced networking features such as ENA and EFA improve network performance by reducing latency and increasing throughput for EC2 instances.

### 108. Which of the following is a valid use case for EC2 "Spot Instances"?

A. Running critical applications that cannot tolerate interruptions  
B. Running long-running applications that need to maintain a constant instance uptime  
C. Running stateless or fault-tolerant workloads that can handle interruptions  
D. Running applications that require high availability at all times  

**Correct Answer:** C. Running stateless or fault-tolerant workloads that can handle interruptions  
**Explanation:** Spot Instances are suitable for workloads that are flexible and can handle interruptions, such as batch processing or data analysis jobs.

### 109. What feature can you use to store and replicate your EC2 instances across multiple Availability Zones?

A. Elastic Load Balancer (ELB)  
B. EC2 Auto Scaling  
C. EC2 Instance Recovery  
D. Amazon Machine Images (AMI)  

**Correct Answer:** B. EC2 Auto Scaling  
**Explanation:** EC2 Auto Scaling can distribute your instances across multiple Availability Zones to ensure high availability and fault tolerance.

### 110. What should you use if you need to ensure that an EC2 instance is always launched with the same configuration, such as specific software and security settings?

A. EC2 Launch Templates  
B. EC2 AMIs  
C. EC2 Snapshots  
D. EC2 Instance Types  

**Correct Answer:** B. EC2 AMIs  
**Explanation:** EC2 AMIs (Amazon Machine Images) allow you to create reusable configurations of an EC2 instance, including operating system, software, and settings, which can be launched repeatedly with the same configuration.

### 111. Which EC2 instance type is best suited for storage-intensive applications?

A. T3  
B. I3  
C. C5  
D. R5  

**Correct Answer:** B. I3  
**Explanation:** I3 instances are optimized for high storage throughput and low-latency storage, making them ideal for workloads like NoSQL databases and data warehousing.

### 112. What is the primary benefit of using EC2 "Dedicated Hosts"?

A. It provides high availability and redundancy  
B. It allows you to control the placement of instances on physical servers  
C. It enables the use of specialized GPUs for machine learning workloads  
D. It automatically manages instance scaling based on demand  

**Correct Answer:** B. It allows you to control the placement of instances on physical servers  
**Explanation:** EC2 Dedicated Hosts provide physical servers that are fully dedicated to your use, allowing you to control where instances are placed.

### 113. How can you assign a static IP address to an EC2 instance?

A. By using an Elastic IP  
B. By using a NAT Gateway  
C. By configuring a static private IP  
D. By assigning a public IP to the instance during launch  

**Correct Answer:** A. By using an Elastic IP  
**Explanation:** An Elastic IP allows you to assign a static, public IP address to your EC2 instance, which can be reassigned if necessary.

### 114. How do you secure an EC2 instance from unauthorized access?

A. By using EC2 security groups to restrict access to only trusted IP addresses  
B. By enabling EC2 Instance Termination Protection  
C. By enabling automatic software updates on the EC2 instance  
D. By using EC2 auto scaling to replace the instance if compromised  

**Correct Answer:** A. By using EC2 security groups to restrict access to only trusted IP addresses  
**Explanation:** EC2 security groups act as a virtual firewall to control inbound and outbound traffic to your EC2 instances, allowing you to restrict access to trusted sources.

### 115. What is the maximum number of EC2 instances that can be launched in a single availability zone?

A. 100  
B. 500  
C. 1000  
D. There is no set limit  

**Correct Answer:** D. There is no set limit  
**Explanation:** There is no hard limit on the number of EC2 instances in a specific Availability Zone, though other limits (e.g., EC2 instance limits) may apply based on your account.

### 116. How can you protect sensitive data in an EC2 instance from unauthorized access?

A. By using encryption at rest and in transit (e.g., with EBS encryption)  
B. By using EC2 Instance Store for storage  
C. By enabling EC2 Instance Metadata  
D. By using multiple security groups with strict access policies  

**Correct Answer:** A. By using encryption at rest and in transit (e.g., with EBS encryption)  
**Explanation:** Encrypting data at rest (with EBS encryption) and in transit (using SSL/TLS) ensures that sensitive data is protected from unauthorized access.

### 117. What happens when an EC2 instance is terminated?

A. The instance is stopped and can be restarted later  
B. The instance’s data is lost, and it cannot be restarted  
C. The instance’s Elastic IP is retained  
D. The instance is moved to another region  

**Correct Answer:** B. The instance’s data is lost, and it cannot be restarted  
**Explanation:** When an EC2 instance is terminated, its data stored on instance store volumes is lost, and the instance cannot be restarted.

### 118. Which of the following EC2 instance types is designed for GPU-based workloads like machine learning?

A. P3  
B. M5  
C. C5  
D. T3  

**Correct Answer:** A. P3  
**Explanation:** P3 instances are designed for GPU-based workloads such as machine learning and high-performance computing.

### 119. How can you prevent an EC2 instance from being accidentally terminated by someone?

A. Enable instance termination protection  
B. Set IAM policies to deny termination actions  
C. Use EC2 Auto Scaling to automatically replace terminated instances  
D. Use EC2 Instance Metadata to block termination  

**Correct Answer:** A. Enable instance termination protection  
**Explanation:** Instance termination protection prevents the accidental termination of an EC2 instance by ensuring it cannot be terminated from the AWS Console or API unless explicitly disabled.

### 120. What is the default behavior of EC2 Auto Scaling when a health check fails for an instance?

A. The instance is automatically stopped  
B. The instance is automatically terminated and replaced with a new one  
C. The instance is automatically rebooted  
D. The instance is flagged but not replaced  

**Correct Answer:** B. The instance is automatically terminated and replaced with a new one  
**Explanation:** EC2 Auto Scaling will replace unhealthy instances with new ones to maintain the desired capacity.

### 121. How can you ensure that EC2 instances are running in a specific Availability Zone for disaster recovery purposes?

A. By manually selecting the Availability Zone during the instance launch  
B. By using EC2 Instance Recovery  
C. By using a Load Balancer to distribute traffic  
D. By configuring the EC2 Auto Scaling group to prefer certain zones  

**Correct Answer:** A. By manually selecting the Availability Zone during the instance launch  
**Explanation:** During the EC2 instance launch, you can manually select an Availability Zone to ensure that your instances are placed in specific zones for disaster recovery.

### 122. Which EC2 instance type is most suitable for compute-heavy tasks like scientific computing?

A. C5  
B. T3  
C. R5  
D. I3  

**Correct Answer:** A. C5  
**Explanation:** C5 instances are optimized for compute-intensive workloads, offering high CPU performance for tasks such as scientific computing, gaming, and video encoding.

### 123. Which AWS service would you use to automate the patching of EC2 instances?

A. AWS Lambda  
B. AWS Systems Manager  
C. AWS CloudFormation  
D. Amazon S3  

**Correct Answer:** B. AWS Systems Manager  
**Explanation:** AWS Systems Manager allows you to automate patch management tasks for EC2 instances, keeping them up to date with the latest security patches.

### 124. Which of the following is NOT a valid EC2 instance storage option?

A. EBS Volumes  
B. EC2 Instance Store  
C. Amazon S3  
D. Amazon EFS  

**Correct Answer:** D. Amazon EFS  
**Explanation:** Amazon EFS is a managed file system for EC2 instances, but it is not considered an EC2 instance storage option like EBS or instance store.

### 125. What is the maximum number of EC2 instances you can launch per region?

A. 100  
B. 500  
C. 1000  
D. It depends on the instance type and other limits  

**Correct Answer:** D. It depends on the instance type and other limits  
**Explanation:** The maximum number of EC2 instances that can be launched per region depends on the instance type and the account's resource limits, which may vary.

### 126. Which EC2 instance type would be the best choice for high-performance computing applications that require fast access to large data sets stored locally?

A. M5  
B. I3  
C. P3  
D. R5  

**Correct Answer:** B. I3  
**Explanation:** I3 instances are optimized for workloads requiring high storage throughput and low-latency access to large datasets, such as NoSQL databases and data warehousing.

### 127. How can you prevent unauthorized users from accessing EC2 instances through SSH?

A. By creating a public-private key pair and restricting access in the security group  
B. By disabling SSH access for all users in the EC2 console  
C. By blocking access through IAM policies  
D. By using multi-factor authentication (MFA)  

**Correct Answer:** A. By creating a public-private key pair and restricting access in the security group  
**Explanation:** Using key pairs and security group rules can effectively prevent unauthorized SSH access to EC2 instances.

### 128. What happens if the EC2 instance's root volume is deleted?

A. The instance stops running but retains all data  
B. The instance stops running, and the data is lost  
C. The instance is terminated and replaced with a new one  
D. The instance continues running without the root volume  

**Correct Answer:** B. The instance stops running, and the data is lost  
**Explanation:** If the root volume of an EC2 instance is deleted, the instance will stop running, and any data on the volume will be lost unless it is backed up elsewhere.

### 129. Which EC2 pricing model is best suited for applications with unpredictable workloads?

A. On-Demand Instances  
B. Reserved Instances  
C. Spot Instances  
D. Savings Plans  

**Correct Answer:** A. On-Demand Instances  
**Explanation:** On-Demand Instances are ideal for workloads with unpredictable or spiky usage patterns, as you pay only for the compute capacity you use.

### 130. What is an Amazon EC2 "Launch Template"?

A. A predefined configuration for launching EC2 instances with specific parameters  
B. A configuration to automate scaling and load balancing of EC2 instances  
C. A tool for managing the lifecycle of EC2 instances  
D. A mechanism for ensuring high availability of EC2 instances  

**Correct Answer:** A. A predefined configuration for launching EC2 instances with specific parameters  
**Explanation:** A Launch Template is used to define instance parameters like AMI, instance type, key pair, security groups, and other configurations that are used when launching EC2 instances.

### 131. How can you restrict an EC2 instance to only communicate with other instances in the same VPC?

A. By configuring the instance’s security group to allow traffic only within the VPC  
B. By configuring the instance’s private IP address  
C. By disabling the instance’s public IP address  
D. By using a network ACL that restricts traffic to the VPC  

**Correct Answer:** A. By configuring the instance’s security group to allow traffic only within the VPC  
**Explanation:** Security groups can be configured to allow traffic only between instances within the same VPC, providing a level of isolation.

### 132. What is the key difference between EC2 "Spot Instances" and "On-Demand Instances"?

A. Spot Instances are always cheaper and have no termination risk  
B. Spot Instances allow you to bid for unused capacity at a discount, but they can be interrupted  
C. On-Demand Instances require a long-term commitment  
D. Spot Instances offer guaranteed availability of resources  

**Correct Answer:** B. Spot Instances allow you to bid for unused capacity at a discount, but they can be interrupted  
**Explanation:** Spot Instances allow you to take advantage of unused EC2 capacity at a discounted price, but they can be terminated by AWS when demand for resources increases.

### 133. Which EC2 instance type would you choose for applications that require high network throughput?

A. C5  
B. T3  
C. M5  
D. P3  

**Correct Answer:** A. C5  
**Explanation:** C5 instances are optimized for compute-intensive applications and provide high network throughput, making them ideal for high-performance computing and data processing workloads.

### 134. Which AWS service allows you to monitor and automatically respond to changes in your EC2 instances?

A. AWS CloudWatch  
B. AWS Lambda  
C. AWS Systems Manager  
D. AWS Inspector  

**Correct Answer:** A. AWS CloudWatch  
**Explanation:** AWS CloudWatch monitors EC2 instances and allows you to set alarms and automatic actions based on metrics like CPU utilization, memory usage, and network activity.

### 135. How do you increase the maximum number of EC2 instances in your AWS account?

A. By submitting a request to AWS Support to increase the instance limit  
B. By upgrading to a higher service tier  
C. By deleting unused instances  
D. By upgrading the region’s EC2 quota  

**Correct Answer:** A. By submitting a request to AWS Support to increase the instance limit  
**Explanation:** You can request an increase in the EC2 instance limit through AWS Support if you reach the maximum for your account.

### 136. What happens if an EC2 instance runs out of disk space on an EBS volume?

A. The instance will automatically scale to use more disk space  
B. The instance may become unresponsive or experience application failures  
C. The instance will terminate and restart  
D. The instance will automatically detach the EBS volume  

**Correct Answer:** B. The instance may become unresponsive or experience application failures  
**Explanation:** If the EBS volume runs out of disk space, the instance may encounter performance degradation or failure of applications relying on that volume.

### 137. Which EC2 instance type is best suited for applications that require a balance of compute, memory, and networking resources?

A. M5  
B. T3  
C. C5  
D. R5  

**Correct Answer:** A. M5  
**Explanation:** M5 instances provide a balanced mix of compute, memory, and networking resources, making them suitable for a wide variety of applications like web servers and databases.

### 138. Which service allows you to schedule EC2 instance starts and stops?

A. AWS Systems Manager  
B. AWS Lambda  
C. AWS CloudWatch Events  
D. EC2 Auto Scaling  

**Correct Answer:** C. AWS CloudWatch Events  
**Explanation:** AWS CloudWatch Events can be used to automate the scheduling of EC2 instance starts and stops based on specific time intervals.

### 139. How can you ensure high availability of EC2 instances in different regions?

A. By using EC2 Auto Scaling groups with cross-region replication  
B. By using an Elastic Load Balancer to route traffic across regions  
C. By deploying EC2 instances in multiple Availability Zones within a region  
D. By using AWS Global Accelerator  

**Correct Answer:** B. By using an Elastic Load Balancer to route traffic across regions  
**Explanation:** Elastic Load Balancers (ELB) can be used to route traffic to EC2 instances in different regions, providing high availability.

### 140. What is the purpose of using EC2 Instance Metadata?

A. To track billing and usage for EC2 instances  
B. To store user-specific information for applications  
C. To retrieve configuration data, such as instance ID, region, and AMI  
D. To monitor the health and performance of the instance  

**Correct Answer:** C. To retrieve configuration data, such as instance ID, region, and AMI  
**Explanation:** EC2 Instance Metadata provides information about the instance that can be accessed by the instance itself, such as its instance ID, public IP, and AMI used for launch.

### 141. What feature of EC2 instances allows you to quickly replicate your instance configuration and launch new instances with the same setup?

A. EC2 Auto Scaling  
B. EC2 AMIs  
C. EC2 Snapshots  
D. Elastic Load Balancing  

**Correct Answer:** B. EC2 AMIs  
**Explanation:** An Amazon Machine Image (AMI) captures the state of an EC2 instance and can be used to quickly launch new instances with the same configuration.

### 142. What is the primary benefit of using EC2 "Reserved Instances"?

A. Guaranteed instance availability at all times  
B. Significant cost savings for long-term workloads  
C. Flexible instance size and type changes  
D. Automatic scaling based on demand  

**Correct Answer:** B. Significant cost savings for long-term workloads  
**Explanation:** Reserved Instances offer a significant discount compared to On-Demand Instances for long-term usage commitments.

### 143. How do you enable SSL/TLS encryption on your EC2 instance?

A. By configuring security groups to allow HTTPS traffic  
B. By installing an SSL certificate on the web server  
C. By using AWS Certificate Manager (ACM)  
D. All of the above  

**Correct Answer:** D. All of the above  
**Explanation:** SSL/TLS encryption is enabled by installing an SSL certificate on the web server and allowing HTTPS traffic through the security group, along with using ACM for managing certificates.

### 144. Which EC2 instance type is optimized for workloads requiring deep learning and GPU processing?

A. G4  
B. P3  
C. T3  
D. M5  

**Correct Answer:** B. P3  
**Explanation:** P3 instances are optimized for deep learning, high-performance computing, and GPU-based processing tasks, providing high-speed data throughput and advanced GPU capabilities.

### 145. Which EC2 pricing model allows you to pay for compute capacity only when it is being used?

A. On-Demand Instances  
B. Reserved Instances  
C. Spot Instances  
D. Savings Plans  

**Correct Answer:** A. On-Demand Instances  
**Explanation:** On-Demand Instances allow you to pay for compute capacity only when it is used, making it suitable for workloads with unpredictable usage patterns.

### 146. How can you troubleshoot a situation where an EC2 instance is not responding?

A. By reviewing CloudWatch logs for any system issues  
B. By checking the EC2 instance status checks for hardware issues  
C. By reviewing the instance's security group and network ACL settings  
D. All of the above  

**Correct Answer:** D. All of the above  
**Explanation:** Troubleshooting involves checking CloudWatch logs, EC2 status checks, and reviewing security groups and network ACL settings for issues that may be preventing access.

### 147. How can you ensure that your EC2 instance is compliant with security policies, such as operating system hardening?

A. By using AWS Inspector to scan for vulnerabilities  
B. By setting up a security group with restricted access  
C. By applying security patches using AWS Systems Manager Patch Manager  
D. By using AWS Shield for protection  

**Correct Answer:** A. By using AWS Inspector to scan for vulnerabilities  
**Explanation:** AWS Inspector is a service that automatically assesses the EC2 instance for vulnerabilities and provides recommendations for remediation.

### 148. What is the best approach to move an EC2 instance from one VPC to another?

A. Create a snapshot of the instance and restore it in the new VPC  
B. Use VPC Peering to transfer the instance  
C. Manually configure the instance in the new VPC  
D. Use EC2 Image Builder to automate the migration  

**Correct Answer:** A. Create a snapshot of the instance and restore it in the new VPC  
**Explanation:** To move an EC2 instance to another VPC, you would typically create a snapshot of the instance and restore it in the new VPC.

### 149. What is the purpose of EC2 Auto Scaling?

A. To automatically scale the instance size based on load  
B. To automatically increase or decrease the number of EC2 instances based on demand  
C. To automatically replace terminated EC2 instances  
D. To automatically launch Spot Instances for additional capacity  

**Correct Answer:** B. To automatically increase or decrease the number of EC2 instances based on demand  
**Explanation:** EC2 Auto Scaling automatically adjusts the number of instances based on demand, helping maintain application performance and reduce costs.

### 150. Which of the following AWS services can be integrated with EC2 to provide centralized logging and monitoring?

A. AWS CloudWatch  
B. Amazon S3  
C. AWS Lambda  
D. Amazon RDS  

**Correct Answer:** A. AWS CloudWatch  
**Explanation:** AWS CloudWatch provides centralized logging and monitoring for EC2 instances, allowing you to track metrics, set alarms, and monitor application logs.


### 151. Which of the following is the primary benefit of using EC2 Spot Instances?

A. They provide guaranteed uptime  
B. They are available at a significant discount compared to On-Demand Instances  
C. They automatically scale with traffic  
D. They are always the most expensive instance type  

**Correct Answer:** B. They are available at a significant discount compared to On-Demand Instances  
**Explanation:** Spot Instances allow you to purchase unused EC2 capacity at a discount, but they can be interrupted by AWS when demand increases.

### 152. Which tool can be used to create an EC2 instance from an existing EC2 instance configuration?

A. EC2 Launch Wizard  
B. EC2 AMI (Amazon Machine Image)  
C. EC2 Auto Scaling  
D. EC2 Snapshot Manager  

**Correct Answer:** B. EC2 AMI (Amazon Machine Image)  
**Explanation:** You can create an EC2 AMI from an existing instance to replicate its configuration for future launches.

### 153. What is the main purpose of the EC2 Instance Metadata Service v2 (IMDSv2)?

A. To securely access instance metadata via HTTP requests with token-based authentication  
B. To manage instance lifecycle states  
C. To facilitate instance monitoring and auto-scaling  
D. To back up instance data regularly  

**Correct Answer:** A. To securely access instance metadata via HTTP requests with token-based authentication  
**Explanation:** IMDSv2 improves security by requiring token-based authentication for accessing instance metadata, reducing the risk of metadata exposure.

### 154. How do you connect to an EC2 instance if you’ve forgotten the SSH key pair?

A. By using EC2 Instance Connect  
B. By generating a new key pair and updating the instance  
C. By using an IAM role to reset the SSH key  
D. By stopping the instance and manually retrieving the key  

**Correct Answer:** A. By using EC2 Instance Connect  
**Explanation:** EC2 Instance Connect allows you to securely connect to an instance using SSH without needing the original key pair.

### 155. What is the maximum number of Elastic IPs that can be associated with a single EC2 instance?

A. 1  
B. 2  
C. 5  
D. 10  

**Correct Answer:** A. 1  
**Explanation:** Each EC2 instance can only have one Elastic IP associated with it. However, you can associate multiple Elastic IPs with different instances in your VPC.

### 156. Which EC2 feature helps reduce network bottlenecks by improving network performance for workloads requiring high throughput?

A. EC2 Enhanced Networking  
B. EC2 Auto Scaling  
C. EC2 Instance Store  
D. EC2 Load Balancer  

**Correct Answer:** A. EC2 Enhanced Networking  
**Explanation:** EC2 Enhanced Networking improves network throughput and reduces latency for workloads requiring high network performance.

### 157. How can you automatically assign a public IP to an EC2 instance when it is launched in a VPC?

A. By enabling the "Auto-assign Public IP" option in the subnet settings  
B. By using Elastic IP addresses  
C. By manually assigning a public IP address in the instance settings  
D. By using EC2 Instance Connect to assign the IP automatically  

**Correct Answer:** A. By enabling the "Auto-assign Public IP" option in the subnet settings  
**Explanation:** By enabling the "Auto-assign Public IP" option in the subnet settings, any instance launched in that subnet will automatically be assigned a public IP.

### 158. What is the purpose of EC2 Instance Store?

A. To provide persistent storage for EC2 instances  
B. To offer temporary storage that is lost when the instance is stopped or terminated  
C. To store backup data of EC2 instances  
D. To create and store EC2 AMIs  

**Correct Answer:** B. To offer temporary storage that is lost when the instance is stopped or terminated  
**Explanation:** EC2 Instance Store provides temporary block-level storage for EC2 instances, and the data is lost if the instance is stopped or terminated.

### 159. How does EC2 Auto Scaling maintain application availability?

A. By automatically increasing the instance size based on demand  
B. By maintaining a minimum number of running instances  
C. By distributing traffic across Availability Zones  
D. By scheduling instance startups and shutdowns  

**Correct Answer:** B. By maintaining a minimum number of running instances  
**Explanation:** EC2 Auto Scaling ensures high availability by automatically adding or removing instances to maintain the desired number of running instances.

### 160. Which of the following can be used to restrict inbound traffic to EC2 instances based on IP address or protocol?

A. VPC Flow Logs  
B. Security Groups  
C. IAM Policies  
D. AWS Shield  

**Correct Answer:** B. Security Groups  
**Explanation:** Security Groups act as virtual firewalls for EC2 instances, controlling inbound and outbound traffic based on IP address, protocol, and port.

### 161. Which EC2 instance type is optimized for memory-intensive applications?

A. C5  
B. M5  
C. R5  
D. T3  

**Correct Answer:** C. R5  
**Explanation:** R5 instances are optimized for memory-intensive applications, such as databases, in-memory caches, and big data processing.

### 162. How can you secure SSH access to EC2 instances to ensure that only specific users can connect?

A. By adding users to a security group  
B. By configuring IAM policies to control SSH access  
C. By using key pairs and restricting access in the instance’s security group  
D. By using EC2 Instance Connect only  

**Correct Answer:** C. By using key pairs and restricting access in the instance’s security group  
**Explanation:** SSH access can be secured by using key pairs and configuring the security group to only allow specific IP addresses.

### 163. What is the default security level of the EC2 instances’ root EBS volume at launch?

A. Unencrypted  
B. Encrypted with a default key  
C. Encrypted with a custom key  
D. Requires manual encryption  

**Correct Answer:** A. Unencrypted  
**Explanation:** By default, EC2 instances' root EBS volumes are not encrypted. However, encryption can be enabled at launch by selecting the "Encryption" option.

### 164. What does EC2 Instance Recovery do?

A. It automatically recovers EC2 instances in case of a failure  
B. It resets EC2 instance data and restarts the instance  
C. It restores deleted instances  
D. It ensures instances are always running  

**Correct Answer:** A. It automatically recovers EC2 instances in case of a failure  
**Explanation:** EC2 Instance Recovery is a feature that automatically recovers instances in case of hardware or underlying infrastructure failure.

### 165. Which of the following is a valid way to launch EC2 instances in multiple Availability Zones?

A. Use EC2 Auto Scaling with a Launch Template that specifies multiple zones  
B. Manually launch instances in each Availability Zone  
C. Use Elastic Load Balancing to spread traffic across zones  
D. All of the above  

**Correct Answer:** D. All of the above  
**Explanation:** EC2 instances can be launched in multiple Availability Zones using EC2 Auto Scaling, manually selecting zones during instance creation, or using Elastic Load Balancing to distribute traffic.

### 166. What happens if you stop and then start an EC2 instance that has an Elastic IP attached?

A. The Elastic IP is disassociated from the instance  
B. The Elastic IP is reassigned to a different instance  
C. The Elastic IP remains attached to the instance  
D. The instance automatically loses its Elastic IP  

**Correct Answer:** C. The Elastic IP remains attached to the instance  
**Explanation:** Elastic IPs remain associated with instances even after they are stopped and started again.

### 167. What is the purpose of "Placement Groups" in EC2?

A. To group EC2 instances for resource optimization and fault tolerance  
B. To distribute EC2 instances across different regions for better latency  
C. To group EC2 instances for easier billing  
D. To define network security settings for EC2 instances  

**Correct Answer:** A. To group EC2 instances for resource optimization and fault tolerance  
**Explanation:** Placement Groups allow you to place instances together to meet specific needs, such as low-latency, high-throughput, or fault-tolerance requirements.

### 168. Which EC2 instance type would be ideal for short-term, burstable workloads that require occasional high CPU performance?

A. C5  
B. M5  
C. T3  
D. R5  

**Correct Answer:** C. T3  
**Explanation:** T3 instances are ideal for workloads that have variable CPU demands and can benefit from burstable performance when needed.

### 169. What is the best practice for managing EC2 instance configurations across different environments (e.g., development, staging, production)?

A. Use EC2 Launch Templates for consistent configuration  
B. Manually configure each instance in each environment  
C. Use EC2 Snapshots to copy configurations across environments  
D. Use IAM policies to control configurations per environment  

**Correct Answer:** A. Use EC2 Launch Templates for consistent configuration  
**Explanation:** EC2 Launch Templates allow you to define and reuse instance configurations across multiple environments, ensuring consistency.

### 170. What would you use to monitor an EC2 instance’s resource utilization over time?

A. AWS CloudWatch  
B. EC2 Instance Metadata  
C. EC2 Security Groups  
D. AWS Config  

**Correct Answer:** A. AWS CloudWatch  
**Explanation:** AWS CloudWatch allows you to monitor EC2 instances' resource utilization (CPU, memory, disk I/O, etc.) in real-time.

### 171. How can you ensure that an EC2 instance has access to a specific VPC endpoint?

A. By configuring the instance’s security group to allow access to the VPC endpoint  
B. By associating the instance with a subnet that has a route to the VPC endpoint  
C. By configuring IAM roles to grant access to the endpoint  
D. All of the above  

**Correct Answer:** D. All of the above  
**Explanation:** Ensuring access to a VPC endpoint requires configuring security groups, routing, and IAM roles to grant the necessary permissions.

### 172. What should you do to improve the availability of an EC2 instance in case of hardware failure?

A. Use EC2 Auto Scaling to launch new instances  
B. Use EC2 Instance Recovery to automatically restart the instance  
C. Use Elastic Load Balancer to distribute traffic across multiple instances  
D. All of the above  

**Correct Answer:** D. All of the above  
**Explanation:** To improve availability, you can use Auto Scaling, Instance Recovery, and Load Balancing to ensure there are always available resources to handle traffic in case of failure.

### 173. How does EC2 Instance Store differ from EBS in terms of data persistence?

A. Instance Store is persistent, even if the instance is terminated  
B. EBS is non-persistent, while Instance Store is persistent  
C. Instance Store data is lost when the instance is stopped or terminated, but EBS data persists  
D. Both Instance Store and EBS data are persistent  

**Correct Answer:** C. Instance Store data is lost when the instance is stopped or terminated, but EBS data persists  
**Explanation:** Instance Store provides temporary storage that is lost when the instance is stopped or terminated, whereas EBS provides persistent storage that retains data even if the instance stops.


### 174. Which EC2 instance type is best for compute-intensive applications like batch processing or high-performance computing?

A. C5  
B. T3  
C. M5  
D. R5  

**Correct Answer:** A. C5  
**Explanation:** C5 instances are optimized for compute-intensive workloads, such as batch processing, scientific modeling, and high-performance computing.

### 175. How can you ensure the high availability of an EC2 instance in case of failure?

A. By using EC2 Auto Scaling across multiple Availability Zones  
B. By using a dedicated EC2 instance in each Availability Zone  
C. By deploying EC2 instances in a single Availability Zone  
D. By using a larger EC2 instance type  

**Correct Answer:** A. By using EC2 Auto Scaling across multiple Availability Zones  
**Explanation:** EC2 Auto Scaling across multiple Availability Zones ensures that your application remains highly available by distributing the instances across different zones.

### 176. Which of the following is a method for backing up data stored on EC2 instances?

A. Create an EC2 Snapshot of the EBS volume  
B. Use EC2 Instance Recovery  
C. Enable CloudWatch monitoring  
D. Create a new IAM policy for backup  

**Correct Answer:** A. Create an EC2 Snapshot of the EBS volume  
**Explanation:** EC2 Snapshots allow you to back up the state of an EBS volume, enabling you to restore or replicate the volume later.

### 177. Which EC2 pricing model offers the most cost-effective solution for workloads with predictable usage patterns?

A. On-Demand Instances  
B. Spot Instances  
C. Reserved Instances  
D. Savings Plans  

**Correct Answer:** C. Reserved Instances  
**Explanation:** Reserved Instances provide significant cost savings for workloads with predictable usage patterns by committing to a one- or three-year term.

### 178. What would you use to launch EC2 instances with custom configurations like instance type, AMI, and storage options?

A. EC2 Launch Templates  
B. EC2 Instance Types  
C. EC2 Auto Scaling  
D. EC2 Snapshots  

**Correct Answer:** A. EC2 Launch Templates  
**Explanation:** EC2 Launch Templates allow you to define instance configurations, including instance type, AMI, storage options, and more, for easy instance deployment.

### 179. Which AWS service allows you to configure automatic recovery of EC2 instances when they become impaired due to underlying hardware failure?

A. EC2 Auto Scaling  
B. EC2 Instance Recovery  
C. AWS Systems Manager  
D. AWS CloudFormation  

**Correct Answer:** B. EC2 Instance Recovery  
**Explanation:** EC2 Instance Recovery automatically recovers instances in case of underlying hardware failure or system impairment.

### 180. What is the main limitation of EC2 Spot Instances?

A. They cannot be used with Auto Scaling  
B. They can be terminated by AWS with little notice  
C. They do not support Elastic IPs  
D. They require long-term contracts  

**Correct Answer:** B. They can be terminated by AWS with little notice  
**Explanation:** Spot Instances are subject to termination by AWS when the capacity is needed for On-Demand Instances, which is the main limitation of using them.

### 181. How can you ensure that your EC2 instances remain secure by restricting access only to trusted IP addresses?

A. By using VPC Security Groups  
B. By applying IAM roles to control access  
C. By using EC2 Key Pairs  
D. By enabling AWS CloudTrail logging  

**Correct Answer:** A. By using VPC Security Groups  
**Explanation:** VPC Security Groups allow you to define inbound and outbound traffic rules based on IP address, ensuring only trusted IPs can access the instance.

### 182. What is the recommended storage solution for EC2 instances requiring low-latency, high-throughput access to data?

A. EC2 Instance Store  
B. Amazon EBS with Provisioned IOPS (io1 or io2)  
C. Amazon S3  
D. AWS Glacier  

**Correct Answer:** B. Amazon EBS with Provisioned IOPS (io1 or io2)  
**Explanation:** Amazon EBS with Provisioned IOPS (io1 or io2) provides low-latency, high-throughput storage suitable for performance-sensitive workloads.

### 183. What should you do to launch an EC2 instance within a VPC and ensure that the instance is publicly accessible?

A. Associate an Elastic IP with the instance  
B. Launch the instance in a private subnet and enable NAT  
C. Use EC2 Instance Connect to access the instance  
D. Configure the instance to use a VPC security group with open SSH ports  

**Correct Answer:** A. Associate an Elastic IP with the instance  
**Explanation:** To make the EC2 instance publicly accessible, you should associate an Elastic IP with the instance, allowing it to have a public IP address.

### 184. What is the benefit of EC2 Auto Scaling?

A. It helps you maintain application availability by automatically adjusting the number of running instances  
B. It automatically scales EC2 instances to different regions  
C. It improves network performance by adding more instances  
D. It helps you reduce instance size based on traffic demand  

**Correct Answer:** A. It helps you maintain application availability by automatically adjusting the number of running instances  
**Explanation:** EC2 Auto Scaling ensures high availability by adding or removing instances based on demand, maintaining consistent application performance.

### 185. Which AWS service allows you to monitor and store log data from EC2 instances?

A. AWS CloudTrail  
B. AWS Config  
C. AWS CloudWatch Logs  
D. AWS Lambda  

**Correct Answer:** C. AWS CloudWatch Logs  
**Explanation:** AWS CloudWatch Logs collects and stores log data from EC2 instances, allowing for monitoring and troubleshooting.

### 186. Which of the following would you use to run applications that need consistent CPU performance?

A. EC2 T3 Instances  
B. EC2 M5 Instances  
C. EC2 C5 Instances  
D. EC2 R5 Instances  

**Correct Answer:** B. EC2 M5 Instances  
**Explanation:** EC2 M5 instances provide balanced compute, memory, and networking resources, making them ideal for workloads requiring consistent performance.

### 187. How can you ensure that your EC2 instances are encrypted by default when launched?

A. By selecting the encryption option in the EC2 launch wizard  
B. By using EC2 Key Pairs  
C. By configuring IAM policies for encryption  
D. By enabling encryption in the EC2 Security Group  

**Correct Answer:** A. By selecting the encryption option in the EC2 launch wizard  
**Explanation:** You can enable encryption for EBS volumes during instance launch by selecting the encryption option in the launch wizard.

### 188. Which EC2 instance type is ideal for applications with varying CPU demands that require bursts of high CPU performance?

A. M5  
B. C5  
C. T3  
D. R5  

**Correct Answer:** C. T3  
**Explanation:** T3 instances are burstable and ideal for workloads that have variable CPU demands, with occasional bursts of high performance.

### 189. What is the purpose of EC2 Placement Groups for workloads requiring low latency and high throughput?

A. To optimize instance performance by distributing them across different regions  
B. To group instances together to minimize network latency  
C. To enable fault tolerance by spreading instances across multiple Availability Zones  
D. To improve security by placing instances in isolated subnets  

**Correct Answer:** B. To group instances together to minimize network latency  
**Explanation:** EC2 Placement Groups can be used to place instances together to minimize network latency for applications requiring high throughput and low latency.

### 190. What would you use to enable SSH access to an EC2 instance from an on-premises server?

A. Configure the instance's security group to allow inbound SSH traffic from the server’s IP  
B. Use IAM roles to grant SSH access  
C. Enable SSH tunneling via AWS VPN  
D. Use EC2 Instance Connect to provide SSH access  

**Correct Answer:** A. Configure the instance's security group to allow inbound SSH traffic from the server’s IP  
**Explanation:** To enable SSH access from an on-premises server, you need to configure the EC2 instance’s security group to allow inbound SSH traffic from the server’s IP address.

### 191. How can you monitor the health of EC2 instances within an Auto Scaling group?

A. Use EC2 Instance Metadata  
B. Set up CloudWatch Alarms to track instance performance  
C. Use EC2 Status Checks  
D. Enable CloudTrail logs for EC2  

**Correct Answer:** B. Set up CloudWatch Alarms to track instance performance  
**Explanation:** CloudWatch Alarms can be used to monitor EC2 instances' health within Auto Scaling groups, tracking CPU utilization, memory, and other metrics.

### 192. What is the difference between an EC2 Instance Store and EBS?

A. Instance Store provides persistent storage, while EBS is temporary  
B. Instance Store is faster but not persistent, while EBS provides persistent storage  
C. EBS is used only for large applications, while Instance Store is for small data  
D. Both Instance Store and EBS are persistent storage options  

**Correct Answer:** B. Instance Store is faster but not persistent, while EBS provides persistent storage  
**Explanation:** Instance Store offers high-speed, temporary storage that is lost when the instance stops or terminates, while EBS provides persistent storage.

### 193. What AWS service allows you to create and manage EC2 instances across multiple regions and Availability Zones?

A. AWS Lambda  
B. AWS CloudFormation  
C. AWS EC2 Auto Scaling  
D. AWS Elastic Beanstalk  

**Correct Answer:** B. AWS CloudFormation  
**Explanation:** AWS CloudFormation allows you to automate the creation and management of EC2 instances across multiple regions and Availability Zones through infrastructure-as-code templates.

### 194. How do you manage EC2 instance lifecycle events, such as terminations and instance starts, across a fleet of instances?

A. AWS Systems Manager  
B. AWS CloudWatch Events  
C. EC2 Auto Scaling Policies  
D. IAM User Permissions  

**Correct Answer:** B. AWS CloudWatch Events  
**Explanation:** CloudWatch Events can be used to automatically trigger actions in response to EC2 instance lifecycle events, such as instance start or termination.

### 195. What would you use to automatically back up EC2 instance data on a regular schedule?

A. EC2 Snapshots with scheduled backup  
B. AWS Backup  
C. EC2 Auto Scaling  
D. AWS DataSync  

**Correct Answer:** B. AWS Backup  
**Explanation:** AWS Backup provides centralized, automated backup management for EC2 instances and other AWS services.

### 196. What feature of EC2 instances allows you to manage virtual machine hypervisor settings?

A. EC2 Image Builder  
B. EC2 Placement Groups  
C. EC2 Instance Metadata  
D. EC2 Hypervisor  

**Correct Answer:** D. EC2 Hypervisor  
**Explanation:** EC2 Hypervisor enables the management of virtual machine configurations within the EC2 instance, including resource allocation and scheduling.

### 197. How would you make an EC2 instance automatically scale based on CPU usage?

A. Use EC2 Auto Scaling with a CPU utilization trigger  
B. Use EC2 Instance Recovery  
C. Modify EC2 security

 group rules for scaling  
D. Use Elastic Load Balancing to scale the instance  

**Correct Answer:** A. Use EC2 Auto Scaling with a CPU utilization trigger  
**Explanation:** EC2 Auto Scaling allows you to scale instances automatically based on metrics like CPU utilization, ensuring efficient resource use.

### 198. What EC2 pricing model is best for a workload with unpredictable usage and cannot afford to be interrupted?

A. Spot Instances  
B. Reserved Instances  
C. On-Demand Instances  
D. Savings Plans  

**Correct Answer:** C. On-Demand Instances  
**Explanation:** On-Demand Instances are the best choice for workloads with unpredictable usage that cannot tolerate interruptions, offering flexibility without long-term commitment.

### 199. What method allows EC2 instances to communicate securely within a VPC?

A. Use of Private IP Addresses  
B. EC2 Security Groups and Network ACLs  
C. Elastic IPs for private communication  
D. EC2 Instance Role Policies  

**Correct Answer:** B. EC2 Security Groups and Network ACLs  
**Explanation:** EC2 Security Groups and Network ACLs are used to control traffic to and from EC2 instances within a VPC, ensuring secure communication.

### 200. Which EC2 instance type is optimized for memory-intensive applications like large databases or in-memory caches?

A. C5  
B. R5  
C. T3  
D. M5  

**Correct Answer:** B. R5  
**Explanation:** R5 instances are optimized for memory-intensive applications such as high-performance databases and in-memory caches.
