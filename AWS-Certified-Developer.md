## AWS Certified Developer - Associate 2020

### IAM - Identity and Access Management

##### Using Multi-Factor Authentication (MFA) in AWS
* Virtual MFA devices.
* U2F security key.
* Hardware MFA device. 
* SMS text message-based MFA.

### AWS IAM allows you to:
* Manage IAM users and their access – You can create users in IAM, assign them individual security credentials (in other words, access keys, passwords, and multi-factor authentication devices), or request temporary security credentials to provide users access to AWS services and resources. You can manage permissions in order to control which operations a user can perform.
* Manage IAM roles and their permissions – You can create roles in IAM and manage permissions to control which operations can be performed by the entity, or AWS service, that assumes the role. You can also define which entity is allowed to assume the role. In addition, you can use service-linked roles to delegate permissions to AWS services that create and manage AWS resources on your behalf.
* Manage federated users and their permissions – You can enable identity federation to allow existing identities (users, groups, and roles) in your enterprise to access the AWS Management Console, call AWS APIs, and access resources, without the need to create an IAM user for each identity. Use any identity management solution that supports SAML 2.0, or use one of our federation samples (AWS Console SSO or API federation).

### EC2 101

Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers. Amazon EC2’s simple web service interface allows you to obtain and configure capacity with minimal friction. It provides you with complete control of your computing resources and lets you run on Amazon’s proven computing environment.

#### EC2 Options
* On Demand - allows ypou to pay a fixed rate by hour (or by second) with no commitment.
* Reserved - provides you with a capacity reservation, and offer a significant discount on the hourly charge for an instance 1year or 3 year terms.
* Spot - enables you to bid whatever price you want for instance capacity, providing for even greater savings if your applications jhave flexible start and end time.
* Dedicated Hosts - physical EC2 server dedicated for your user.

#### EC2 instance types

Amazon EC2 provides a wide selection of instance types optimized to fit different use cases. Instance types comprise varying combinations of CPU, memory, storage, and networking capacity and give you the flexibility to choose the appropriate mix of resources for your applications. Each instance type includes one or more instance sizes, allowing you to scale your resources to the requirements of your target workload.

F
I
G
H
T
D
R
M
C
P
X

#### What is EBS

Amazon EBS allows you to create storage volumes and attach them to Amazon EC2 instances.

#### EBS Volume Types
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