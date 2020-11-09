# Total Score 78%

## Questions Answered Wrong

### You have been evaluating the NACLs in your company. Currently, you are looking at the default network ACL. What is true about the default network ACL?

***Correct Answers:***

You can add or remove rules from the default network ACL.

***My Answers:***

You cannot edit the default NACL.

***Explanation:***

Incorrect. The default network ACL is configured to allow all traffic to flow in and out of the subnets with which it is associated. Each network ACL also includes a rule whose rule number is an asterisk. This rule ensures that if a packet doesn't match any of the other numbered rules, it's denied. You can't modify or remove this rule.

The default network ACL is configured to allow all traffic to flow in and out of the subnets with which it is associated. Each network ACL also includes a rule whose rule number is an asterisk. This rule ensures that if a packet doesn't match any of the other numbered rules, it's denied. You can't modify or remove this rule.

***Links:***

[Default network ACL](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html#default-network-acl)

### You have been evaluating the NACLS in your company. Most of the NACLs are configured the same: 100 All Traffic Allow 200 All Traffic Deny '' All Traffic Deny What function does the '' rule perform?

***Correct Answers:***

This rule ensures that if a packet doesn't match any of the other numbered rules, it's denied.

***My Answers:***

It is there in case no other rules are defined.

***Explanation:***

This rule ensures that if a packet doesn't match any of the other numbered rules, it's denied.

The default network ACL is configured to allow all traffic to flow in and out of the subnets with which it is associated. Each network ACL also includes a rule whose rule number is an asterisk. This rule ensures that if a packet doesn't match any of the other numbered rules, it's denied. You can't modify or remove this rule.

***Links:***

[Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)


### Your company is using a hybrid configuration because there are some legacy applications which are not easily converted and migrated to AWS. And with this configuration comes a typical scenario where the legacy apps must maintain the same private IP address and MAC address. You are attempting to convert the application to the cloud and have configured an EC2 instance to house the application. What you are currently testing is removing the ENI from the legacy instance and attaching it to the EC2 instance. You want to attempt a cold attach. What does this mean?

***Correct Answers:***

Attach ENI when the instance is being launched.

***My Answers:***

Attach ENI before the public IP address is assigned.

***Explanation:***

Incorrect. This is not a specific option.

Best practices for configuring network interfaces You can attach a network interface to an instance when it's running (hot attach), when it's stopped (warm attach), or when the instance is being launched (cold attach). You can detach secondary network interfaces when the instance is running or stopped. However, you can't detach the primary network interface. You can move a network interface from one instance to another, if the instances are in the same Availability Zone and VPC but in different subnets. When launching an instance using the CLI, API, or an SDK, you can specify the primary network interface and additional network interfaces. Launching an Amazon Linux or Windows Server instance with multiple network interfaces automatically configures interfaces, private IPv4 addresses, and route tables on the operating system of the instance. A warm or hot attach of an additional network interface may require you to manually bring up the second interface, configure the private IPv4 address, and modify the route table accordingly. Instances running Amazon Linux or Windows Server automatically recognize the warm or hot attach and configure themselves. Attaching another network interface to an instance (for example, a NIC teaming configuration) cannot be used as a method to increase or double the network bandwidth to or from the dual-homed instance. If you attach two or more network interfaces from the same subnet to an instance, you may encounter networking issues such as asymmetric routing. If possible, use a secondary private IPv4 address on the primary network interface instead. For more information, see Assigning a secondary private IPv4 address.

***Links:***

[Elastic network interfaces](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html)

### A software company has created an application to capture service requests from users and also enhancement requests. The application is deployed on an Auto Scaling Group of EC2 instances fronted by an Application Load Balancer. The Auto Scaling Group has scaled to maximum capacity, but there are still requests being lost. The company has decided to use SQS with the Auto Scaling Group to ensure all messages are saved and processed. What is an appropriate metric for auto scaling with SQS?

***Correct Answers:***

backlog per instance

***My Answers:***

backlog per hour

***Explanation:***

Incorrect. This is not a valid metric.

The issue with using a CloudWatch Amazon SQS metric like ApproximateNumberOfMessagesVisible for target tracking is that the number of messages in the queue might not change proportionally to the size of the Auto Scaling Group that processes messages from the queue. That's because the number of messages in your SQS queue does not solely define the number of instances needed. The number of instances in your Auto Scaling Group can be driven by multiple factors, including how long it takes to process a message and the acceptable amount of latency (queue delay). The solution is to use a backlog per instance metric with the target value being the acceptable backlog per instance to maintain. You can calculate these numbers as follows: Backlog per instance: To calculate your backlog per instance, start with the ApproximateNumberOfMessages queue attribute to determine the length of the SQS queue (number of messages available for retrieval from the queue). Divide that number by the fleet's running capacity, which for an Auto Scaling Group is the number of instances in the InService state, to get the backlog per instance.

***Links:***

[Scaling based on Amazon SQS](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-using-sqs-queue.html)

### You are working as a Solutions Architect in a large healthcare organization. You have many Auto Scaling Groups that you need to create. One requirement is that you need to reuse some software licenses and therefore need to use dedicated hosts on EC2 instances in your Auto Scaling Groups. What step must you take to meet this requirement?

***Correct Answers:***

Use a launch template with your Auto Scaling Group.

***My Answers:***

Make sure your launch configurations are using Dedicated Hosts.

***Explanation:***

Incorrect. Using Dedicated Hosts is the end goal, but this can't be achieved with launch configurations. Launch templates are needed to use Dedicated Hosts.

In addition to the features of Amazon EC2 Auto Scaling that you can configure by using launch templates, launch templates provide more advanced Amazon EC2 configuration options. For example, you must use launch templates to use Amazon EC2 Dedicated Hosts. Dedicated Hosts are physical servers with EC2 instance capacity that are dedicated to your use. While Amazon EC2 Dedicated Instances also run on dedicated hardware, the advantage of using Dedicated Hosts over Dedicated Instances is that you can bring eligible software licenses from external vendors and use them on EC2 instances. If you currently use launch configurations, you can specify a launch template when you update an Auto Scaling group that was created using a launch configuration. To create a launch template to use with an Auto Scaling Group, create the template from scratch, create a new version of an existing template, or copy the parameters from a launch configuration, running instance, or other template.

***Links:***

[Launch templates](https://docs.aws.amazon.com/autoscaling/ec2/userguide/LaunchTemplates.html)

### Your company is using a hybrid configuration because there are some legacy applications which are not easily converted and migrated to AWS. And with this configuration comes a typical scenario where the legacy apps must maintain the same private ip address and MAC address. You are attempting to convert the application to the Cloud and have configured an EC2 instance to house the application. What you are currently testing is removing the ENI from the legacy instance and attaching it to the EC2 instance. You want to attempt a warm attach. What does this mean?

***Correct Answers:***

Attach ENI When it’s stopped.

***My Answers:***

Attach ENI to an instance when it's running.

***Explanation:***

Incorrect. This is a hot attach.

Some best practices for configuring network interfaces: You can attach a network interface to an instance when it's running (hot attach), when it's stopped (warm attach), or when the instance is being launched (cold attach). You can detach secondary network interfaces when the instance is running or stopped. However, you can't detach the primary network interface. You can move a network interface from one instance to another, if the instances are in the same Availability Zone and VPC but in different subnets. When launching an instance using the CLI, API, or an SDK, you can specify the primary network interface and additional network interfaces. Launching an Amazon Linux or Windows Server instance with multiple network interfaces automatically configures interfaces, private IPv4 addresses, and route tables on the operating system of the instance. A warm or hot attach of an additional network interface may require you to manually bring up the second interface, configure the private IPv4 address, and modify the route table accordingly. Instances running Amazon Linux or Windows Server automatically recognize the warm or hot attach and configure themselves. Attaching another network interface to an instance (for example, a NIC teaming configuration) cannot be used as a method to increase or double the network bandwidth to or from the dual-homed instance. If you attach two or more network interfaces from the same subnet to an instance, you may encounter networking issues such as asymmetric routing. If possible, use a secondary private IPv4 address on the primary network interface instead. For more information, see Assigning a secondary private IPv4 address.

***Links:***

[Elastic network interfaces](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html)

### You have taken over management of several instances in the company AWS environment. You want to quickly review scripts used to bootstrap the instances at runtime. A URL command can be used to do this. What can you append to the URL http://169.254.169.254/latest/ to retrieve this data?

***Correct Answers:***

user-data/

***My Answers:***

meta-data/

***Explanation:***

Incorrect. You would use user-data to configure EC2 instances.

When you launch an instance in Amazon EC2, you have the option of passing user data to the instance that can be used to perform common automated configuration tasks and even run scripts after the instance starts. You can pass two types of user data to Amazon EC2: shell scripts and cloud-init directives.

When you launch an instance in Amazon EC2, you have the option of passing user data to the instance that can be used to perform common automated configuration tasks and even run scripts after the instance starts. You can pass two types of user data to Amazon EC2: shell scripts and cloud-init directives.

***Links:***

* [Working with instance user data](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instancedata-add-user-data.html)
* [Instance metadata and user data](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2-instance-metadata.html)
* [User data and shell scripts](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/user-data.html#user-data-shell-scripts)
* [Instance metadata and user data](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2-instance-metadata.html)
* 