A deployment package uses the AWS CLI to copy files into any S3 bucket in the account, using access keys stored in environment variables. The package is running on EC2 instances, and the instances have been modified to run with an assumed IAM role and a more restrictive policy that allows access to only one bucket. After the change, the Developer logs into the host and still has the ability to write into all of the S3 buckets in that account.\
What is the MOST likely cause of this situation?
  1. An IAM inline policy is being used on the IAM role
  2. An IAM managed policy is being used on the IAM role
  3. The AWS CLI is corrupt and needs to be reinstalled
  4. (X) The AWS credential provider looks for instance profile credentials last

\
An application has hundreds of users. Each user may use multiple devices to access the application. The Developer wants to assign unique identifiers to these users regardless of the device they use.\
Which of the following methods should be used to obtain unique identifiers?
1. Create a user table in Amazon DynamoDB as key-value pairs of users and their devices. Use these keys as unique identifiers.
2. Use IAM-generated access key IDs for the users as the unique identifier, but do not store secret keys.
3. (X) Implement developer-authenticated identities by using Amazon Cognito, and get credentials for these identities.
4. Assign IAM users and roles to the users. Use the unique IAM resource ID as the unique identifier.

\
A Developer is creating a Lambda function and will be using external libraries that are not included in the standard Lambda libraries.
What action would minimize the Lambda compute time consumed?
1. Install the dependencies and external libraries at the beginning of the Lambda function.
2. Create a Lambda deployment package that includes the external libraries.
3. Copy the external libraries to Amazon S3, and reference the external libraries to the S3 location.
4. (X) Install the external libraries in Lambda to be available to all Lambda functions.

\
A company is migrating its on-premises database to Amazon RDS for MySQL. The company has read-heavy workloads, and wants to make sure it re-factors its code to achieve optimum read performance for its queries.
How can this objective be met?
1. Add database retries to effectively use RDS with vertical scaling
2. Use RDS with multi-AZ deployment
3. (X) Add a connection string to use an RDS read replica for read queries
4. Add a connection string to use a read replica on an EC2 instance.

\
A Developer is testing a Docker-based application that uses the AWS SDK to interact with Amazon DynamoDB. In the local development environment, the application has used IAM access keys. The application is now ready for deployment onto an ECS cluster.
How should the application authenticate with AWS services in production?
1. (X) Configure an ECS task IAM role for the application to use
2. Refactor the application to call AWS STS AssumeRole based on an instance role
3. Configure AWS access key/secret access key environment variables with new credentials
4. Configure the credentials file with a new access key/secret access key

\
The Lambda function below is being called through an API using Amazon API Gateway. The average execution time for the Lambda function is about 1 second.
The pseudocode for the Lambda function is as shown in the exhibit.
<img src="https://www.examtopics.com/assets/media/exam-media/02738/0002100001.png">
What two actions can be taken to improve the performance of this Lambda function without increasing the cost of the solution? (Select two.)
1. (X) Package only the modules the Lambda function requires
2. Use Amazon DynamoDB instead of Amazon RDS
3. (X) sMove the initialization of the variable Amazon RDS connection outside of the handler function
4. Implement custom database connection pooling with the Lambda function
5. Implement local caching of Amazon RDS data so Lambda can re-use the cache

\
A Developer has setup an Amazon Kinesis Stream with 4 shards to ingest a maximum of 2500 records per second. A Lambda function has been configured to process these records.
In which order will these records be processed?
1. Lambda will receive each record in the reverse order it was placed into the stream following a LIFO (last-in, first-out) method
2. Lambda will receive each record in the exact order it was placed into the stream following a FIFO (first-in, first-out) method.
3. (X) Lambda will receive each record in the exact order it was placed into the shard following a FIFO (first-in, first-out) method. There is no guarantee of order across shards.
4. The Developer can select FIFO, (first-in, first-out), LIFO (last-in, last-out), random, or request specific record using the getRecords API.

\
For a deployment using AWS CodeDeploy, what is the run order of the hooks for in-place deployments?
1. Before Install -> Application Stop -> Application Start -> After Install
2. (X) Application Stop -> Before Install -> After Install -> Application Start
3. Before Install -> Application Stop -> Validate Service -> Application Start
4. Application Stop -> Before Install -> Validate Service -> Application Start

\
A Developer is developing an application that manages financial transactions. To improve security, multi-factor authentication (MFA) will be required as part of the login protocol.
What services can the Developer use to meet these requirements?
1. Amazon DynamoDB to store MFA session data, and Amazon SNS to send MFA codes
2. (X) Amazon Cognito with MFA
3. AWS Directory Service
4. AWS IAM with MFA enabled

\
A supplier is writing a new RESTful API for customers to query the status of orders. The customers requested the following API endpoint. http://www.supplierdomain.com/status/customerID
Which of the following application designs meet the requirements? (Select two.)
1. Amazon SQS; Amazon SNS
2. (X) Elastic Load Balancing; Amazon EC2
3. Amazon ElastiCache; Amazon Elacticsearch Service
4. (X) Amazon API Gateway; AWS Lambda
5. Amazon S3; Amazon CloudFront

\
A legacy service has an XML-based SOAP interface. The Developer wants to expose the functionality of the service to external clients with the Amazon API
Gateway. Which technique will accomplish this?
1. (X) Create a RESTful API with the API Gateway; transform the incoming JSON into a valid XML message for the SOAP interface using mapping templates.
2. Create a RESTful API with the API Gateway; pass the incoming JSON to the SOAP interface through an Application Load Balancer.
3. Create a RESTful API with the API Gateway; pass the incoming XML to the SOAP interface through an Application Load Balancer.
4. Create a RESTful API with the API Gateway; transform the incoming XML into a valid message for the SOAP interface using mapping templates.

\
A company is using AWS CodeBuild to compile a website from source code stored in AWS CodeCommit. A recent change to the source code has resulted in the
CodeBuild project being unable to successfully compile the website.
How should the Developer identify the cause of the failures?
1. Modify the buildspec.yml file to include steps to send the output of build commands to Amazon CloudWatch.
2. Use a custom Docker image that includes the AWS X-Ray agent in the AWS CodeBuild project configuration.
3. (X) Check the build logs of the failed phase in the last build attempt in the AWS CodeBuild project build history.
4. Manually re-run the build process on a local machine so that the output can be visualized.

\
A Developer executed a AWS CLI command and received the error shown below:
<img src="https://www.examtopics.com/assets/media/exam-media/02738/0002800001.png">
What action should the Developer perform to make this error human-readable?
1. Make a call to AWS KMS to decode the message.
2. (X) Use the AWS STS decode-authorization-message API to decode the message.
3. Use an open source decoding library to decode the message.
4. Use the AWS IAM decode-authorization-message API to decode this message.

\
An application stops working with the following error: The specified bucket does not exist. Where is the BEST place to start the root cause analysis?
1. Check the Elastic Load Balancer logs for DeleteBucket requests.
2. Check the application logs in Amazon CloudWatch Logs for Amazon S3 DeleteBucket errors.
3. Check AWS X-Ray for Amazon S3 DeleteBucket alarms.
4. (X) Check AWS CloudTrail for a DeleteBucket event.

\
A Developer must repeatedly and consistently deploy a serverless RESTful API on AWS.\
Which techniques will work? (Choose two.)
1. Define a Swagger file. Use AWS Elastic Beanstalk to deploy the Swagger file.
2. Define a Swagger file. Use AWS CodeDeploy to deploy the Swagger file.
3. (X) Deploy a SAM template with an inline Swagger definition.
4. (X) Define a Swagger file. Deploy a SAM template that references the Swagger file.
5. Define an inline Swagger definition in a Lambda function. Invoke the Lambda function.

\
A set of APIs are exposed to customers using the Amazon API Gateway. These APIs have caching enabled on the API Gateway. Customers have asked for an option to invalidate this cache for each of the APIs.
What action can be taken to allow API customers to invalidate the API Cache?
1. Ask customers to use AWS credentials to call the InvalidateCache API.
2. Ask customers to invoke an AWS API endpoint which invalidates the cache.
3. (X) Ask customers to pass an HTTP header called Cache-Control:max-age=0.
4. Ask customers to add a query string parameter called "INVALIDATE_CACHE" when making an API call.

\
A company is developing a new online game that will run on top of Amazon ECS. Four distinct Amazon ECS services will be part of the architecture, each requiring specific permissions to various AWS services. The company wants to optimize the use of the underlying Amazon EC2 instances by bin packing the containers based on memory reservation.
Which configuration would allow the Development team to meet these requirements MOST securely?
1. Create a new Identity and Access Management (IAM) instance profile containing the required permissions for the various ECS services, then associate that instance role with the underlying EC2 instances.
2. Create four distinct IAM roles, each containing the required permissions for the associated ECS service, then configure each ECS service to reference the associated IAM role.
3. Create four distinct IAM roles, each containing the required permissions for the associated ECS service, then, create an IAM group and configure the ECS cluster to reference that group.
4. (X) Create four distinct IAM roles, each containing the required permissions for the associated ECS service, then configure each ECS task definition to referenÑe the associated IAM role.

\
An application is real-time processing millions of events that are received through an API.
What service could be used to allow multiple consumers to process the data concurrently and MOST cost-effectively?
1. Amazon SNS with fanout to an SQS queue for each application
2. Amazon SNS with fanout to an SQS FIFO (first-in, firtst-out) queue for each application
3. Amazon Kinesis Firehouse
4. (X) Amazon Kinesis Streams

\
A Developer must trigger an AWS Lambda function based on the item lifecycle activity in an Amazon DynamoDB table.\
How can the Developer create the solution?
1. Enable a DynamoDB stream that publishes an Amazon SNS message. Trigger the Lambda function synchronously from the SNS message.
2. Enable a DynamoDB stream that publishes an SNS message. Trigger the Lambda function asynchronously from the SNS message.
3. (X) Enable a DynamoDB stream, and trigger the Lambda function synchronously from the stream.
4. Enable a DynamoDB stream, and trigger the Lambda function asynchronously from the stream.

\
A social media company is using Amazon Cognito in order to synchronize profiles across different mobile devices, to enable end users to have a seamless experience.
Which of the following configurations can be used to silently notify users whenever an update is available on all other devices?
1. Modify the user pool to include all the devices which keep them in sync.
2. Use the SyncCallback interface to receive notifications on the application.
3. Use an Amazon Cognito stream to analyze the data and push the notifications.
4. (X) Use the push synchronization feature with the appropriate IAM role.

\
A website's page load times are gradually increasing as more users access the system at the same time. Analysis indicates that a user profile is being loaded from a database in all the web pages being visited by each user and this is increasing the database load and the page load latency. To address this issue the
Developer decides to cache the user profile data.\
Which caching strategy will address this situation MOST efficiently?
1. Create a new Amazon EC2 Instance and run a NoSQL database on it. Cache the profile data within this database using the write-through caching strategy.
2. (X) Create an Amazon ElastiCache cluster to cache the user profile data. Use a cache-aside caching strategy.
3. Use a dedicated Amazon RDS instance for caching profile data. Use a write-through caching strategy.
4. Create an ElastiCache cluster to cache the user profile data. Use a write-through caching strategy.

\
A development team is using AWS Elastic Beanstalk to deploy a two-tier application that consists of a load-balanced web tier and an Amazon RDS database tier in production. The team would like to separate the RDS instance from the Elastic Beanstalk.
How can this be accomplished?
1. Use the Elastic Beanstalk CLI to disassociate the database.
2. Use the AWS CLI to disassociate the database.
3. Change the deployment policy to disassociate the database.
4. (X) Recreate a new Elastic Beanstalk environment without Amazon RDS.

\
The development team is working on an API that will be served from Amazon API gateway. The API will be served from three environments: development, test, and production. The API Gateway is configured to use 237 GB of cache in all three stages.
Which is the MOST cost-efficient deployment strategy?
1. Create a single API Gateway with all three stages.
2. Create three API Gateways, one for each stage in a single AWS account.
3. Create an API Gateway in three separate AWS accounts.
4. (X) Enable the cache for development and test environments only when needed.

\
An application running on an Amazon Linux EC2 instance needs to manage the AWS infrastructure.
How can the EC2 instance be configured to make AWS API calls securely?
1. Sign the AWS CLI command using the signature version 4 process.
2. Run the aws configure AWS CLI command and specify the access key id and secret access key.
3. (X) Specify a role for the EC2 instance with the necessary privileges.
4. Pass the access key id and secret access key as parameters for each AWS CLI command.

\
A Developer is creating a Lambda function that will generate and export a file. The function requires 100 MB of temporary storage for temporary files while executing. These files will not be needed after the function is complete.
How can the Developer MOST efficiently handle the temporary files?
1. Store the files in EBS and delete the files at the end of the Lambda function.
2. Copy the files to EFS and delete the files at the end of the Lambda function.
3. (X) Store the files in the /tmp directory and delete the files at the end of the Lambda function.
4. Copy the files to an S3 bucket with a lifecycle policy to delete the files.

\
AWS CodeBuild builds code for an application, creates the Docker image, pushes the image to Amazon Elastic Container Registry (Amazon ECR), and tags the image with a unique identifier.
If the Developers already have AWS CLI configured on their workstations, how can the Docker images be pulled to the workstations?
1. Run the following: docker pull REPOSITORY URI : TAG
2. (X) Run the output of the following: aws ecr get-login and then run: docker pull REPOSITORY URI : TAG
3. Run the following: aws ecr get-login and then run: docker pull REPOSITORY URI : TAG
4. Run the output of the following: aws ecr get-download-url-for-layer and then run: docker pull REPOSITORY URI : TAG

\
A Developer wants to encrypt new objects that are being uploaded to an Amazon S3 bucket by an application. There must be an audit trail of who has used the key during this process. There should be no change to the performance of the application.
Which type of encryption meets these requirements?
1. Server-side encryption using S3-managed keys
2. (X) Server-side encryption with AWS KMS-managed keys
3. Client-side encryption with a client-side symmetric master key
4. Client-side encryption with AWS KMS-managed keys

\
While developing an application that runs on Amazon EC2 in an Amazon VPC, a Developer identifies the need for centralized storage of application-level logs.
Which AWS service can be used to securely store these logs?
1. Amazon EC2 VPC Flow Logs
2. (X) Amazon CloudWatch Logs
3. Amazon CloudSearch
4. AWS CloudTrail

\
An application uses Amazon Kinesis Data Streams to ingest and process large streams of data records in real time. Amazon EC2 instances consume and process the data from the shards of the Kinesis data stream by using Amazon Kinesis Client Library (KCL). The application handles the failure scenarios and does not require standby workers. The application reports that a specific shard is receiving more data than expected. To adapt to the changes in the rate of data flow, the "hot" shard is resharded.
Assuming that the initial number of shards in the Kinesis data stream is 4, and after resharding the number of shards increased to 6, what is the maximum number of EC2 instances that can be deployed to process data from all the shards?
1. 12
2. (X) 6
3. 4
4. 1

Typically, when you use the KCL, you should ensure that the number of instances does not exceed the number of shards (except for failure standby purposes). Each shard is processed by exactly one KCL worker and has exactly one corresponding record processor, so you never need multiple instances to process one shard. However, one worker can process any number of shards, so it's fine if the number of shards exceeds the number of instances.
https://docs.aws.amazon.com/streams/latest/dev/kinesis-record-processor-scaling.html

\
A Development team is working on a case management solution that allows medical claims to be processed and reviewed. Users log in to provide information related to their medical and financial situations.
As part of the application, sensitive documents such as medical records, medical imaging, bank statements, and receipts are uploaded to Amazon S3. All documents must be securely transmitted and stored. All access to the documents must be recorded for auditing.
What is the MOST secure approach?
1. Use S3 default encryption using Advanced Encryption Standard-256 (AES-256) on the destination bucket.
2. Use Amazon Cognito for authorization and authentication to ensure the security of the application and documents.
3. Use AWS Lambda to encrypt and decrypt objects as they are placed into the S3 bucket.
4. (X) Use client-side encryption/decryption with Amazon S3 and AWS KMS.

Not only will KMS provide the Auditing you need, but with client-side encryption although a little more work on client side, this method provides the needed encryption at rest since the data has to be encrypted before being transmitted to s3 for storage, and it REQUIRES (and only allows) HTTPS for the transmission across to the bucket

\
A company has an internet-facing application that uses Web Identity Federation to obtain a temporary credential from AWS Security Token Service (AWS STS).
The app then uses the token to access AWS services.
Review the following response:
<img src="https://www.examtopics.com/assets/media/exam-media/02738/0005900001.jpg">
1. (X) Permissions associated with the role AROACLKWSDQRAOEXAMPLE:app1
2. Permissions associated with the default role used when the AWS service was built
3. Permission associated with the IAM principal that owns the AccessKeyID ASgeIAIOSFODNN7EXAMPLE
4. Permissions associated with the account that owns the AWS service

\
A company has multiple Developers located across the globe who are updating code incrementally for a development project. When Developers upload code concurrently, internet connectivity is slow and it is taking a long time to upload code for deployment in AWS Elastic Beanstalk.
Which step will result in minimized upload and deployment time with the LEAST amount of administrative effort?
1. Allow the Developers to upload the code to an Amazon S3 bucket, and deploy it directly to Elastic Beanstalk.
2. Allow the Developers to upload the code to a central FTP server to deploy the application to Elastic Beanstalk.
3. (X) Create an AWS CodeCommit repository, allow the Developers to commit code to it, and then directly deploy the code to Elastic Beanstalk.
4. Create a code repository on an Amazon EC2 instance so that all Developers can update the code, and deploy the application from the instance to Elastic Beanstalk.

An application running on Amazon EC2 instances must access objects within an Amaon S3 busket that are encrypted using server-side encryption using AWS
KMS encryption keys (SSE-KMS). The application must have access to the customer master key (CMK) to decrypt the objects.\
Which combination of steps will grant the application access? (Select TWO.)
1. Write an S3 bucket policy that grants the bucket access to the key.
2. (X) Grant access to the key in the IAM EC2 role attached to the application's EC2 instances.
3. (X) Write a key policy that enables IAM policies to grant access to the key.
4. Grant access to the key in the S3 bucket's ACL
5. Create a Systems Manager parameter that exposes the KMS key to the EC2 instances.
 
\ 
A Developer is designing a fault-tolerant environment where client sessions will be saved.
How can the Developer ensure that no sessions are lost if an Amazon EC2 instance fails?
1. Use sticky sessions with an Elastic Load Balancer target group.
2. Use Amazon SQS to save session data.
3. (X) Use Amazon DynamoDB to perform scalable session hadling.
4. Use Elastic Load Balancer connection draining to stop sending requests to failing instances.

\
How should custom libraries be utilized in AWS Lambda?
1. Host the library on Amazon S3 and reference to it from the Lambda function.
2. (X) Install the library locally and upload a ZIP file of the Lambda function.
3. Import the necessary Lambda blueprint when creating the function.
4. Modify the function runtime to include the necessary library.

\
An AWS Lambda function generates a 3MB JSON file and then uploads it to an Amazon S3 bucket daily. The file contains sensitive information, so the Developer must ensure that it is encrypted before uploading to the bucket.
Which of the following modifications should the Developer make to ensure that the data is encrypted before uploading it to the bucket?
1. Use the default AWS KMS customer master key for S3 in the Lambda function code.
2. Use the S3 managed key and call the GenerateDataKey API to encrypt the file.
3. (X) Use the GenerateDataKey API, then use that data key to encrypt the file in the Lambda function code.
4. Use a custom KMS customer master key created for S3 in the Lambda function code.

\
A Developer has published an update to an application that is served to a global user base using Amazon CloudFront. After deploying the application, users are not able to see the updated changes.\
How can the Developer resolve this issue?
1. Remove the origin from the CloudFront configuration and add it again.
2. Disable forwarding of query strings and request headers from the CloudFront distribution configuration.
3. (X) Invalidate all the application objects from the edge caches.
4. Disable the CloudFront distribution and enable it again to update all the edge locations.

A Developer wants to enable AWS X-Ray for a secure application that runs in an Amazon ECS environment.\
What combination of steps will enable X-Ray? (Select THREE.)
1. (X) Create a Docker image that runs the X-Ray daemon.
2. (X) Add instrumentation to the application code for X-Ray.
3. Install the X-Ray daemon on the underlying EC2 instance.
4. Configure and use an IAM EC2 instance role.
5. Register the application with X-Ray.
6. (X) Configure and use an IAM role for tasks.

\
An AWS Elastic Beanstalk application needs to be deployed in multiple regions and requires a different Amazon Machine Image (AMI) in each region.
Which AWS CloudFormation template key can be used to specify the correct AMI for each region?
1. Parameters
2. Outputs
3. (X) Mappings
4. Resources

\
A Developer writes an AWS Lambda function and uploads the code in a .ZIP file to Amazon S3. The Developer makes changes to the code and uploads a new
.ZIP file to Amazon S3. However, Lambda executes the earlier code.
How can the Developer fix this in the LEAST disruptive way?
1. Create another Lambda function and specify the new .ZIP file.
2. (X) Call the update-function-code API.
3. Remove the earlier .ZIP file first, then add the new .ZIP file.
4. Call the create-alias API. 

An AWS Lambda function must read data from an Amazon RDS MySQL database in a VPC and also reach a public endpoint over the internet to get additional data.
Which steps must be taken to allow the function to access both the RDS resource and the public endpoint? (Select TWO.)
1. (X) Modify the default configuration for the Lambda function to associate it with an Amazon VPC private subnet.
2. Modify the default network access control list to allow outbound traffic.
3. (X) Add a NAT Gateway to the VPC.
4. Modify the default configuration of the Lambda function to associate it with a VPC public subnet.
5. Add an environmental variable to the Lambda function to allow outbound internet access.

\
A Developer is creating an AWS Lambda function to process a stream of data from an Amazon Kinesis Data Stream. When the Lambda function parses the data and encounters a missing field, it exits the function with an error. The function is generating duplicate records from the Kinesis stream. When the Developer looks at the stream output without the Lambda function, there are no duplicate records.
What is the reason for the duplicates?
1. The Lambda function did not advance the Kinesis stream pointer to the next record after the error.
2. The Lambda event source used asynchronous invocation, resulting in duplicate records.
3. (X) The Lambda function did not handle the error, and the Lambda service attempted to reprocess the data.
4. The Lambda function is not keeping up with the amount of data coming from the stream.

\
A company is providing services to many downstream consumers. Each consumer may connect to one or more services. This has resulted in a complex architecture that is difficult to manage and does not scale well. The company needs a single interface to manage these services to consumers.
Which AWS service should be used to refactor this architecture?
1. AWS Lambda
2. AWS X-Ray
3. Amazon SQS
4. (X) Amazon API Gateway

\
A Development team has pushed out 10 applications running on several Amazon EC2 instances. The Operations team is asking for a graphical representation of one key performance metric for each application. These metrics should be available on one screen for easy monitoring.
Which steps should the Developer take to accomplish this using Amazon CloudWatch?
1. (X) Create a custom namespace with a unique metric name for each application.
2. Create a custom dimension with a unique metric name for each application.
3. Create a custom event with a unique metric name for each application.
4. Create a custom alarm with a unique metric name for each application.

\
A Developer wants access to make the log data of an application running on an EC2 instance available to systems administrators.
Which of the following enables monitoring of this metric in Amazon CloudWatch?
1. Retrieve the log data from CloudWatch using the GetMetricData API call
2. Retrieve the log data from AWS CloudTrail using the LookupEvents API call.
3. Launch a new EC2 instance, configure Amazon CloudWatch Events, and then install the application.
4. (X) Install the Amazon CloudWatch Logs agent on the EC2 instance that the application is running on.