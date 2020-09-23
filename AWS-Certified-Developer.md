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

#### A security group acts as a virtual firewall for your EC2 instances to control incoming and outgoing traffic. Inbound rules control the incoming traffic to your instance, and outbound rules control the outgoing traffic from your instance. ... If you don't specify a security group, Amazon EC2 uses the default security group.

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
* Got SSH, cd ~/.aws, delete credential and config

Exam Tips
* Roles allow you to not use access key ID's and secret access keys
* Roles are preferred from a security perspective
* Roles are controlled by policies
* You can change a policy on a role and it will take immediate affect
* You can attach and detach roels to running EC2 instance without having to stop or terminate these instances.

#### Encrypt An EB Volume Attached to EC2

* Create new Volume - EC2 -> Elastic Block Store -> Volumes -> Create Volume
* Select Encryption
* Create Volume
* Attach this volume to EC2 instance
* go to SSH
* run command to list volumes
```
lsblk
```
* Check volume
```
file -s /dev/xvdf
```
* Create file system on volume
```
 mkfs -t ext4 /dev/xvdf
 ```
 * Mount file system
 ```
 cd /
 mkdir filesystem
 mount /dev/xvdf /filesystem
```
* Unmount
```
umount -d /dev/xvdf
```
* Detach volume from EC2 instance
* Craete snapshot
* Delete Volume
* Go to snapshots
* Select snapshot
* create volume from shapshot
* Attach it to EC2 instance
* Go to SSH, mount filesystem

Encrypt root volume
* create a snapshot
* Go to snapshot, select it and execute copy action
* Select Encryption and create
* Select encrypted root volume
* Select create image in Images/AMIs
* Launch the image

Exam Tips
* You can encrypt the root device volume(the volume the OS is installed on) using operating system level encryption
* You can encrypt the root device volume by fist taking a shapshot of that volume, and then creating a copy of thet snap with encryption. You can then make an AMI of this snap and deploy the encrypted root device volume.
* You can encrypt additional attached volumes using the console, CLI or API

#### RDS - Relational database service

Relational database type
* SQL Server
* Oracle
* MySQL
* PostgreSQL
* Aurora
* MariaDB

Non Relaional Database
* Database
  * Collection
  * Document
  * Key Value pairs

Data Warehouse
* Used for business intelligence. Tools like Cognos, Jaspersoft, SQL server Reporting services, Oracle Hyperion, SAP NetWeaver
* Used to pull in vary large and complex data sets, Uaually used by management to do queries on data(Such as current performance vstargets, etc.)

OLTP vs OLAP

* Online Transaction Processing (OLTP) differs from online Analytics Processing (OLAP) in terms of the types of queries you will run.


Elasticache - is a web service that makes it esay to deploy, operate, and scale an in-memoty cache in the cloud. The service inproves the performance of web applications by allowing you to retrieve information from fast, managed, in-menory caches, instead of relying entirelyu on slower disk-based database.
* Memcached
* Redis

AWS database types
* RDS - OLTP
  * SQL Server
  * OraMariaDBcle
  * MySQL
  * PostgreSQL
  * Aurora
  * MariaDB
* DynamoDB - NoSQL
* RedShift - OLAP
* Elasticache - In memory Caching
  * Memcached
  * Redis

#### RDS - Backups, Nulti-AZ & Read Relicas

Amazon RDS provides two different methods for backing up and restoring your DB Instance(s): automated backups and database snapshots (DB Snapshots).\

Turned on by default, the automated backup feature of Amazon RDS enables point-in-time recovery for your DB Instance. Amazon RDS will back up your database and transaction logs and store both for a user-specified retention period. This allows you to restore your DB Instance to any second during your retention period, up to the last 5 minutes. Your automatic backup retention period can be configured to up to 35 days.\

During the backup window, storage I/O may be suspended while your data is being backed up. This I/O suspension typically lasts a few minutes. This I/O suspension is avoided with Multi-AZ DB deployments, since the backup is taken from the standby.\

DB Snapshots are user-initiated backups of your DB Instance. These full database backups are stored by Amazon RDS until you explicitly delete them. You can copy DB snapshots of any size and move them between any of AWS’s public regions, or copy the same snapshot to multiple regions simultaneously. You can then create a new DB Instance from a DB Snapshot whenever you desire.\

Amazon RDS creates a storage volume snapshot of your DB instance, backing up the entire DB instance and not just individual databases. You can create a DB instance by restoring from this DB snapshot. When you restore the DB instance, you provide the name of the DB snapshot to restore from, and then provide a name for the new DB instance that is created from the restore. You can't restore from a DB snapshot to an existing DB instance; a new DB instance is created when you restore.\

You can encrypt your Amazon RDS DB instances and snapshots at rest by enabling the encryption option for your Amazon RDS DB instances. Data that is encrypted at rest includes the underlying storage for DB instances, its automated backups, read replicas, and snapshots.\

Amazon RDS encrypted DB instances use the industry standard AES-256 encryption algorithm to encrypt your data on the server that hosts your Amazon RDS DB instances. After your data is encrypted, Amazon RDS handles authentication of access and decryption of your data transparently with a minimal impact on performance. You don't need to modify your database client applications to use encryption.\

Once you have created an encrypted DB instance, you can't change the type of encryption key used by that DB instance. Therefore, be sure to determine your encryption key requirements before you create your encrypted DB instance.\

Copy a snapshot can enable encription on\

Multi-AZ - Amazon RDS provides high availability and failover support for DB instances using Multi-AZ deployments. Amazon RDS uses several different technologies to provide failover support. Multi-AZ deployments for MariaDB, MySQL, Oracle, and PostgreSQL DB instances use Amazon's failover technology. SQL Server DB instances use SQL Server Database Mirroring (DBM) or Always On Availability Groups (AGs).\

Amazon RDS Read Replicas provide enhanced performance and durability for RDS database (DB) instances. They make it easy to elastically scale out beyond the capacity constraints of a single DB instance for read-heavy database workloads. You can create one or more replicas of a given source DB Instance and serve high-volume application read traffic from multiple copies of your data, thereby increasing aggregate read throughput. Read replicas can also be promoted when needed to become standalone DB instances. Read replicas are available in Amazon RDS for MySQL, MariaDB, PostgreSQL, Oracle, and SQL Server as well as Amazon Aurora.\

You can reduce the load on your source DB instance by routing read queries from your applications to the read replica. Read replicas allow you to elastically scale out beyond the capacity constraints of a single DB instance for read-heavy database workloads. Because read replicas can be promoted to master status, they are useful as part of a sharding implementation.\

#### Elasticache - Fully managed in-memory data store, compatible with Redis or Memcached.

Amazon ElastiCache allows you to seamlessly set up, run, and scale popular open-Source compatible in-memory data stores in the cloud. Build data-intensive apps or boost the performance of your existing databases by retrieving data from high throughput and low latency in-memory data stores.\

Amazon ElastiCache works as an in-memory data store and cache to support the most demanding applications requiring sub-millisecond response times. By utilizing an end-to-end optimized stack running on customer dedicated nodes, Amazon ElastiCache provides secure, blazing fast performance.\

Elasticache Exam Tips

* Typically, you will be given a scenario where a particular database is under a lot of stress/load. You maybe asked which service you should user to alleviate this.
* Elasticace is a good choice if your database is particularly read-heavy and not prone to frequent changing.
* Redshift is a good answer if the reason your database is feeling stress in because management keep running OLAP transactions on it etc.
* Use Mencached if
  * Object caching is your primary goal
  * You want to keep things as simple as possible
  * You want to scale uyour cache horizontally(scale out)

* Use Redis if
  * You have advanced data types such as lists, hashes and sets.
  * You are doing data sorting and ranking (sucn as leader boards)
  * Data Persistence
  * Multi AZ
  * Put/Sub capabilities are needed

### S3

Amazon Simple Storage Service is storage for the Internet. It is designed to make web-scale computing easier for developers.\

Amazon S3 has a simple web services interface that you can use to store and retrieve any amount of data, at any time, from anywhere on the web. It gives any developer access to the same highly scalable, reliable, fast, inexpensive data storage infrastructure that Amazon uses to run its own global network of web sites. The service aims to maximize benefits of scale and to pass those benefits on to developers.\
* S3 is a safe place to store your files
* It is Object-based storage
* The data is spread across multiple devices and facilities

S3 - The Basics
* S3 is Object-based - i.e. allows you to upload files
* Files can be from 0 byte to 5 TB
* There is unlimited storage
* Files are stored in Buckers (similar to a folder)
* S3 is a universal namespace. That is , names must be unique globally.
* When you upload a file to S3, you will receive a HTTP 200 code if the upload was successful
* Built for 99.99% availablity for the S3 platform
* Amazon Guarantee 99.9% availability
* Amazon guarantees 99.99999999& durablity for S3 information. (remember 11*9s)
* Tiered stored available
* Lifecycle management
* Versioning
* Encryption
* Secure your data - access control lists and Bucker policies

Data Consistency Model for S3
* Read after write consistence for PUTS of new object
* Eventual Consistency for overwrite PUTS and DELETES (can take some time to propagate)

S3 is a Simple key-value store
* S3 is Object based. Objects consist of the following:
  * Key - this is simply the name of the objecdt
  * Value - this is simply the data, which is made up of a sequence of bytes.
  * Version ID
  * Metadata (data about data you are storing)
  * Subresources - bucket-specific configuration
    * Bucket Policies, access control lists.
    * Cross Origin Resource Sharing (CORS)
    * Transfer Acceleration

S3 - Storage Tiers/classes
* S3 standard - 99.99% availabilty
* S3 Intelligent-Tiering - is designed to optimize costs by automatically moving data to the most cost-effective access tier, without performance impact or operational overhead. It works by storing objects in two access tiers: one tier that is optimized for frequent access and another lower-cost tier that is optimized for infrequent access. 
* S3 - IA (Infrequently Accessed): For data that is accessed less frequently, bnut requires rapid access when needed. Lower fee than S3, but you are charged a retrieval fee.
* S3 - One Zone IA: Same as IA however data is stored in a single AZ, same durability but only 99.5% avaiability. Cost is 20% less than regular S3 - IA.
* Reduced redundancy over a given year(99.99% durability and 99.99% availability). Used for data that can be recreated if lost, e.g. thumbnials.
* Glacier - Very cheap, but used for archival only. Optimised for data that is infrequently accessed and it takes 3 - 5 hours to restore from Glacier.

[S3 tiers](https://miro.medium.com/max/875/1*PZryXkcXoVj99unK-XNqUA.png)

S3 Intelligent Tier
* Unknown or unpredictable access patterns
* 2 tiers - frequent and infrequent access
* Automatically moves your data to most cost-effective tier based on how frequently you access each object
* same availability and durability as S3 stardand
* Optimizes cost
* No fees for accessing your data but a s small monthly fee for monitoring/automation %0.0025 per 1000 object

S3 charges
* charged for:
  * Storage per GB
  * Requestrs(Get, Put, Copy, etc.1
  * Storage Management Pricing
    * Inventory, Analytics and object tags
  * Data management pricing
    * Data transferred out of S3
    * Transfer Acceleration
      * Use of CloudFront to optimize transfers

Exam Tips for S3 Basic
* Remember that S3 is Object-based: i.e. allows you to upload files. object-based storage only(for files)
* Not suitable to install an operating system or running a database on.
* Files can be from 0 bytes to 5 TB
* There is unlinited storage
* Files are stored in buckets.
* S3 is a universal namespace. That is names must by unique globally.
* Read after write consistency for PUTS of new objects
* Eventual onsistency for overwrite PUTS and DELETES(can take some time to propagate)
* S3 Storage Class/Tiers
* Remember the core fundamentals of an S3 object:
  * Key (name)
  * Value (data)
  * Version ID
  * Metadata
  * Subresource - bucket-specific configuration
    * Bucket Poliocies, Access control lists.
    * CORS
    * Transfer Acceleration
    * Successful uploads will generate a HTTP 200 status code - when you use the CLI API
    * [FAQ](https://aws.amazon.com/s3/faqs/)

#### S3 Security

Securing your buckets
* By Default, all newly created buckets are PRIVTE
* You can set up access control to youyr buckets using: 
  * Bucket Policies - Applied at a bucket level
  * Access Control Lists - Applied at an onject level
* S3 buckets can be configured to create access logs, which log all requests made to the S3 bucket. These logs can be written to another bucket.


#### S3 Policies

#### S3 Encryption

Encryption
* In Transit: SSL/TLS
* At Rest:
  * Server Side Encryption (AES-256)
    * S3 Managed keys - SSE-S3
    * AWS Key Management service, managed keys, SSE-KMS
    * Server side Encryption with customer provided keys - SSE-C
  * Client side encryption

Enforcing Encryption on S3 Buckets
* Every time a file is uploaded to S3, a PUT request is initiated.
* This is what a PUT request loos like
```
PUT /myfile HTTP/1.1
Host: muyBucket.s3.amazonaws.com
Date: Wed, 25 Apr 2020 09:50:00 GMT
AuthorizationL authorization string
Content-Type:text/plain
Content-Length: 23456
x-amz-meta-author: Gary
Expect: 100-continue
[23445 bytes of object data]
```
* If the file is to be encrypted at upload time, the x-amz-server-side-encryption parameter will be included in the request header
* Two options are current available:
  * x-amz-server-side-encryption:ASE256 (SSE-S3 - S3 managed key)
  * x-amz-server-side-encryption:ams:kms (SSE-KMS 0 KMS managed keys)
* When this parameter is inclkuded in the header of the PUT request, it tells S3 to encrypt the object at the time of upload, using the specified encryption method.
* You can enforce the use of server side encryption by using a Bucket Policy which denies any S# PUT request which doesn't include the x-amz-server-side-encryption parameter in the request header.

Exam Tips
* Encryption in-transit - SSL/TLS (HTTPS)
* Encryption at rest - server side / client side
* If you want to enforce the use of encryption of your files stored in S#, use an S3 budkct policy to deny all PUT requests that doesn't inlcude the x-amz-server-side-encryption parameter in HTTP header

##### Setup encryption on S# bucket
* Creatre a S3 bucket
* Select bucket, select permission/Bucket Policy
* Click Policy generator
  * Type of policy: S3 Bucket Policy
  * Effect: Deny
  * Principal: * (any request)
  * AWS Service: Amazon S3
  * Action: PUTObject
  * Amazon Resource Name (ARN): <the name of the bucket>
  * Add Condition
    * Condition: StringNotEquals
    * Key: s3:x-amz-server-side-encryption
    * Value: aws:kms
  * Click Add conition -> Add Statement -> Generate Policy
  * Copy to Bucket policy editor, add /* to Resource in Json
  * Save it

  Upload file
  * select file
  * Encryption: select AWS KMS master-key
  * key: aws/s3
  * upload

#### CORS Configuration
* Create a bucket
* Config it as public bucket
* Go into the bucket
* Goto properties / Static website hosting
* Select Use this bucket to host a website
* Upload index.html to the bucket (public read permission)

* Create another static website hosting S3 bucket
* Update load a html page to seconed bucket (public read permission)\
* Update index.html in first bucket to load html of second bucket
* Go into second bucket
* Go to permission / CORS comfiguration
* Copy below xml to editor and save it
```xml
<?xml version="1.0" encoding="UTF-8"?>
<CORSConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">
<CORSRule>
    <AllowedOrigin>[endpoint of first bucket]</AllowedOrigin>
    <AllowedMethod>GET</AllowedMethod>
    <MaxAgeSeconds>3000</MaxAgeSeconds>
    <AllowedHeader>Authorization</AllowedHeader>
</CORSRule>
</CORSConfiguration>
```

#### [CloudFront](https://aws.amazon.com/cloudfront/)

What is CDN? \

A content delivery network (CDN) is a system of distriuted servers (network) that deliver webpages and other web content to a user based on the geographic locations of the user, the origin of the webpage, and a content delivery server.\

CouldFront - Key Terminology

* Edge Location - This is the location where content is cached and can also be written, Seperate to an AWS Region/AZ.
* Origo - This is the origin of all the files that the CDN will distribute. Origins can be an S3 bucket, an EC2 Instance, an Elstic Load Balancer, or Route53.
* Distribution - This is the name given the CDN, which consists of a collection of Edge Locations.
* Web Distribution - Typically used for websites, http/https
* RTMP - (Abpobe Real Time Messaging Protocal) Used for media streaming / Flash multi-media content


What is CloudFront\

Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment. CloudFront is integrated with AWS – both physical locations that are directly connected to the AWS global infrastructure, as well as other AWS services. CloudFront works seamlessly with services including AWS Shield for DDoS mitigation, Amazon S3, Elastic Load Balancing or Amazon EC2 as origins for your applications, and Lambda@Edge to run custom code closer to customers’ users and to customize the user experience. Lastly, if you use AWS origins such as Amazon S3, Amazon EC2 or Elastic Load Balancing, you don’t pay for any data transferred between these services and CloudFront.\

CouldFront and S3 transfer acceleration\

Amazon S3 Transfer Acceleration enables fast, easy, and secure transfers of files over long distances between your client and an S3 bucket. Transfer Acceleration takes advantage of Amazon CloudFront’s globally distributed edge locations. As the data arrives at an edge location, data is routed to Amazon S3 over an optimized network path.

CloudFront - Exam Tips
* Edge Location
* Origin
* Distribution
  * Web Distribution
  * RTMP
* Edge location are not just READ only - you can WRITE to them,too(i.e. PUT an object on to them.)
* CloudFront Edge Lications are utilised by S3 transfer acceleration to reduct latency for s3 uploads.
* Objects are cached for the life of the TTL (Time to Live).
* You can clear cached objects, but you will be charged.

##### S3 Performance Optimization

S3 is designed to support very high request rates. However if your S3 buckets are routinely receiving PUT/LIST/DELETE or > 300 GET requests per second, then these are some best prictice guildlines that will help optimize S3 performance.

The Guidance is based on the type of workload your are running:
* GET-Intensice workloads - Use CloudFront content delivery service to get best performance. CloudFront will cache your most frequently accessed objects and will reduce latency for yout GET request.
* Mixed Request Type Workloads a mix of GET,PUT,DELETE,, the key names you use for your objects can impact performance for intensive workloads.
* S3 uses the key name to determine which partition an object will be stored in
* The use of sequential key names e.g. names perfixed with a time stamp or alphabetical sequence increases the likelihood of having multiple objects stored on the same partition.
* For heavy workloads this can cause I/O issue and contention
* By using a rendom prefix to key names, you can force S3 to distribute your keys across multiple partitions, distributing the I/O workload.

Exam Tips:
* GET-Intensice workloads - Use CloudFront
* Mixed Request Type Workloads - avoid sequential key names, instead add a random prefix like a hex hash to the key name (after July 2018 Amazon annonced a massive increase in S3 performace, logical and sequential naming patterns can now be used without any performance implication)

[Amazon S3 FAQs](https://aws.amazon.com/s3/faqs/)

### Serverless computing

#### Lambda

What is Lambda

AWS Lambda is a compute service that lets you run code without provisioning or managing servers. AWS Lambda executes your code only when needed and scales automatically, from a few requests per day to thousands per second. You pay only for the compute time you consume - there is no charge when your code is not running. With AWS Lambda, you can run code for virtually any type of application or backend service - all with zero administration. AWS Lambda runs your code on a high-availability compute infrastructure and performs all of the administration of the compute resources, including server and operating system maintenance, capacity provisioning and automatic scaling, code monitoring and logging. All you need to do is supply your code in one of the languages that AWS Lambda supports.

* Data Centers
* Hardware
* Assembly code/Protocols
* High level language
* Operating systems
* Application Layer/AWS APIs
* AWS Lambda

* You can use AWS Lambda to run your code in response to events, such as changes to data in an Amazon S3 bucket or an Amazon DynamoDB table; 
* To run your code in response to HTTP requests using Amazon API Gateway; 
* Invoke your code using API calls made using AWS SDKs.

 With these capabilities, you can use Lambda to easily build data processing triggers for AWS services like Amazon S3 and Amazon DynamoDB, process streaming data stored in Kinesis, or create your own back end that operates at AWS scale, performance, and security.

 Languages
 * Node.js
 * Python
 * Ruby
 * Java
 * GO
 * .Net

 Exam Tips
 * Lambda scales out (not up) automaticlly
 * Lambda functions are independent, 1 event = 1 function
 * Serverless
 * Know what services are serverless
 * Lambda functions can trigger other lambda fnctions, 1 event can = x functions if functions trigger oehter functgions
 * Atchitectures can get extremely complicated, AWS x-ray allows you to debug what is happening
 * Lambda can do things globally, you can use it to backup S3 buckets to other S3 buckets etc
 * Know your triggers

 #### API Gateway

 API - An API is an application programming interface

Type of APIs
* Restful APIs - Uses Json
* SOAP APIs - Use XML

Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as the "front door" for applications to access data, business logic, or functionality from your backend services. Using API Gateway, you can create RESTful APIs and WebSocket APIs that enable real-time two-way communication applications. API Gateway supports containerized and serverless workloads, as well as web applications.

What can API gateway do?
* Expost HTTPS endpoints to define a Restful API
* Serverless-ly connect to services like Lambda & DynamoDB
* Send each API endpoint to a different target
* Run efficiently with low cost
* Scale effortlessly
* Track and control usage by API key
* Throttle requests to prevent attacks
* Connect to CloudWatch to log all requests for monitoring
* Maintain multiple versions for your APIs

How do I configure API Gateway
* Define an API (Container)
* Define resources and nested resource (URL paths)
* For each resource
  * Select supported HTTP methods
  * Set Security
  * Choose target (EC2, Lambda, DynamoDB etc.)
  * Set request and response transformations
* Deploy API to a stage
  * Uses API gateway domain, by default
  * Can use custom domain
  * Supports AWS certificate manmager: free SSL/TSL certs.

API Caching - You can enable API caching in Amazon API Gateway to chache your endpoint's response.

Exam Tips
* Remember what API gateway is at a high level
* API Gateway has caching caoabilities to increase performance
* API gateway is low cost and scales automatically
* You can throttle API gateway to prevent attacks
* You can log results to CloudWatch
* If you are using javascript that uses multiple domains with API gateway, ensure that you have enabled CORS on API gateway
* CORS is enforced by the client

#### Version control with Lambda

* Each Lambda function version has a unique Amazon Resource Nane (ARN). After you publish a version, it is immutable(that is, it can't be changed).
* AWS Lambda maintains your latest function code in the $LATEST version.

A function version includes the following information:
* The function code and all associated dependencies.
* The Lambda runtime that invokes the function.
* All of the function settings, including the environment variables.
* A unique Amazon Resource Name (ARN) to identify the specific version of the function.

You can create one or more aliases for your Lambda function. A Lambda alias is like a pointer to a specific function version. Users can access the function version using the alias Amazon Resource Name (ARN).

Exam Tips
* Can have multiple versions of lambda functions
* Latest version will user $LATEST
* Qualified version will use $latest, unqualified will not have it
* Versions are immutable(Can not be changed)
* Can split traffic using aliases to different versions
  * can not split traffic with $latest, instead create an alias to latest

#### Step Functions

AWS Step Functions is a serverless function orchestrator that makes it easy to sequence AWS Lambda functions and multiple AWS services into business-critical applications. Through its visual interface, you can create and run a series of checkpointed and event-driven workflows that maintain the application state. The output of one step acts as an input to the next. Each step in your application executes in order, as defined by your business logic.

Orchestrating a series of individual serverless applications, managing retries, and debugging failures can be challenging. As your distributed applications become more complex, the complexity of managing them also grows. Step Functions automatically manages error handling, retry logic, and state. With its built-in operational controls, Step Functions manages sequencing, error handling, retry logic, and state, removing a significant operational burden from your team.

* Great way to visualize your serverless application.
* Step functions automatically triggers and tracks each step.
* Step Functions logs the state of each step so if something goes wrong you can track what went wrong and where.

#### X-Ray

AWS X-Ray is a service that collects data about requests that your application serves, and provides tools you can use to view, filter, and gain insights into that data to identify issues and opportunities for optimization. For any traced request to your application, you can see detailed information not only about the request and response, but also about calls that your application makes to downstream AWS resources, microservices, databases and HTTP web APIs.

<img src="https://docs.aws.amazon.com/xray/latest/devguide/images/architecture-dataflow.png"/>

The X-Ray SDK provides:
* Interceptors to add to your code to trace incoming HTTP requests
* Client handlers to instrument AWS SDK clients that your application uses to call other AWS services
* An HTTP client to use to instrument calls to other internal and external HTTP web services

The X-Ray integrates with the following AWS services:
* Elastic Load Balancing
* AWS Lambda
* Amazon API Gateway
* Amazon EC2
* AWS Elastic Beanstalk

X-Ray supported languages
* GO
* Java
* Node.js
* Python
* Ruby
* .Net

#### Advanced API Gateway

* You can use API Gateway Import API feature to import an API from am external definition file into API Gateway, the Import API feature supports Swagger V2.0 definition files.
* API Throttling, by defayult API Gateway limits the steady-state request rate to 10000requests per second, the maximum concurrent requests is 5000 requests across all APIs within an AWS account, if go over the maximum you will receive a 429 Too Many Request error
* SOAP Webservice Passthrough


### DynamoDB

[Amazon DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html) is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability. DynamoDB lets you offload the administrative burdens of operating and scaling a distributed database so that you don't have to worry about hardware provisioning, setup and configuration, replication, software patching, or cluster scaling. DynamoDB also offers encryption at rest, which eliminates the operational burden and complexity involved in protecting sensitive data. 

* Stored on SSD storage
* Spread across 3 Availability Zones in an AWS Region.
* Choice of 2 cionsisteny models
  * Eventual Consistent Reads (Default) - Consistency across all copies of data is usually reached within a second. Repeating a read after a short time should return the updated data. (Best read performance)
  * Strongly Consistent Reads - A strongly consistent read returns a result that reflects all writes thet received a successful respons prior to the read.

  Core Components of Amazon DynamoDB
  * Tables - Similar to other database systems, DynamoDB stores data in tables. A table is a collection of data. For example, see the example table called People that you could use to store personal contact information about friends, family, or anyone else of interest. You could also have a Cars table to store information about vehicles that people drive.
  * Items- Each table contains zero or more items. An item is a group of attributes that is uniquely identifiable among all of the other items. In a People table, each item represents a person. For a Cars table, each item represents one vehicle. Items in DynamoDB are similar in many ways to rows, records, or tuples in other database systems. In DynamoDB, there is no limit to the number of items you can store in a table.
  * Attributes - Each item is composed of one or more attributes. An attribute is a fundamental data element, something that does not need to be broken down any further. For example, an item in a People table contains attributes called PersonID, LastName, FirstName, and so on. For a Department table, an item might have attributes such as DepartmentID, Name, Manager, and so on. Attributes in DynamoDB are similar in many ways to fields or columns in other database systems.

  Primary Key
  * DynamoDB stores and retrieves data based on a primary key
  * 2 types of Primary key
  * Partition key - unique attribute (e.g. user ID)
    * Value of the partition key is input to an intermal hash function which determines the partition or physical lcoation on which the data is stored
    * If you are using the partition key as your primary key, then no two items can have the same Partition key.
  * Composite primary key (Partition key and sort key) - Referred to as a composite primary key, this type of key is composed of two attributes. The first attribute is the partition key, and the second attribute is the sort key.
    * In a table that has a partition key and a sort key, it's possible for two items to have the same partition key value. However, those two items must have different sort key values.
    * All items with the same Partition key are stored together, then sorted according to the Sort Key value.

Partition
* When you create a table, the initial status of the table is CREATING. During this phase, DynamoDB allocates sufficient partitions to the table so that it can handle your provisioned throughput requirements. You can begin writing and reading table data after the table status changes to ACTIVE.
* DynamoDB allocates additional partitions to a table in the following situations:
  * If you increase the table's provisioned throughput settings beyond what the existing partitions can support.
  * If an existing partition fills to capacity and more storage space is required.

DynamoDB access control
* Authentiation and access contriol is managed using AWS IAM.
* You can creae an IAM user within your AWS acount which has specific permissions to access and create DynamoDB tables
* You can create an IAM role which enables you to obtain temporary access keys which can be ised to access DynamoDB
* Ypu can also use a special IAM condition to restrict user access to only their onw records. (this can done by adding a condition to an IAM policy to allow access only items where the partition key calue matches the user ID)

DyanmoDB Exam tips
* Amazon DynamoDB is a low latency NoSQL database
* Consists of Tables, Items and Attributes
* Support bith document and key-value data models
* Support document formats are JSon, HTML, XML
* 2 Types of Primary key - Partition key and comnonation of Partition key + sort Key (composite key)
* 2 consistency model: strongly consistent / eventually consistent
* Access is controlled using IAM policies
* Fine grained access control usnig IAM condition parameter. dynamodb:LeadingKeys to allow to access the items where the partition key value mates there user ID

DynamoDB indexes - 2 types of index
* Local Secondary Index - An index that has the same partition key as the table, but a different sort key.
  * Can only be created when you are creating your table
  * You cannot add,remove or modify it later
  * But a different Sort Key
  * Gives you a different view of your data, organised according to an alternative Sort key
  * Any queries based on this Sort Key are much faster using the index than the main tale
* Global secondary Index - An index with a partition key and sort key that can be different from those on the table.
  * You can create when you create your table or add it later
  * Different Partition key as well as a Different Soft Key
  * So gives a completely different view of the data
  * Speeds up any queries relating to this alternative Partition and Softkey

#### Scan Vs Query API Call
Query
* A Query operation finds items in a table using only the the Primary Key attribute and a distinct value to search for.
* By default a Query returns a the atrributes for the items but you can the ProjectExpression parameter if you want the query to only return the specific attributes you want.
* Resutls are always sorted by Sort key
* Numeric order - by default in ascending order
* ASCII character code vaules
* You can reverse the order by setting the ScanIndexForward parameter to false
* By defult, Queries are Eventually Consistent
* You need to explicitly set the query to be Strongly Consistent

Scan
* A Scan operation examinmes every item in the table
* By default returns all data attributes
* Use the ProjectExpression parameter to refine the scan to only return the attributes you want

Query or Scan
* Query is more efficient than a Scan
* Scan dumps the entire table,then filters out the values to provide the desired result
* This adds an extra step of removing the data you don't want
* As the table grows, the can operation takes longer
* Scan operation on a large table can use up the provisioned throughput for a large table in just a single operation.
* Avoid using scan operations if you can: design tables in a way thet you can use the Query, Get or BatchGetItem APIs.

How to Improve performance
* You can reduct the impact of query or scan by setting a smaller page size which uses fewer read operations.
* Large number of smaller operations will allow other requests to succeed without throttling
* Avoide using scan operations if you can.

How to improve scan performance
* By Default, a scan operation processes data sequentially in return 1 MB increments before moving on to retrieve the next 1 MB of data. It can onluy scan one partition at a time.
* You can config DynamoDB to use Parallel scans instead by logically dividing a table or index into segments and scanning each segment in parallel.
* Best to avoid parallel scans if your table or index is already incurring heavy read / write activity from other applications.

#### DynamoDB provisioned throughput
* Provisioned throughput is measured in Capacity Units
* When you create a new provisioned table in Amazon DynamoDB, you must specify its provisioned throughput capacity. 
* Read Capacity Units - A read capacity unit represents one strongly consistent read per second, or two eventually consistent reads per second, for an item up to 4 KB in size.
* Write Capacity Units - A write capacity unit represents one write per second, for an item up to 1 KB in size.

#### DynamoDB on-demand capacity option
* Charges apply for Reading, Writing and Storing Data
* With on-demand, you don't need to specify your requirements
* DynamoDB instantly scales up and down based on the activity of your application.
* Great for unpredictab;e workloads
* Ypu want to pay for only what you use (pay per requesst).

#### DynamoDB Accellorator (DAX)

* Amazon DynamoDB Accelerator (DAX) is a fully managed, highly available, in-memory cache for Amazon DynamoDB that delivers up to a 10 times performance improvement—from milliseconds to microseconds—even at millions of requests per second.
* Improves response times for Eventually Consistent reads only
* Idealfor Read-heavy and bursty workloads

How does it work?
* DAX is a write-through caching service - this means data is written to the cache as well as the back and store at the same time.
* Allows you point your DynamoDB API calls at the DAX cluster
* If the item you are querying is in the cache(cache hit), DAX returns the result to the application
* If the item is not available(Cache miss) then DAX performs an Ecentually Consistemt GetItem operation against DynamoDB
* Retrieval of data from DAX reduces the read load on DynamoDB
* May be able to reduce provisioned Read capacity.

Not Suitable for
* Caters for Eventually Consistent reads only - so not suitable for applications that require strongly consistent reads
* Write intensive applications
* Application that do not perform many read operations
* Applications that do not require microsecond response times

#### Elasticache - Inmemory Cache
* Memcached
* Redis

Caching Strategies
* Lasy Loading - Loads the data into cache only when necessary
  * If data in cache, returns the data to application
  * If data not in cache or expired, returns null, application then fetches the data from database and writes it into cache so that is available next time.
  * TTL
* Write-Through - adds or updates data to the cache whenever data is written to the database

Exam tips
* In-memory cache sits between application and database
* 2 different caching strategies: Lazy loading and write through
* Laze laoding only chaches the data when it is requested
* Elasticache Node failuers not fatal just lots of cache misses
* Cache miss penaly: Initial request, query database, query database, writing to cache
* Avoid stale datta by implementing a TTL
* Write through strategy writes data into the cache whenever there is a change to the database
* Data is never stale
* Write penalty: Each write involes a write to the cache
* Elasticache node failure means that data is missing until added or updated in the database
* Wasted resources if most of the data is never used

#### DynamoDB Transactions

* ACID Transactions (Atomic, Consistent, Isolated, Durable)
* Read or write multiple items across multiple tables as an all or nothing operation
* Check for a pre-requisite condition before writing to a table

#### DynanmoDB TTL
* Time To Live attribute defines an expriy time for your data
* Expired items marked for deletion
* Great for removing irrelevant or old data
  * Session data
  * Event logs
  * Temporary data
* Reduces cost by automatically removing datga which is no longer relevant
* TTL expressed as epoch time
* Expiration is set for 2 hours after the session begin
* When the current time is greater than the TTL, the item will be expired and marked for deletion
* You can filter out expired items for your queries and scans

#### DynamoDB Streamss
* Time-ordered sequence of item level modificaions (insert, update, delete)
* Logs are encrypted at rest and store for 24 hours
* Accessed using a dedicated endpoint
* By default the primary key is recorded
* Before and after images can be captured.

Processing DynamoDBN streams
* Event are recorded in near real-time
* Applications can take actions based on contents
* Event source for Lambda
* Lamnbda polls the DynamoDB stream
* Executes Lambda code based on a DuynamoDB Streams event

#### Provisioned throughput Exceeded Exception
* Your request rate is too high for read / write capacity provisioned on your DynamoDB table
* SDK will automatically retries the requests until successful
* If you are not using the SDK you can:
  * Reduce request frequency
  * User Exponential Backoff

What is exponential backoff
* Many components in a network can generate errors due to being overladed
* In addition to simple retries all AWS SDKs use ExponentialBackoff
* Progressively longer waits between consecutive retries e.g. 05 ms, 100 ms, 200 ms....for improve flow control
* If after 1 minutes this doesn't work, your request size may be exceeding the throughput for you read/write capacity.

Exam tips
* If you see ProvisionedThroughputExceeded Error, this means the number of requests is too high
* Ezponential backoff inproves flow by retrying requests using progressively longer waits
* This is not just true for DynmoDB, Exponential Back0ff is a feature of every ASW SDK and applies to many services witn AWS, e.g. S3 buckets, cloudFromation, SES

[DynamoDB Cheatsheet](https://www.freecodecamp.org/news/ultimate-dynamodb-2020-cheatsheet/)


### KMS & Encryption on AWS

AWS Key Management Service (KMS) makes it easy for you to create and manage cryptographic keys and control their use across a wide range of AWS services and in your applications. AWS KMS is a secure and resilient service that uses hardware security modules that have been validated under FIPS 140-2, or are in the process of being validated, to protect your keys. AWS KMS is integrated with AWS CloudTrail to provide you with logs of all key usage to help meet your regulatory and compliance needs.

The customer Master Key:
* CMK
  * alias
  * creation date
  * description
  * key state
  * key material (either customer provided or AWS provided)
* Can Never be exported

#### Setup a customer master key
* Create alias and descryption
* Choose material option
  * Use KMS generated key material
  * Your own key material
* Define Key Administrative Permissions
  * IAM users/roles that can administer(but not use) the key through the KMS API
* Define Key usage permission
  * IAM users/roles that can use the key to encrypt and decrypt data

#### KMS API Calls
```
aws kms encrypt --key-id YOURKEYIDHERE --plaintext fileb://secret.txt --output text --query CiphertextBlob | base64 --decode > encryptedsecret.txt
aws kms decrypt --ciphertext-blob fileb://encryptedsecret.txt --output text --query Plaintext | base64 --decode > decryptedsecret.txt
aws kms re-encrypt --destination-key-id YOURKEYIDHERE --ciphertext-blob fileb://encryptedsecret.txt | base64 > newencryption.txt 
aws kms enable-key-rotation --key-id YOURKEYIDHERE
```

Exam Tips
* aws kms encrypt
* aws kms decrypt
* aws kms re-encrypt
* aws kms enable-key-rotation

#### KMS Envelope Encryption
The Customer Master Key:
* Customer master key userd to decrypt the data key(envelope key)
* envelope key is used to decrypt the data


### Other AWS services

#### SQS (Simple Queue Service)

Amazon Simple Queue Service (SQS) is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. SQS eliminates the complexity and overhead associated with managing and operating message oriented middleware, and empowers developers to focus on differentiating work. Using SQS, you can send, store, and receive messages between software components at any volume, without losing messages or requiring other services to be available. Get started with SQS in minutes using the AWS console, Command Line Interface or SDK of your choice, and three simple commands.

SQS offers two types of message queues. Standard queues offer maximum throughput, best-effort ordering, and at-least-once delivery. SQS FIFO queues are designed to guarantee that messages are processed exactly once, in the exact order that they are sent.

Benefits
* Eliminate administrative overhead
* Keep sensitive data secure
* Reliably deliver messages
* Scale elastically and cost-effectively

Queue types
* Standard Queues
  * Unlimited Throughput
  * At-Least-Once Delivery
  * Best-Effort Ordering
* FIFO Queues
  * High Throughput: By default, FIFO queues support up to 300 messages per second
  * Exactly-Once Processing
  * First-In-First-Out Delivery

Functionality
* Unlimited queues and messages
* Payload Size: Message payloads can contain up to 256KB of text in any format. 
* Batches: Send, receive, or delete messages in batches of up to 10 messages or 256KB. 
* Retain messages in queues for up to 14 days.
* Message locking: When a message is received, it becomes “locked” while being processed. This keeps other computers from processing the message simultaneously. If the message processing fails, the lock will expire and the message will be available again.

SQS Exam Tips
* SQS was the first service on the AWS platform.
* SQS is a distributed message queueing system
* Allow you to decouple the components for an application so that they are independent
* Pull-based, not push-based
* Message payloads can contain up to 256KB of text in any format. 
* Standard queue(defualt) - best-effort ordering, message delivered at least once
* FIFO Queues - order strictly preserved, message delivered once, no duplicated.
* Visibility timeout
  * Changes the visibility timeout of a specified message in a queue to a new value. The maximum allowed timeout value is 12 hours.
  * Default is 30 seconds - increase if your task takes > 30 seconds to complete
  * Max 12 hours
* Short Polling - returned immediately even if no message are in the queue
* Long Polling - polls the queue periodically and only returns a response when a message is the queue or the timeout is reached
* The maximum long polling wait time is 20 seconds.
* Maximum retention period for an SQS message is 14 days

#### SNS (Simple Notification Service)

Amazon Simple Notification Service (SNS) is a fully managed messaging service for both system-to-system and app-to-person (A2P) communication. It enables you to communicate between systems through publish/subscribe (pub/sub) patterns that enable messaging between decoupled microservice applications or to communicate directly to users via SMS, mobile push and email.

The system-to-system pub/sub functionality provides topics for high-throughput, push-based, many-to-many messaging. Using Amazon SNS topics, your publisher systems can fanout messages to a large number of subscriber systems or customer endpoints including Amazon SQS queues, AWS Lambda functions and HTTP/S, for parallel processing. The A2P messaging functionality enables you to send messages to users at scale using either a pub/sub pattern or direct-publish messages using a single API.

SNS Topics
* SNS allows you group multiple recipients using topics. A topic ia an "access point" for allowing recipients to dynamically subscribe for identical copies of the same notification.
* One topic can support deliveries to multiple endpoint types - for examle, you can group together iOS, Andriod ans SMS recipients. When you publis once to a topic, SBS delivers appropriatey formatted copies of your message to each subscriber.
* Tp prevent messages from being lost, all messages published to Amazon SNS are stored redundantly across nultiple availability zones.

SNS Exam Tips
* SNS is a scalable and highly available notification service which allow you to send push notifications from the cloud.
* Variety of message formats supported: SMS, email, SQS and HTTP endpoint
* Pub-sub model whereby users subscribe to topics
* It is a push mechanism rather than a pull mechanism.

#### SES

* SES(Simpole Email Service) is a scalable and highly available email service designed to help marketing teams and application developers send marketing, notifiation, and transactional emails to their customers using a pay as you go model
* Incoming mails can be delivered automaticlly to an S# bucket
* Incoming mails can be used to trigger Lambda function ans SNS notifications.\

#### Elastic Beanstalk
With Elastic Beanstalk, you can quickly deploy and manage applications in the AWS Cloud without having to learn about the infrastructure that runs those applications. Elastic Beanstalk reduces management complexity without restricting choice or control. You simply upload your application, and Elastic Beanstalk automatically handles the details of capacity provisioning, load balancing, scaling, and application health monitoring.

Elastic Beanstalk supports applications developed in Go, Java, .NET, Node.js, PHP, Python, and Ruby. When you deploy your application, Elastic Beanstalk builds the selected supported platform version and provisions one or more AWS resources, such as Amazon EC2 instances, to run your application.

You can interact with Elastic Beanstalk by using the Elastic Beanstalk console, the AWS Command Line Interface (AWS CLI), or eb, a high-level CLI designed specifically for Elastic Beanstalk.

* Fastest and simplest way to deploy your application in AWS
* Automatically scales your application up and down
* You can select the EC2 instance type that is optimal for your application
* Ypou can retain full administrative control over the resources powering your application, or have Elastic Beanstalk do it for you
* Managed platform updateds feature automatically applies updates your Operating System, Java, PHP, Node.js, etc.
* Monitor and manage application health via a dashboard
* Integrated with CloudWatch and X-Ray for performance data and metrics

EBS Deployment Policies

Elastic Beanstalk supports sereral options for processing deployments
* All at once
* Rolling
* Rolling with additional batch
* Immutable

All at once Deployment Updates
* Deploys the new version to all instances simultaneously
* All of your insances are out of service while the deployment takes place
* You will experience an outage while the deployment is talking place - not idea for mission-critical production systems.
* If the update failes, you need to roll back the chagnes byu re-deploying the original version to all your instances.

Rolling Deployment policy, rolling deployment updates:
* Deploys the new version in batches
* Each batch of instances is taken out of service while the deployment takes place
* Your environment capacity will be redeuced by the number of instances in a batch while the deployment takes place
* Not ideal for performance sensitive systems
* If the update failes, you need to perform an additional rolling update to roll back the changes.

Rolling with additional Batch Deployment
* Launches an additional batch of instances
* Deploysthe new version in batches
* Maintains full capacity during the deployment process
* If the update fails, you need to perform an additional rooling update tpo roll back the changes

Immutable deployment policy
* Deploys the new version to a fresh group of instances in their own new autoscaling group
* When the new instances pass their health checks, they are moved to your existing auto scaling group, and finally the old insatnces are terminated.
* Maintains full capacity during the deployment process
* The impace of a failed update is far less ad the rollback process requires only terminating the new auto scaling group
* Preferred option for mission critical production systems.

##### Configure Elastic Beanstalk
You can customize your Elastic Beanstalk environment using Elastic Beanstalk configuration files. There are files written in YAML or JSON format. They can have a filename of your choice but must have a .config extension and be saved inside a folder called .ebextensions

#### RDS & Elastic Beabstalk
Elastic Beabstalk supports two ways of integrationg an RDS database with your Beanstalk environment.

You can lanch the RDS instance from within the Elastic Beanstalk console, which means the RDS instance is created within your Elastic beanstalk environment - a good option for Dev and Test deployments.

However this may net be ideal for production envoronments because it means the lifecycle of your database is tied to the lifecycle of your application environment. If you terminate the environment, the database instance will be terminated too.

For production environments, the preferred option is to decouple the RDS instance from ypur EBS environment: i.e. launch it outside of Elastic Beanstalk, directly from the RSS section of the console. This option gives you a log more flexibility, allows you to connect multiple environment to the same dababase, provides a wider choice of database type, and allows you to tear down your application environment without affecting the datbase instance.

##### Access to RDS from Elastic Beanstalk
To allow the EC2 instance in your Elastic Beanstalk environment to connect to an outside database, there are two additional configuration steps required:
* An additional security group must be added to ypur enironment's Auto Scaling Group
* You'll need tp proide connect string configuration information to ypur application servers (endpoing, password use Elastic Beanstalk environment properties)

#### Systems Manager Parameter Store
* Confidential information such as passwords, database connection strings and license code can be stored in SSM parameter store
* You can store values as plain text or you can encrypt the data.
* Ypou can use this service with EC2, loudFormation, Lambda, EC2 Run Command etc.

#### Kinesis

Amazon Kinesis is a managed, scalable, cloud-based service that allows real-time processing of streaming large amount of data per second. It is designed for real-time applications and allows developers to take in any amount of data from several sources, scaling up and down that can be run on EC2 instances.

It is used to capture, store, and process data from large, distributed streams such as event logs and social media feeds. After processing the data, Kinesis distributes it to multiple consumers simultaneously.

Streaming data - is data that is generated continuouslyu by thousands of data source, which typically send in the data records simultaneously and in small sizes(order fo kilobytes).
  * Purchases from online stores
  * Stock prices
  * Game data
  * Social network data
  * Geospatial data (uber.com)
  * IOT sensor data

Core Kinesis Services
  * Kinesis Streams
  * Kinesis Firehose
  * Kinesis Analytics

Amazon Kinesis Data Streams (KDS) is a massively scalable and durable real-time data streaming service. KDS can continuously capture gigabytes of data per second from hundreds of thousands of sources such as website clickstreams, database event streams, financial transactions, social media feeds, IT logs, and location-tracking events. The data collected is available in milliseconds to enable real-time analytics use cases such as real-time dashboards, real-time anomaly detection, dynamic pricing, and more.
  * Kinesis Streams consissts of shards
    * 5 transactions per second for reads, up to a maximum total data read of 2 MB per second and up to 1000 records per second for writes, up to a maximun total data write rate of 1 MB per second(include partition keys)
    * The data capacity of ypur stream is a function of the numner of shards that you specify for the stream. The total capacity of the stream is the sum of the capacities of its shards.

Amazon Kinesis Data Firehose is the easiest way to reliably load streaming data into data lakes, data stores, and analytics services. It can capture, transform, and deliver streaming data to Amazon S3, Amazon Redshift, Amazon Elasticsearch Service, generic HTTP endpoints, and service providers like Datadog, New Relic, MongoDB, and Splunk. It is a fully managed service that automatically scales to match the throughput of your data and requires no ongoing administration. It can also batch, compress, transform, and encrypt your data streams before loading, minimizing the amount of storage used and increasing security.

Amazon Kinesis Data Analytics is the easiest way to transform and analyze streaming data in real time with Apache Flink. Apache Flink is an open source framework and engine for processing data streams. Amazon Kinesis Data Analytics reduces the complexity of building, managing, and integrating Apache Flink applications with other AWS services.

Amazon Kinesis Data Analytics takes care of everything required to run streaming applications continuously, and scales automatically to match the volume and throughput of your incoming data. With Amazon Kinesis Data Analytics, there are no servers to manage, no minimum fee or setup cost, and you only pay for the resources your streaming applications consume.

##### The Storage Gateway service is primarily used for attaching infrastructure located in a Data center to the AWS Storage infrastructure. The AWS documentation states that; "You can think of a file gateway as a file system mount on S3." Amazon Elastic File System (EFS) is a mountable file storage service for EC2, but has no connection to S3 which is an object storage service. Amazon Elastic Block Store (EBS) is a block level storage service for use with Amazon EC2 and again has no connection to S3.

### Developer Theory

#### CI/CD

#### What is CI/CD
* Software development best practice - Continuous Integration, Continuous Delivery / Development
* Make small change & automate everything (code integration, build, test and deployment)

Benifits of CI/CD
* Automation
* Small changes

AWS Continuous Delivery / Development workflow
* CodeCommit - source control service enabling teams to collaborate on code.
* CodeBuild - Compiles source, runs tests and products packages that are ready to deploy
* CodeDeployment - automates code deployment to any instance, including EC2, Lambda and on-premises
* CodePipeline - Manages the workflow, end-to-end solution, build, test and deploy your application every time there is a code change
[AWS white paper](https://d1.awsstatic.com/whitepapers/DevOps/practicing-continuous-integration-continuous-delivery-on-AWS.pdf)


#### CodeCommit

* Contralized Code Repository, based on GIT
* Enabled Collaboration
* Version control

#### CodeDeploy

Automated Deployment - EC2 instance, on-premises & Lambda

Approaches
* In-place - Application is stopped on each instance and the new release is installed. Also known as a rolling update, With an in-place deployment you will need to re-deploy the previous version to roll back, which can be time consumimg.
  * Lambda is not supported.
* Blue / Green - New instances are provisioned and the new releaase is installed on the new instances. Blue represents the active deployment, green is the new release.
  * Blue represents the current version of application
  * CodeDeploy provisions new instances.
  * The new Revision is deployed to the Green environment
  * The Greeen instances are registered with the Elastic Load Balancer.
  * Traffic is routed away from the old environment.
  * Blue environment is eventually terminated.
  * Just set the load balancer to redirect tjhe traffic back to the original environment to roll back.
  * Easy to switch between the old and new releases
  * Only works if you didn't already terminate your old environment

  #### CodeDeploy AppSpec File
  * Configuration File, defines the parameters to be used during a CodeDeploy depolyment
  * For EC2 and on-premises system, YAML only.
  * Lambda - YAML and JSON supported. File structure depends on whether your are deploying to Lambda or EC2.
  
  EC2 AppSpec file structure
  * Version - reserved for furure use, currentlyu the allowed value is 0.0
  * OS - Linux or windows
  * Files - Configuration files, packages, the location of any application files that need to be copied and wjhere they should be copied to.
  * Hooks - LifeCycle event hooks,scripts which need to run at set points in the deployment lifecycle. Hooks have a very specific run order.

  ##### Typical folder setup
  * appspec.yml
  * /scripts
  * /config
  * /source

##### CodeDeploy lifeCycle Event Hooks

* Phase 1 - De-register instances from a Load Balancer
* Phase 2 - The real nets & bolts of the application deployment
* Phase 3 - Re-register instances with the Load Balancer

Run order for an in-place deployment

* BeforeBlockTraffic - Run on instances before they are de-registered from a load balancer
* BlockTraffic - De-register instances from a Load Balancer
* AfterBlockTraffic - Run on instances after they are de-registered from a load balancer
* ApplicationStop - Gracefully stop the application
* DownloadBundle - CodeDeploy agent copies the application revision files to a temporary location
* BeforeInstall - Pre-installation scripts, e.g. backinng up the current version, decrypting files.
* Install - Copy application revision files to final location
* AfterInstall - Post-install scripts e.g. configuration, file permissions.
* ApplicationStart - start any services that were stopped during ApplicationStop.
* ValidateService - Run tests to validate the service
* BeforeAllowTraffic - Task you want to run on instances before they are registered with the load balancer
* AllowTraffic - Register instances with a load balancer
* AfterAllowTraffic - Tasks you want to run on instances after they are registered with a load balancer

#### CodePipeline

A Fully managed CI/CD service
* Orchestrates build, test & deployment
  * The pipeline is triggered every time there is a change to your code, like a conductor in an orchestra.
* Automated release process
  * Fast, consistent, fewer mistakes. Enables quick release of new features and bug fixes.
* CodePipeline integrates with
  * CodeCommit, CodeBuild, CodeDeploy, Github, Jenkins, Elastic Beanstalk, CloudFormation, Lanbda, Elastic container service.
  