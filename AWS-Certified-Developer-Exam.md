
* A user has enabled the automated backup, but not specified the backup window. What will RDS do in this case?\
If the user does not specify a preferred backup window while enabling an automated backup, Amazon RDS assigns a default 30-minute backup window which is selected at random from an 8-hour block of time per region.\
LEARN MORE: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.BackingUpAndRestoringAmazonRDSInstances.html

* If a IAM user is trying to perform some action on an object belonging to another AWS user’s bucket, S3 will verify whether the owner of the IAM user has given sufficient permission to him. It also verifies the policy for the bucket as well as the policy defined by the object owner.\
LEARN MORE: http://docs.aws.amazon.com/AmazonS3/latest/dev/access-control-auth-workflow-object-operation.html

* The user can configure the AutoScaling group to automatically scale up and then scale down based on  the various specified CloudWatch monitoring conditions.  The user needs to provide the adjustment value and the adjustment type. A positive adjustment value increases the current capacity and a negative adjustment value decreases the current capacity. The user can express the change to the current size as an absolute number, an increment or as a percentage of the current group size.\
LEARN MORE: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html

* In DynamoDB, you can increase the throughput you have provisioned for your table using UpdateTable API or in the AWS Management Console. If you wish to exceed throughput rates of 10,000 writes/second or 10,000 reads/second, you must first contact AWS.\
LEARN MORE: http://aws.amazon.com/dynamodb/

* In Amazon SNS, to begin using Amazon SNS mobile push notifications, you first need an app for the mobile endpoints that uses one of the supported push notification services: APNS, GCM, or ADM. After you’ve registered and configured the app to use one of these services, you configure Amazon SNS to send push notifications to the mobile endpoints.\
LEARN MORE: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html

* In AWS Elastic Beanstalk, one environment cannot support two different environment tiers because each requires its own set of resources; a worker environment tier and a web server environment tier each require an Auto Scaling group, but AWS Elastic Beanstalk supports only one Auto Scaling group per environment.\
LEARN MORE: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts.concepts.architecture.html

* If the user wants to temporarily stop the access to S3 the best solution is to disable the keys.  Deleting the user will result in a loss of all the credentials and the app will not be useful in the future. If the user stops the instance IAM users can still access S3. The change of the key does not help either as they are still active. The best possible solution is to disable the keys.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/ManagingCredentials.html

* In Amazon SNS, you have the ability to send notification messages directly to apps on mobile devices. Notification messages sent to a mobile endpoint can appear in the mobile app as message alerts, badge updates, or even sound alerts. Microsoft Windows Mobile Messaging (MWMM) doesn’t exist and is not supported by Amazon SNS.\
LEARN MORE: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html

* S3 buckets can be in one of the three states: unversioned (the default), versioning-enabled or versioning-suspended. The bucket owner can configure the versioning state of a bucket. The versioning state applies to all (never some) of the objects in that bucket. The first time owner enables a bucket for versioning, objects in it are thereafter always versioned and given a unique version ID.\
LEARN MORE: http://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html

* The user can achieve automated scaling by launching different EC2 instances and making them a part of an ELB.  Cloudwatch will be used to monitor the resources and based on the scaling need it will trigger policies. AutoScaling is then used to scale up or down the instances.\
LEARN MORE: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/WhatIsAutoScaling.html

* AWS Elastic Beanstalk is designed to support a number of multiple running environments

* Amazon Simple Notification Service (Amazon SNS) is a fast, flexible, and fully managed push messaging service. Amazon SNS can deliver notifications by SMS text message or email to the Amazon Simple Queue Service (SQS) queues or to any HTTP endpoint.  The user can select one the following transports as part of the subscription requests: “HTTP”, “HTTPS”,”Email”, “Email-JSON”, “SQS”, “and SMS”.\
LEARN MORE: http://aws.amazon.com/sns/faqs/

* In DynamoDB, when you create a table with a hash-and-range key, you can optionally define one or more secondary indexes on that table. A secondary index lets you query the data in the table using an alternate key, in addition to queries against the primary key.\
LEARN MORE: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DataModel.html

* Regarding Amazon EC2, when launching an instance, the user needs to select the region the instance would be launched from. While launching, the user needs to plan for the insRtance type and the OS of the instance.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-instance_linux.html

* A user can see the number of AutoScaling resources currently allowed for the AWS account either by using the as-describe-account-limits command or by calling the DescribeAccountLimits action.\
LEARN MORE: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ts-as-capacity.html

* Amazon DynamoDB is ideal for database applications that require very low latency and predictable performance at any scale but don’t need complex querying capabilities like joins or transactions. Amazon DynamoDB is a fully-managed NoSQL database service that offers high performance, predictable throughput and low cost. It is easy to set up, operate, and scale.\
With Amazon DynamoDB, you can start small, specify the throughput and storage you need, and easily scale your capacity requirements on the fly. Amazon DynamoDB automatically partitions data over a number of servers to meet your request capacity. In addition, DynamoDB automatically replicates your data synchronously across multiple Availability Zones within an AWS Region to ensure high-availability and data durability.\
LEARN MORE: https://aws.amazon.com/running_databases/#dynamodb_anchor

* The statement is the main element of the IAM policy and it is a must for a policy. Elements such as condition, version and ID are not required.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/AccessPolicyLanguage_ElementDescriptions.html

* If an EBS volume stays in the detaching state, the user can force the detachment by clicking Force Detach. Forcing the detachment can lead to either data loss or a corrupted file system. The user should use this option only as a last resort to detach a volume from a failed instance or if he is detaching a volume with the intention of deleting it.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-detaching-volume.html

* In Amazon Web Services, when a user has configured an instance with Apache, the user needs to ensure that the ports in the security group are opened as configured in Apache config. E.g. If Apache is running on port 80, the user should open port 80 in the security group.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html

* AWS RRS provides the same functionality as AWS S3, but at a cheaper rate. It is ideally suited for non-mission, critical applications, such as files which can be reproduced.\
LEARN MORE: http://docs.aws.amazon.com/AmazonS3/latest/dev/UsingRRS.html

* The IAM group policy is always aggregated. In this case, if the user does not have permission for one group, but has permission for another group, he will have full access to EC2. Unless there is specific deny policy, the user will be able to access EC2.\
LEARN MORE: http://docs.aws.amazon.com/IAM/latest/UserGuide/PoliciesOverview.html

* S3 objects stored in the bucket before the user has set the versioning state have a version ID of null. When the user enables versioning, the objects in the bucket do not change and their ID remains null.\
LEARN MORE: http://docs.aws.amazon.com/AmazonS3/latest/dev/AddingObjectstoVersionSuspendedBuckets.html

* In Amazon SNS, to send messages to a queue through a topic, you must subscribe the queue to the Amazon SNS topic. You specify the queue by its ARN.\
LEARN MORE: http://docs.aws.amazon.com/sns/latest/dg/SendMessageToSQS.html

* When a user is trying to mount a blank EBS volume, it is required that the user first creates a file system within the volume.\
LEARN MORE: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-using-volumes.html

* Amazon Simple Workflow (Amazon SWF) is a task coordination and state management service for cloud applications. With Amazon SWF, you can stop writing complex glue-code and state machinery and invest more in the business logic that makes your applications unique.\
LEARN MORE: http://aws.amazon.com/swf/

* In AWS Elastic Beanstalk, if the application returns any response other than 200, OK or there is no response within the configured InactivityTimeout period, SQS once again makes the message visible in the queue and available for another attempt at processing.\
LEARN MORE: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features-managing-env-tiers.html#worker-environ

* A message can be stored in the Simple Queue Service (SQS) from 1 minute up to a maximum of 14 days.\
LEARN MORE: http://aws.amazon.com/sqs/faqs/#How_long_can_I_keep_my_messages_in_Amazon_SQS_queues

* Amazon SQS is a distributed queuing system that is optimized for horizontal scalability, not for single-threaded sending or receiving speeds. A single client can send or receive Amazon SQS messages at a rate of about 5 to 50 messages per second. Higher receive performance can be achieved by requesting multiple messages (up to 10) in a single call. It may take several seconds before a message that has been to a queue is available to be received.\
LEARN MORE: http://media.amazonwebservices.com/AWS_Storage_Options.pdf