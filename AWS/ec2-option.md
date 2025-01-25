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
