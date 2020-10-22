
#### RDS

* A user has enabled the automated backup, but not specified the backup window. What will RDS do in this case?\
If the user does not specify a preferred backup window while enabling an automated backup, Amazon RDS assigns a default 30-minute backup window which is selected at random from an 8-hour block of time per region.\
LEARN MORE: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.BackingUpAndRestoringAmazonRDSInstances.html

* When the user makes any changes to the RDS security group the rule status will be authorizing for some time until the changes are applied to all instances that the group is connected with. Once the changes are propagated the rule status will change to authorized.\
LEARN MORE: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithSecurityGroups.html

* Amazon RDS provides two different methods for backing up and restoring the Amazon DB instances. A brief I/O freeze, typically lasting a few seconds, occurs during both automated backups and DB snapshot operations on Single-AZ DB instances.\
LEARN MORE: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.BackingUpAndRestoringAmazonRDSInstances.html

* RDS charges the user on a pay as you go basis. It charges the user based on the instance type, number of hours that the instance is running, data transfer, storage cost as well for the I/O requests. The monitoring is free of cost.\
LEARN MORE: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html

* Amazon RDS provides two different methods for backing up and restoring the Amazon DB instances: automated backups and DB snapshots. Automated backups automatically back up the DB instance during a specific, user-definable backup window, and keep the backups for a limited, user-specified period of time.\
LEARN MORE: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.BackingUpAndRestoringAmazonRDSInstances.html

* AWS RDS provides a managed DB platform, which offers features, such as automated backup, patch management, automated failure detection and recovery. The scaling is not automated and the user needs to plan it with a few clicks.\
LEARN MORE: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html

* When creating an RDS instance, the user needs to specify whether it is Multi AZ or not. If the user does not provide the value for the zone, the maintenance window or automated backup window, RDS will automatically select the value.\
LEARN MORE: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html

* The AWS RDS DB instance is an isolated DB environment provided by AWS in which the user can create more than 1 database. The maximum size of the instance should be between 5 GB and 3 TB. The size of each DB can be anything in this range.\
LEARN MORE: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html

#### IAM

* If a IAM user is trying to perform some action on an object belonging to another AWS user’s bucket, S3 will verify whether the owner of the IAM user has given sufficient permission to him. It also verifies the policy for the bucket as well as the policy defined by the object owner.\
LEARN MORE: http://docs.aws.amazon.com/AmazonS3/latest/dev/access-control-auth-workflow-object-operation.html

* The statement is the main element of the IAM policy and it is a must for a policy. Elements such as condition, version and ID are not required.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccessPolicyLanguage_ElementDescriptions.html

* The IAM group policy is always aggregated. In this case, if the user does not have permission for one group, but has permission for another group, he will have full access to EC2. Unless there is specific deny policy, the user will be able to access EC2.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/PoliciesOverview.html

* If an organization has created the IAM users, the users can access AWS services either with an IAM specific login/password or console. The organization can generate the IAM X.509 certificates to access AWS with CLI. The organization can also enable MFA for each IAM user, which allows an added security for each IAM user. If the organization has created the access key and secret key than the user cannot access the console using those keys. Access key and secret access key are useful for CLI or Webservices.

* The user can configure the AutoScaling group to automatically scale up and then scale down based on the specified conditions. To configure this, the user must setup policies which will get triggered by the CloudWatch alarms.\
LEARN MORE: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html

* It is a recommended approach to avoid using the access and secret access keys of the root account. Thus, do not download or delete it. Instead make the IAM user as powerful as the root account and use its credentials. The user cannot generate their own access and secret access keys as they are always generated by AWS.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/IAMBestPractices.html

* When an organization is using AWS IAM for creating various users and manage their access rights, the IAM user can not use the login URL http://aws.amazon.com/console to access AWS management console. The console login URL for the IAM user will have AWS account ID of that organization to identify the IAM user belongs to particular account. The AWS console login URL for the IAM user will be https:// <AWS_Account_ID>.signin.aws.amazon.com/console/. \
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html

* If a user wants the URL of the AWS IAM sign-in page to have a company name instead of the AWS account ID, he can create an alias for his AWS account ID. The alias should be unique.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html

* Identity federation enables users from an existing directory to access resources within your AWS account, making it easier to manage your users by maintaining their identities in a single place. In this case, the federated user is the only solution since AWS does not allow creating more than 5000 IAM users.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html

* If a user wants the URL of the AWS IAM sign-in page to have the company name instead of the AWS account ID, he can create an alias for his AWS account ID. The alias must be unique across all Amazon Webservices products and contain only digits, lowercase letters, and hyphens.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccountAlias.html

* It is a recommended rule that the root user should grant the least privileges to the IAM user or the group. The higher the privileges, the more problems it can create.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/IAMBestPractices.html

* Newly created IAM users have no password and no access key (access key ID and secret access key). If the user needs to administer your AWS resources using the AWS Management Console, you can create a password for the user. If the user needs to interact with AWS programmatically (using the command line interface (CLI), the AWS SDK, or service-specific APIs), you can create an access key for that user. The credentials you create for users are what they use to uniquely identify themselves to AWS.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_WorkingWithGroupsAndUsers.html

* A user can share an AMI with another user / peer using the command: ec2-modify-image-attribute <AMI-ID> -l -a <AWS Account ID>\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/sharingamis-explicit.html

* While launching an EC2 instance, the user can create a new key pair, select an existing key pair or proceed without a key pair. The user cannot upload a new key pair in the EC2 instance launch console.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/launching-instance.html

* Master keys are created and used only within AWS KMS to help ensure their security, enable your policies to be consistently enforced, and provide a centralized log of their use. Keys are only stored and used in the region in which they are created. They cannot be transferred to another region. For example; keys created in the EU-Central (Frankfurt) region are only stored and used within the EU-Central (Frankfurt) region.

#### AutoScaling

* The user can configure the AutoScaling group to automatically scale up and then scale down based on  the various specified CloudWatch monitoring conditions.  The user needs to provide the adjustment value and the adjustment type. A positive adjustment value increases the current capacity and a negative adjustment value decreases the current capacity. The user can express the change to the current size as an absolute number, an increment or as a percentage of the current group size.\
LEARN MORE: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html

* The user can achieve automated scaling by launching different EC2 instances and making them a part of an ELB.  Cloudwatch will be used to monitor the resources and based on the scaling need it will trigger policies. AutoScaling is then used to scale up or down the instances.\
LEARN MORE: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/WhatIsAutoScaling.html

* AutoScaling attempts to distribute instances evenly between the Availability Zones that are enabled for the user’s AutoScaling group. Auto Scaling does this by attempting to launch new instances in the Availability Zone with the fewest instances.\
LEARN MORE: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/AS_Concepts.html

* A user can see the number of AutoScaling resources currently allowed for the AWS account either by using the as-describe-account-limits command or by calling the DescribeAccountLimits action.\
LEARN MORE: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ts-as-capacity.html

* The Manual Scaling as part of Auto Scaling allows the user to change the capacity of Auto Scaling group. The user can add / remove EC2 instances on the fly. To execute manual scaling, the user should modify the desired capacity. AutoScaling will adjust instances as per the requirements. If the user is trying to CLI, he can use command
```
as-set-desired-capacity <Auto Scaling Group Name> --desired-capacity <New Capacity>
```

* The user can get notifications using SNS if he has configured the notifications while creating the Auto Scaling group.\
LEARN MORE: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/GettingStartedTutorial.html

* Before Auto Scaling selects an instance to terminate, it first identifies the Availability Zone that has more instances than the other Availability Zones used by the group. If all the Availability Zones have the same number of instances, it identifies a random Availability Zone.\
LEARN MORE: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/us-termination-policy.html

#### DynamoDB

* In DynamoDB, you can increase the throughput you have provisioned for your table using UpdateTable API or in the AWS Management Console. If you wish to exceed throughput rates of 10,000 writes/second or 10,000 reads/second, you must first contact AWS.\
LEARN MORE: http://aws.amazon.com/dynamodb/

* In DynamoDB, when you create a table with a hash-and-range key, you can optionally define one or more secondary indexes on that table. A secondary index lets you query the data in the table using an alternate key, in addition to queries against the primary key.\
LEARN MORE: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DataModel.html

* Amazon DynamoDB is ideal for database applications that require very low latency and predictable performance at any scale but don’t need complex querying capabilities like joins or transactions. Amazon DynamoDB is a fully-managed NoSQL database service that offers high performance, predictable throughput and low cost. It is easy to set up, operate, and scale.\
With Amazon DynamoDB, you can start small, specify the throughput and storage you need, and easily scale your capacity requirements on the fly. Amazon DynamoDB automatically partitions data over a number of servers to meet your request capacity. In addition, DynamoDB automatically replicates your data synchronously across multiple Availability Zones within an AWS Region to ensure high-availability and data durability.\
LEARN MORE: https://aws.amazon.com/running_databases/#dynamodb_anchor

Amazon DynamoDB supports increment or decrement atomic operations.\
LEARN MORE: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/APISummary.html

* The ListTables operation requires no parameters. However, you can specify optional parameters. For example, you can set the limit parameter if you want to use paging to limit the number of table names per page.\
LEARN MORE: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/LowLevelJavaCreateUpdateDeleteTable.html#LowLevelJavaCreate

* In DynamoDB, DescribeTable returns information about the table, including the current status of the table, when it was created, the primary key schema, and any indexes on the table.\
LEARN MORE: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SecondaryIndexes.html

* Amazon DynamoDB supports the following data types:
  * Scalar data types (like Number, String, and Binary)
  * Multi-valued types (like String Set, Number Set, and Binary Set).
LEARN MORE: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DataModel.html#DataModel.DataTypes

#### SQS

* In AWS Elastic Beanstalk, if the application returns any response other than 200, OK or there is no response within the configured InactivityTimeout period, SQS once again makes the message visible in the queue and available for another attempt at processing.\
LEARN MORE: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features-managing-env-tiers.html#worker-environ

* A message can be stored in the Simple Queue Service (SQS) from 1 minute up to a maximum of 14 days.\
LEARN MORE: http://aws.amazon.com/sqs/faqs/#How_long_can_I_keep_my_messages_in_Amazon_SQS_queues

* Amazon SQS is a distributed queuing system that is optimized for horizontal scalability, not for single-threaded sending or receiving speeds. A single client can send or receive Amazon SQS messages at a rate of about 5 to 50 messages per second. Higher receive performance can be achieved by requesting multiple messages (up to 10) in a single call. It may take several seconds before a message that has been to a queue is available to be received.\
LEARN MORE: http://media.amazonwebservices.com/AWS_Storage_Options.pdf

* Queue names are limited to 80 characters. Alphanumeric characters plus hyphens (-) and underscores (_) are allowed. Queue names must be unique within an AWS account. After you delete a queue, you can reuse the queue name.\
LEARN MORE: https://aws.amazon.com/sqs/faqs/

* The SQS message retention period is configurable and can be set anywhere from 1 minute to 2 weeks. The default is 4 days and once the message retention limit is reached your messages will be automatically deleted. The option for longer message retention provides greater flexibility to allow for longer intervals between message production and consumption.\
LEARN MORE: https://aws.amazon.com/sqs/faqs/

* AWS reserve the right to delete a queue if none of the following requests have been issued against the queue for more than 30 consecutive days:
  * SendMessage
  * ReceiveMessage
  * DeleteMessage
  * GetQueueAttributes
  * SetQueueAttributes
You should design your application with this in mind.\
LEARN MORE: https://aws.amazon.com/sqs/faqs/

#### SNS

* In Amazon SNS, to begin using Amazon SNS mobile push notifications, you first need an app for the mobile endpoints that uses one of the supported push notification services: APNS, GCM, or ADM. After you’ve registered and configured the app to use one of these services, you configure Amazon SNS to send push notifications to the mobile endpoints.\
LEARN MORE: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html

* In Amazon SNS, you have the ability to send notification messages directly to apps on mobile devices. Notification messages sent to a mobile endpoint can appear in the mobile app as message alerts, badge updates, or even sound alerts. Microsoft Windows Mobile Messaging (MWMM) doesn’t exist and is not supported by Amazon SNS.\
LEARN MORE: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html

* Amazon Simple Notification Service (Amazon SNS) is a fast, flexible, and fully managed push messaging service. Amazon SNS can deliver notifications by SMS text message or email to the Amazon Simple Queue Service (SQS) queues or to any HTTP endpoint.  The user can select one the following transports as part of the subscription requests: “HTTP”, “HTTPS”,”Email”, “Email-JSON”, “SQS”, “and SMS”.\
LEARN MORE: http://aws.amazon.com/sns/faqs/

* In Amazon SNS, It costs $1.00 to send one million mobile push notifications ($0.50 per million publishes, plus $0.50 per million mobile push notification deliveries).\
LEARN MORE: http://aws.amazon.com/sns/pricing/

#### S3

* If the user wants to temporarily stop the access to S3 the best solution is to disable the keys.  Deleting the user will result in a loss of all the credentials and the app will not be useful in the future. If the user stops the instance IAM users can still access S3. The change of the key does not help either as they are still active. The best possible solution is to disable the keys.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/ManagingCredentials.html

* S3 buckets can be in one of the three states: unversioned (the default), versioning-enabled or versioning-suspended. The bucket owner can configure the versioning state of a bucket. The versioning state applies to all (never some) of the objects in that bucket. The first time owner enables a bucket for versioning, objects in it are thereafter always versioned and given a unique version ID.\
LEARN MORE: http://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html

* AWS RRS provides the same functionality as AWS S3, but at a cheaper rate. It is ideally suited for non-mission, critical applications, such as files which can be reproduced.\
LEARN MORE: http://docs.aws.amazon.com/AmazonS3/latest/dev/UsingRRS.html

* S3 objects stored in the bucket before the user has set the versioning state have a version ID of null. When the user enables versioning, the objects in the bucket do not change and their ID remains null.\
LEARN MORE: http://docs.aws.amazon.com/AmazonS3/latest/dev/AddingObjectstoVersionSuspendedBuckets.html

* AWS S3 follows the eventual consistent model in the US Standard Region. Once the object is updated it may return the new value or the old value based on whether all the content is replicated across multiple servers until it becomes consistent (eventual).

* If the user is using the server-side encryption feature, Amazon S3 encrypts the object data before saving it on disks in its data centres and decrypts it when the user downloads the objects. Thus, the user is free from the tasks of managing encryption, encryption keys, and related tools.\
LEARN MORE: http://docs.aws.amazon.com/AmazonS3/latest/dev/UsingEncryption.html

* Amazon S3 offers access policy options broadly categorized as resource-based policies and user policies. Access policies, such as ACL and resource policy can be attached to the bucket.  With the object the user can only have ACL and not an object policy. The user can also attach access policies to the IAM users in the account. These are called user policies.\
LEARN MORE: http://docs.aws.amazon.com/AmazonS3/latest/dev/s3-access-control.html

#### Beanstalk

* AWS Elastic Beanstalk is designed to support a number of multiple running environments

* If a user is configuring HTTPS on the front end and TCP on the back end, ELB will not allow saving these listeners and will respond with the message.\
“Load Balancer protocol is an application layer protocol, but instance protocol is not. Both the Load Balancer protocol and the instance protocol should be at the same layer. Please fix.”\
LEARN MORE: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/elb-troubleshooting.html

* In AWS Elastic Beanstalk, one environment cannot support two different environment tiers because each requires its own set of resources; a worker environment tier and a web server environment tier each require an Auto Scaling group, but AWS Elastic Beanstalk supports only one Auto Scaling group per environment.\
LEARN MORE: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts.concepts.architecture.html

* AWS Elastic Beanstalk can use the Amazon Simple Notification Service (Amazon SNS) to notify you of important events affecting your application.\
LEARN MORE: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.managing.sns.html

* In AWS Elastic Beanstalk, applications can have many versions and each application version is unique. In a running environment, you can deploy any application version you already uploaded to the application or you can upload and immediately deploy a new application version. You might upload multiple application versions to test differences between one version of your web application and another.\
LEARN MORE: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts.components.html

* *hile AWS Elastic Beanstalk creates your AWS resources and launches your application, the environment will be in a Launching (gray) state. Status messages about launch events are displayed in the environment’s dashboard. If the environment health is gray, the environment is still in the process of being launched.\
LEARN MORE: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/GettingStarted.Walkthrough.html

* In AWS Elastic Beanstalk, you can update your deployed application, even while it is part of a running environment. For a Java application, you can also use the AWS Toolkit for Eclipse to update your deployed application.\
LEARN MORE: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/GettingStarted.Walkthrough.html

#### EC2 & EBS

* Regarding Amazon EC2, when launching an instance, the user needs to select the region the instance would be launched from. While launching, the user needs to plan for the insRtance type and the OS of the instance.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-instance_linux.html

* If an EBS volume stays in the detaching state, the user can force the detachment by clicking Force Detach. Forcing the detachment can lead to either data loss or a corrupted file system. The user should use this option only as a last resort to detach a volume from a failed instance or if he is detaching a volume with the intention of deleting it.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-detaching-volume.html

* In Amazon Web Services, when a user has configured an instance with Apache, the user needs to ensure that the ports in the security group are opened as configured in Apache config. E.g. If Apache is running on port 80, the user should open port 80 in the security group.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html

* When a user is trying to mount a blank EBS volume, it is required that the user first creates a file system within the volume.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-using-volumes.html

* An EBS volume provides persistent data storage. The user can attach a volume to any instance provided they are both in the same AZ. Even if they are in the same region but in a different AZ, it will not be able to attach the volume to that instance.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AmazonEBS.html

* If a user has launched an EBS backed instance, the user will be charged for the EBS volume even though the instance is in a stopped state. The instance will be charged for the EC2 hourly cost only when it is running.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-detaching-volume.html

* A user can always create a new EBS volume of a higher size than the original snapshot size. The user cannot create a volume of a lower size. When the new volume is created the size in the instance will be shown as the original size. The user needs to change the size of the device with resize2fs or other OS specific commands.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-expand-volume.html

* The EBS snapshots are a point in time backup of the EBS volume. It is an incremental snapshot, but is always specific to the region and never specific to a single AZ.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html

* Spread Placement Groups are recommended for applications that have a small number of critical instances which need to be kept separate from each other. Launching instances in a Spread Placement Group reduces the risk of simultaneous failures that might occur when instances share the same underlying hardware. Spread Placement Groups provide access to distinct hardware, and are therefore suitable for mixing instance types or launching instances over time. In this case, deploying the EC2 instances in a Spread Placement Group is the only correct option.

* To retrieve instance metadata or user data, you will need to use the following IP Address: http://169.254.169.254.

* Amazon EC2 RI Types - With RIs, you can choose the type that best fits your applications needs.
  * Standard RIs: These provide the most significant discount (up to 72% off On-Demand) and are best suited for steady-state usage.
  * Convertible RIs: These provide a discount (up to 54% off On-Demand) and the capability to change the attributes of the RI as long as the exchange results in the creation of Reserved Instances of equal or greater value. Like Standard RIs, Convertible RIs are best suited for steady-state usage.
  * Scheduled RIs: These are available to launch within the time windows you reserve. This option allows you to match your capacity reservation to a predictable recurring schedule that only requires a fraction of a day, a week, or a month.

#### SWF

* Amazon Simple Workflow (Amazon SWF) is a task coordination and state management service for cloud applications. With Amazon SWF, you can stop writing complex glue-code and state machinery and invest more in the business logic that makes your applications unique.\
LEARN MORE: http://aws.amazon.com/swf/

* In Amazon SWF, an activity worker is a program that receives activity tasks, performs them, and provides results back. Note that the task itself might actually be performed by a person, in which case the person would use the activity worker software for the receipt and disposition of the task. An example might be a statistical analyst, who receives sets of data, analyzes them, and then sends back the analysis.\
LEARN MORE: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dg-intro-to-swf.html

* In Amazon SWF, the maximum open activity tasks is up to 1,000 per workflow execution.\
LEARN MORE: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dg-limits.html

* In Amazon SWF, workflow execution time is up to maximum 1 year.\
LEARN MORE: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dg-limits.html

* In relation to Amazon Simple Workflow Service (Amazon SWF), an activity worker is a program that receives activity tasks, performs them, and provides results back. Which translates to a piece of software that implements tasks.\
LEARN MORE: http://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dg-develop-activity.html

#### VPC

* Every subnet in your VPC must be associated witfh exactly one Route Table. However, multiple subnets can be associated with the same Route Table.\
LEARN MORE: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Route_Tables.html

#### CloudFomation

* The template is a JSON-format or YAML file that describes all the AWS resources you need to deploy to run your application.\
LEARN MORE: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/concept-template.html

* Transforms is used to reference code located in S3 and also for specifying the use of the Serverless Application Model (SAM) for Lambda deployments.

* In AWS CloudFormation, the default value is overridden if you specify a value for the parameter as part of theaws cloudformation create-stack –parameters option. Parameter values you override at runtime are returned as part of the aws cloudformation describe-stacks command, unless you suppress that in the parameter declaration by including the NoEcho property with a value of true.\
LEARN MORE: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/concept-parameters.html

#### ELB

* The key to manage the sticky session is determining how long the load balancer should route the user’s request to the same application instance. If the application has its own session cookie, then the user can set the Elastic Load Balancing to create the session cookie to follow the duration specified by the application’s session cookie. If the user’s application does not have its own session cookie, then he can set the Elastic Load Balancing to create a session cookie by specifying his own stickiness duration.\
LEARN MORE: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/US_StickySessions.html

* It is possible to have one instance part of two separate ELBs, though both ELBs have different configurations. ELBs are never launched in specific zones.\
LEARN MORE: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/enable-disable-az.html

* An ELB performs a health check on its instances to ensure that it diverts traffic only to healthy instances. The ELB can perform a health check on HTTP, HTTPS, TCP and SSL protocols.\
LEARN MORE: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/Welcome.html

#### SAM 

* AWS SAM resource and property types
  * AWS::Serverless::Api
  * AWS::Serverless::Application
  * AWS::Serverless::Function
  * AWS::Serverless::HttpApi
  * AWS::Serverless::LayerVersion
  * AWS::Serverless::SimpleTable
  * AWS::Serverless::StateMachine