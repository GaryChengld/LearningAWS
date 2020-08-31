## AWS Certified Developer - Associate 2020

[AWS Certified Developer–Associate(DVA-C01) Examination Guide](https://d1.awsstatic.com/training-and-certification/docs-dev-associate/AWS_Certified_Developer_Associate-Exam_Guide_EN_1.4.pdf)
[AWS Best Practices](https://d1.awsstatic.com/whitepapers/AWS_Cloud_Best_Practices.pdf)

### IAM - Identity and Access Management

##### Using Multi-Factor Authentication (MFA) in AWS
* Virtual MFA devices.
* U2F security key.
* Hardware MFA device. 
* SMS text message-based MFA.

#### AWS IAM allows you to:
* Manage IAM users and their access – You can create users in IAM, assign them individual security credentials (in other words, access keys, passwords, and multi-factor authentication devices), or request temporary security credentials to provide users access to AWS services and resources. You can manage permissions in order to control which operations a user can perform.
* Manage IAM roles and their permissions – You can create roles in IAM and manage permissions to control which operations can be performed by the entity, or AWS service, that assumes the role. You can also define which entity is allowed to assume the role. In addition, you can use service-linked roles to delegate permissions to AWS services that create and manage AWS resources on your behalf.
* Manage federated users and their permissions – You can enable identity federation to allow existing identities (users, groups, and roles) in your enterprise to access the AWS Management Console, call AWS APIs, and access resources, without the need to create an IAM user for each identity. Use any identity management solution that supports SAML 2.0, or use one of our federation samples (AWS Console SSO or API federation).

[Identities (Users, Groups, and Roles)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html?icmpid=docs_iam_console)

#### IAM roles are a secure way to grant permissions to entities that you trust. Examples of entities include the following:

* IAM user in another account
* Application code running on an EC2 instance that needs to perform actions on AWS resources
* An AWS service that needs to act on resources in your account to provide its features
* Users from a corporate directory who use identity federation with SAML
* IAM roles issue keys that are valid for short durations, making them a more secure way to grant access.

### EC2 - Amazon Elastic Compute Cloud

Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers. Amazon EC2’s simple web service interface allows you to obtain and configure capacity with minimal friction. It provides you with complete control of your computing resources and lets you run on Amazon’s proven computing environment.

#### EC2 Options
* On Demand - allows ypou to pay a fixed rate by hour (or by second) with no commitment.
* Reserved - provides you with a capacity reservation, and offer a significant discount on the hourly charge for an instance 1year or 3 year terms.
* Spot - enables you to bid whatever price you want for instance capacity, providing for even greater savings if your applications jhave flexible start and end time.
* Dedicated Hosts - physical EC2 server dedicated for your user.

#### EC2 instance types

Amazon EC2 provides a wide selection of instance types optimized to fit different use cases. Instance types comprise varying combinations of CPU, memory, storage, and networking capacity and give you the flexibility to choose the appropriate mix of resources for your applications. Each instance type includes one or more instance sizes, allowing you to scale your resources to the requirements of your target workload.

* General Purpose: The most popular; used for web servers, development environments, etc.
* Compute Optimized: Good for compute-intensive applications such as some scientific modeling or high-performance web servers.
* Memory Optimized: Used for anything that needs memory-intensive applications, such as real-time big data analytics, or running Hadoop or Spark.
* Accelerated Computing: Include additional hardware (GPUs, FPGAs) to provide massive amounts of parallel processing for tasks such as graphics processing.
* Storage Optimized: Ideal for tasks that require huge amounts of storage, specifically with sequential read-writes, such as log processing.

<img src="https://cloudacademy.com/wp-content/uploads/2016/12/ec2-types-vertical.jpg">

FIGHT-DR-MC-PX


#### EC2 Cheat Sheet
  ![EC2-CheatSheet](https://user-images.githubusercontent.com/3359299/91666421-9c03a780-eaca-11ea-8166-ff7512482bb4.PNG)

#### What is EBS

Amazon EBS allows you to create storage volumes and attach them to Amazon EC2 instances.

EBS Volume Types
* General Purpose SSD (GP2)
* Provisioned IOPS SSD (I01)
* Throughput Optimized HDD (ST1)
* Cold HDD (SC1)
* Magnetic (Standard)

#### Create EC2 instance

* Save keypair
* puttygen to generate ppk format file
* putty
  * host name: ec2-user@<ec2 ipaddress>
  * SSH -> Auth -> select private key file
  * Open session
```
  sudo su
  yum update -y
  yum install httpd
  service httpd start
  chkconfig httpd on
```
  * create index.html under /var/www/html (nano command)

##### Install node js on EC2
1. Connect to your Linux instance as ec2-user using SSH.  
2. Install node version manager (nvm) by typing the following at the command line.
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
```
3 Activate nvm by typing the following at the command line.
```
. ~/.nvm/nvm.sh
```
4. Use nvm to install the latest version of Node.js by typing the following at the command line.
```
nvm install node
```
5. Test that Node.js is installed and running correctly by typing the following at the command line.
```
node -e "console.log('Running Node.js ' + process.version)"
```

#### Elastic load balancers

Type of Load balancers

* Application Load Balancer
* Network Load Balancer
* Classic Load Balancer

Application load balancers are bust suited for load balancing of HTTP/HTTPS traffic. They operate at layer 7 and are application-aware.\
Network load balancers are best suited for load balancing of TCP traffic where extreme performance is required.Operating at the connection level (Layer 4).\
Classic load balancers are the lagacy Elastic Load Balancers. You can load balance HTTP/HTTPS applications and use Layer 7-specific features, such as X-Forwarded and sticky sessions. Ypou can alspo user strict Layer 4 load balancing for applications that rely purely on the TCP protocol.\

Load Balancer Errors\
* 504 error means gateway has time out. This means that the application not responding within the idle timeout period. Trouble shoot the application. Is it the web server or datbase server issue?\

If you need the IPv4 address of your end user, look for the X-Forwrded-For header.

#### Route53

* Route53 is Amazon's DNS service
* Allows you to map your domain name to
  * EC2 instances.
  * Load Balancers.
  * S3 Buckets.

#### EC2 Cli
1. Add user with programmatic access
2. Open SSH
3. AWS configure
```
aws configure
```
List S3 bucket
```
aws s3 ls
```
Create s3 bucket
```
aws s3 mb s://<bucket-name>
```
copy file to s3
```
aws s3 cp <filename> s3://<bucket-name>
```
list s3 bucket
```
aws s3 ls s3://<bucket-name>
```

[AWS cli commanmd reference](https://docs.aws.amazon.com/cli/latest/)


CLI Tips
* Least Privilege - Always give your users the minimun amount of access required.
* Create Groups - Assign your users to groups. Your users will automatically inherit the permissions of the group. The groups permissions are assigned using policy document.
* Secret Access Key - You will see this only once. If you do not save it, you can delete the key pair and regenerate it. You will need to run aws configure again.
* Do not use just one access key - Do nmpt create just one access key and share that with all your developers. If someone leaves the company on bad terms, then yoou will need to delete the key and create a new one and every developer would then need to update their keys. Instead create one key pair per developer.
* You can use the CLI on your PC - You can install the CLI on your Mac, Linix or Windows PC. 

#### EC2 with S3 role

* Create role for EC2 service with S3 full access
* Go to EC2 -> Instance, select EC2 instance
* Action -> Instance setting-> Attach/Replace IAM Role
* Select the role and apply

Exam Tips
* Roles allow you to not use access key ID's and secret access keys
* Roles are preferred from a security perspective
* Roles are controlled by policies
* You can change a policy on a role and it will take immediate affect
* You can attach and detach roels to running EC2 instance without having to stop or terminate these instances.

