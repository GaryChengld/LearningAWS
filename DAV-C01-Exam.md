A deployment package uses the AWS CLI to copy files into any S3 bucket in the account, using access keys stored in environment variables. The package is running on EC2 instances, and the instances have been modified to run with an assumed IAM role and a more restrictive policy that allows access to only one bucket. After the change, the Developer logs into the host and still has the ability to write into all of the S3 buckets in that account.\
What is the MOST likely cause of this situation?
  1. An IAM inline policy is being used on the IAM role
  2. An IAM managed policy is being used on the IAM role
  3. The AWS CLI is corrupt and needs to be reinstalled
  4. The AWS credential provider looks for instance profile credentials last

4


An application has hundreds of users. Each user may use multiple devices to access the application. The Developer wants to assign unique identifiers to these users regardless of the device they use.\
Which of the following methods should be used to obtain unique identifiers?
1. Create a user table in Amazon DynamoDB as key-value pairs of users and their devices. Use these keys as unique identifiers.
2. Use IAM-generated access key IDs for the users as the unique identifier, but do not store secret keys.
3. Implement developer-authenticated identities by using Amazon Cognito, and get credentials for these identities.
4. Assign IAM users and roles to the users. Use the unique IAM resource ID as the unique identifier.

3


A Developer is creating a Lambda function and will be using external libraries that are not included in the standard Lambda libraries.
What action would minimize the Lambda compute time consumed?
1. Install the dependencies and external libraries at the beginning of the Lambda function.
2. Create a Lambda deployment package that includes the external libraries.
3. Copy the external libraries to Amazon S3, and reference the external libraries to the S3 location.
4. Install the external libraries in Lambda to be available to all Lambda functions.

4


A company is migrating its on-premises database to Amazon RDS for MySQL. The company has read-heavy workloads, and wants to make sure it re-factors its code to achieve optimum read performance for its queries.
How can this objective be met?
1. Add database retries to effectively use RDS with vertical scaling
2. Use RDS with multi-AZ deployment
3. Add a connection string to use an RDS read replica for read queries
4. Add a connection string to use a read replica on an EC2 instance.

3


A Developer is testing a Docker-based application that uses the AWS SDK to interact with Amazon DynamoDB. In the local development environment, the application has used IAM access keys. The application is now ready for deployment onto an ECS cluster.
How should the application authenticate with AWS services in production?
1. Configure an ECS task IAM role for the application to use
2. Refactor the application to call AWS STS AssumeRole based on an instance role
3. Configure AWS access key/secret access key environment variables with new credentials
4. Configure the credentials file with a new access key/secret access key

1


The Lambda function below is being called through an API using Amazon API Gateway. The average execution time for the Lambda function is about 1 second.
The pseudocode for the Lambda function is as shown in the exhibit.
<img src="https://www.examtopics.com/assets/media/exam-media/02738/0002100001.png">
What two actions can be taken to improve the performance of this Lambda function without increasing the cost of the solution? (Select two.)
1. Package only the modules the Lambda function requires
2. Use Amazon DynamoDB instead of Amazon RDS
3. Move the initialization of the variable Amazon RDS connection outside of the handler function
4. Implement custom database connection pooling with the Lambda function
5. Implement local caching of Amazon RDS data so Lambda can re-use the cache

1,3


A Developer has setup an Amazon Kinesis Stream with 4 shards to ingest a maximum of 2500 records per second. A Lambda function has been configured to process these records.
In which order will these records be processed?
1. Lambda will receive each record in the reverse order it was placed into the stream following a LIFO (last-in, first-out) method
2. Lambda will receive each record in the exact order it was placed into the stream following a FIFO (first-in, first-out) method.
3. Lambda will receive each record in the exact order it was placed into the shard following a FIFO (first-in, first-out) method. There is no guarantee of order across shards.
4. The Developer can select FIFO, (first-in, first-out), LIFO (last-in, last-out), random, or request specific record using the getRecords API.

3


For a deployment using AWS CodeDeploy, what is the run order of the hooks for in-place deployments?
1. Before Install -> Application Stop -> Application Start -> After Install
2. Application Stop -> Before Install -> After Install -> Application Start
3. Before Install -> Application Stop -> Validate Service -> Application Start
4. Application Stop -> Before Install -> Validate Service -> Application Start

2


A Developer is developing an application that manages financial transactions. To improve security, multi-factor authentication (MFA) will be required as part of the login protocol.
What services can the Developer use to meet these requirements?
1. Amazon DynamoDB to store MFA session data, and Amazon SNS to send MFA codes
2. Amazon Cognito with MFA
3. AWS Directory Service
4. AWS IAM with MFA enabled

2


A supplier is writing a new RESTful API for customers to query the status of orders. The customers requested the following API endpoint. http://www.supplierdomain.com/status/customerID
Which of the following application designs meet the requirements? (Select two.)
1. Amazon SQS; Amazon SNS
2. Elastic Load Balancing; Amazon EC2
3. Amazon ElastiCache; Amazon Elacticsearch Service
4. Amazon API Gateway; AWS Lambda
5. Amazon S3; Amazon CloudFront

2,4


A legacy service has an XML-based SOAP interface. The Developer wants to expose the functionality of the service to external clients with the Amazon API
Gateway. Which technique will accomplish this?
1. Create a RESTful API with the API Gateway; transform the incoming JSON into a valid XML message for the SOAP interface using mapping templates.
2. Create a RESTful API with the API Gateway; pass the incoming JSON to the SOAP interface through an Application Load Balancer.
3. Create a RESTful API with the API Gateway; pass the incoming XML to the SOAP interface through an Application Load Balancer.
4. Create a RESTful API with the API Gateway; transform the incoming XML into a valid message for the SOAP interface using mapping templates.

1


A company is using AWS CodeBuild to compile a website from source code stored in AWS CodeCommit. A recent change to the source code has resulted in the
CodeBuild project being unable to successfully compile the website.
How should the Developer identify the cause of the failures?
1. Modify the buildspec.yml file to include steps to send the output of build commands to Amazon CloudWatch.
2. Use a custom Docker image that includes the AWS X-Ray agent in the AWS CodeBuild project configuration.
3. Check the build logs of the failed phase in the last build attempt in the AWS CodeBuild project build history.
4. Manually re-run the build process on a local machine so that the output can be visualized.

3


A Developer executed a AWS CLI command and received the error shown below:
<img src="https://www.examtopics.com/assets/media/exam-media/02738/0002800001.png">
What action should the Developer perform to make this error human-readable?
1. Make a call to AWS KMS to decode the message.
2. Use the AWS STS decode-authorization-message API to decode the message.
3. Use an open source decoding library to decode the message.
4. Use the AWS IAM decode-authorization-message API to decode this message.

2


An application stops working with the following error: The specified bucket does not exist. Where is the BEST place to start the root cause analysis?
1. Check the Elastic Load Balancer logs for DeleteBucket requests.
2. Check the application logs in Amazon CloudWatch Logs for Amazon S3 DeleteBucket errors.
3. Check AWS X-Ray for Amazon S3 DeleteBucket alarms.
4. Check AWS CloudTrail for a DeleteBucket event.

4


A Developer must repeatedly and consistently deploy a serverless RESTful API on AWS.\
Which techniques will work? (Choose two.)
1. Define a Swagger file. Use AWS Elastic Beanstalk to deploy the Swagger file.
2. Define a Swagger file. Use AWS CodeDeploy to deploy the Swagger file.
3. Deploy a SAM template with an inline Swagger definition.
4. Define a Swagger file. Deploy a SAM template that references the Swagger file.
5. Define an inline Swagger definition in a Lambda function. Invoke the Lambda function.

3,4


A set of APIs are exposed to customers using the Amazon API Gateway. These APIs have caching enabled on the API Gateway. Customers have asked for an option to invalidate this cache for each of the APIs.
What action can be taken to allow API customers to invalidate the API Cache?
1. Ask customers to use AWS credentials to call the InvalidateCache API.
2. Ask customers to invoke an AWS API endpoint which invalidates the cache.
3. Ask customers to pass an HTTP header called Cache-Control:max-age=0.
4. Ask customers to add a query string parameter called "INVALIDATE_CACHE" when making an API call.

3


A company is developing a new online game that will run on top of Amazon ECS. Four distinct Amazon ECS services will be part of the architecture, each requiring specific permissions to various AWS services. The company wants to optimize the use of the underlying Amazon EC2 instances by bin packing the containers based on memory reservation.
Which configuration would allow the Development team to meet these requirements MOST securely?
1. Create a new Identity and Access Management (IAM) instance profile containing the required permissions for the various ECS services, then associate that instance role with the underlying EC2 instances.
2. Create four distinct IAM roles, each containing the required permissions for the associated ECS service, then configure each ECS service to reference the associated IAM role.
3. Create four distinct IAM roles, each containing the required permissions for the associated ECS service, then, create an IAM group and configure the ECS cluster to reference that group.
4. Create four distinct IAM roles, each containing the required permissions for the associated ECS service, then configure each ECS task definition to referenÑe the associated IAM role.

4


An application is real-time processing millions of events that are received through an API.
What service could be used to allow multiple consumers to process the data concurrently and MOST cost-effectively?
1. Amazon SNS with fanout to an SQS queue for each application
2. Amazon SNS with fanout to an SQS FIFO (first-in, firtst-out) queue for each application
3. Amazon Kinesis Firehouse
4. Amazon Kinesis Streams

4


A Developer must trigger an AWS Lambda function based on the item lifecycle activity in an Amazon DynamoDB table.\
How can the Developer create the solution?
1. Enable a DynamoDB stream that publishes an Amazon SNS message. Trigger the Lambda function synchronously from the SNS message.
2. Enable a DynamoDB stream that publishes an SNS message. Trigger the Lambda function asynchronously from the SNS message.
3. Enable a DynamoDB stream, and trigger the Lambda function synchronously from the stream.
4. Enable a DynamoDB stream, and trigger the Lambda function asynchronously from the stream.

3


A social media company is using Amazon Cognito in order to synchronize profiles across different mobile devices, to enable end users to have a seamless experience.
Which of the following configurations can be used to silently notify users whenever an update is available on all other devices?
1. Modify the user pool to include all the devices which keep them in sync.
2. Use the SyncCallback interface to receive notifications on the application.
3. Use an Amazon Cognito stream to analyze the data and push the notifications.
4. Use the push synchronization feature with the appropriate IAM role.

4


A website's page load times are gradually increasing as more users access the system at the same time. Analysis indicates that a user profile is being loaded from a database in all the web pages being visited by each user and this is increasing the database load and the page load latency. To address this issue the
Developer decides to cache the user profile data.\
Which caching strategy will address this situation MOST efficiently?
1. Create a new Amazon EC2 Instance and run a NoSQL database on it. Cache the profile data within this database using the write-through caching strategy.
2. Create an Amazon ElastiCache cluster to cache the user profile data. Use a cache-aside caching strategy.
3. Use a dedicated Amazon RDS instance for caching profile data. Use a write-through caching strategy.
4. Create an ElastiCache cluster to cache the user profile data. Use a write-through caching strategy.

2


A development team is using AWS Elastic Beanstalk to deploy a two-tier application that consists of a load-balanced web tier and an Amazon RDS database tier in production. The team would like to separate the RDS instance from the Elastic Beanstalk.
How can this be accomplished?
1. Use the Elastic Beanstalk CLI to disassociate the database.
2. Use the AWS CLI to disassociate the database.
3. Change the deployment policy to disassociate the database.
4. Recreate a new Elastic Beanstalk environment without Amazon RDS.

4


The development team is working on an API that will be served from Amazon API gateway. The API will be served from three environments: development, test, and production. The API Gateway is configured to use 237 GB of cache in all three stages.
Which is the MOST cost-efficient deployment strategy?
1. Create a single API Gateway with all three stages.
2. Create three API Gateways, one for each stage in a single AWS account.
3. Create an API Gateway in three separate AWS accounts.
4. Enable the cache for development and test environments only when needed.

4


An application running on an Amazon Linux EC2 instance needs to manage the AWS infrastructure.
How can the EC2 instance be configured to make AWS API calls securely?
1. Sign the AWS CLI command using the signature version 4 process.
2. Run the aws configure AWS CLI command and specify the access key id and secret access key.
3. Specify a role for the EC2 instance with the necessary privileges.
4. Pass the access key id and secret access key as parameters for each AWS CLI command.

3


A Developer is creating a Lambda function that will generate and export a file. The function requires 100 MB of temporary storage for temporary files while executing. These files will not be needed after the function is complete.
How can the Developer MOST efficiently handle the temporary files?
1. Store the files in EBS and delete the files at the end of the Lambda function.
2. Copy the files to EFS and delete the files at the end of the Lambda function.
3. Store the files in the /tmp directory and delete the files at the end of the Lambda function.
4. Copy the files to an S3 bucket with a lifecycle policy to delete the files.

3


AWS CodeBuild builds code for an application, creates the Docker image, pushes the image to Amazon Elastic Container Registry (Amazon ECR), and tags the image with a unique identifier.
If the Developers already have AWS CLI configured on their workstations, how can the Docker images be pulled to the workstations?
1. Run the following: docker pull REPOSITORY URI : TAG
2. Run the output of the following: aws ecr get-login and then run: docker pull REPOSITORY URI : TAG
3. Run the following: aws ecr get-login and then run: docker pull REPOSITORY URI : TAG
4. Run the output of the following: aws ecr get-download-url-for-layer and then run: docker pull REPOSITORY URI : TAG

2


A Developer wants to encrypt new objects that are being uploaded to an Amazon S3 bucket by an application. There must be an audit trail of who has used the key during this process. There should be no change to the performance of the application.
Which type of encryption meets these requirements?
1. Server-side encryption using S3-managed keys
2. Server-side encryption with AWS KMS-managed keys
3. Client-side encryption with a client-side symmetric master key
4. Client-side encryption with AWS KMS-managed keys

2


While developing an application that runs on Amazon EC2 in an Amazon VPC, a Developer identifies the need for centralized storage of application-level logs.
Which AWS service can be used to securely store these logs?
1. Amazon EC2 VPC Flow Logs
2. Amazon CloudWatch Logs
3. Amazon CloudSearch
4. AWS CloudTrail

2


An application uses Amazon Kinesis Data Streams to ingest and process large streams of data records in real time. Amazon EC2 instances consume and process the data from the shards of the Kinesis data stream by using Amazon Kinesis Client Library (KCL). The application handles the failure scenarios and does not require standby workers. The application reports that a specific shard is receiving more data than expected. To adapt to the changes in the rate of data flow, the "hot" shard is resharded.
Assuming that the initial number of shards in the Kinesis data stream is 4, and after resharding the number of shards increased to 6, what is the maximum number of EC2 instances that can be deployed to process data from all the shards?
1. 12
2. 6
3. 4
4. 1

2

Typically, when you use the KCL, you should ensure that the number of instances does not exceed the number of shards (except for failure standby purposes). Each shard is processed by exactly one KCL worker and has exactly one corresponding record processor, so you never need multiple instances to process one shard. However, one worker can process any number of shards, so it's fine if the number of shards exceeds the number of instances.
https://docs.aws.amazon.com/streams/latest/dev/kinesis-record-processor-scaling.html

\
A Development team is working on a case management solution that allows medical claims to be processed and reviewed. Users log in to provide information related to their medical and financial situations.
As part of the application, sensitive documents such as medical records, medical imaging, bank statements, and receipts are uploaded to Amazon S3. All documents must be securely transmitted and stored. All access to the documents must be recorded for auditing.
What is the MOST secure approach?
1. Use S3 default encryption using Advanced Encryption Standard-256 (AES-256) on the destination bucket.
2. Use Amazon Cognito for authorization and authentication to ensure the security of the application and documents.
3. Use AWS Lambda to encrypt and decrypt objects as they are placed into the S3 bucket.
4. Use client-side encryption/decryption with Amazon S3 and AWS KMS.

4

Not only will KMS provide the Auditing you need, but with client-side encryption although a little more work on client side, this method provides the needed encryption at rest since the data has to be encrypted before being transmitted to s3 for storage, and it REQUIRES (and only allows) HTTPS for the transmission across to the bucket

\
A company has an internet-facing application that uses Web Identity Federation to obtain a temporary credential from AWS Security Token Service (AWS STS).
The app then uses the token to access AWS services.
Review the following response:
<img src="https://www.examtopics.com/assets/media/exam-media/02738/0005900001.jpg">
1. Permissions associated with the role AROACLKWSDQRAOEXAMPLE:app1
2. Permissions associated with the default role used when the AWS service was built
3. Permission associated with the IAM principal that owns the AccessKeyID ASgeIAIOSFODNN7EXAMPLE
4. Permissions associated with the account that owns the AWS service

1


A company has multiple Developers located across the globe who are updating code incrementally for a development project. When Developers upload code concurrently, internet connectivity is slow and it is taking a long time to upload code for deployment in AWS Elastic Beanstalk.
Which step will result in minimized upload and deployment time with the LEAST amount of administrative effort?
1. Allow the Developers to upload the code to an Amazon S3 bucket, and deploy it directly to Elastic Beanstalk.
2. Allow the Developers to upload the code to a central FTP server to deploy the application to Elastic Beanstalk.
3. Create an AWS CodeCommit repository, allow the Developers to commit code to it, and then directly deploy the code to Elastic Beanstalk.
4. Create a code repository on an Amazon EC2 instance so that all Developers can update the code, and deploy the application from the instance to Elastic Beanstalk.

3


An application running on Amazon EC2 instances must access objects within an Amaon S3 busket that are encrypted using server-side encryption using AWS
KMS encryption keys (SSE-KMS). The application must have access to the customer master key (CMK) to decrypt the objects.\
Which combination of steps will grant the application access? (Select TWO.)
1. Write an S3 bucket policy that grants the bucket access to the key.
2. Grant access to the key in the IAM EC2 role attached to the application's EC2 instances.
3. Write a key policy that enables IAM policies to grant access to the key.
4. Grant access to the key in the S3 bucket's ACL
5. Create a Systems Manager parameter that exposes the KMS key to the EC2 instances.
 
2,3


A Developer is designing a fault-tolerant environment where client sessions will be saved.
How can the Developer ensure that no sessions are lost if an Amazon EC2 instance fails?
1. Use sticky sessions with an Elastic Load Balancer target group.
2. Use Amazon SQS to save session data.
3. Use Amazon DynamoDB to perform scalable session hadling.
4. Use Elastic Load Balancer connection draining to stop sending requests to failing instances.

2


How should custom libraries be utilized in AWS Lambda?
1. Host the library on Amazon S3 and reference to it from the Lambda function.
2. Install the library locally and upload a ZIP file of the Lambda function.
3. Import the necessary Lambda blueprint when creating the function.
4. Modify the function runtime to include the necessary library.

2


An AWS Lambda function generates a 3MB JSON file and then uploads it to an Amazon S3 bucket daily. The file contains sensitive information, so the Developer must ensure that it is encrypted before uploading to the bucket.
Which of the following modifications should the Developer make to ensure that the data is encrypted before uploading it to the bucket?
1. Use the default AWS KMS customer master key for S3 in the Lambda function code.
2. Use the S3 managed key and call the GenerateDataKey API to encrypt the file.
3. Use the GenerateDataKey API, then use that data key to encrypt the file in the Lambda function code.
4. Use a custom KMS customer master key created for S3 in the Lambda function code.

3


A Developer has published an update to an application that is served to a global user base using Amazon CloudFront. After deploying the application, users are not able to see the updated changes.\
How can the Developer resolve this issue?
1. Remove the origin from the CloudFront configuration and add it again.
2. Disable forwarding of query strings and request headers from the CloudFront distribution configuration.
3. Invalidate all the application objects from the edge caches.
4. Disable the CloudFront distribution and enable it again to update all the edge locations.

3


A Developer wants to enable AWS X-Ray for a secure application that runs in an Amazon ECS environment.\
What combination of steps will enable X-Ray? (Select THREE.)
1. Create a Docker image that runs the X-Ray daemon.
2. Add instrumentation to the application code for X-Ray.
3. Install the X-Ray daemon on the underlying EC2 instance.
4. Configure and use an IAM EC2 instance role.
5. Register the application with X-Ray.
6. Configure and use an IAM role for tasks.

1,2,6


An AWS Elastic Beanstalk application needs to be deployed in multiple regions and requires a different Amazon Machine Image (AMI) in each region.
Which AWS CloudFormation template key can be used to specify the correct AMI for each region?
1. Parameters
2. Outputs
3. Mappings
4. Resources

3


A Developer writes an AWS Lambda function and uploads the code in a .ZIP file to Amazon S3. The Developer makes changes to the code and uploads a new
.ZIP file to Amazon S3. However, Lambda executes the earlier code.
How can the Developer fix this in the LEAST disruptive way?
1. Create another Lambda function and specify the new .ZIP file.
2. Call the update-function-code API.
3. Remove the earlier .ZIP file first, then add the new .ZIP file.
4. Call the create-alias API. 

2


An AWS Lambda function must read data from an Amazon RDS MySQL database in a VPC and also reach a public endpoint over the internet to get additional data.
Which steps must be taken to allow the function to access both the RDS resource and the public endpoint? (Select TWO.)
1. Modify the default configuration for the Lambda function to associate it with an Amazon VPC private subnet.
2. Modify the default network access control list to allow outbound traffic.
3. Add a NAT Gateway to the VPC.
4. Modify the default configuration of the Lambda function to associate it with a VPC public subnet.
5. Add an environmental variable to the Lambda function to allow outbound internet access.

1,3


A Developer is creating an AWS Lambda function to process a stream of data from an Amazon Kinesis Data Stream. When the Lambda function parses the data and encounters a missing field, it exits the function with an error. The function is generating duplicate records from the Kinesis stream. When the Developer looks at the stream output without the Lambda function, there are no duplicate records.
What is the reason for the duplicates?
1. The Lambda function did not advance the Kinesis stream pointer to the next record after the error.
2. The Lambda event source used asynchronous invocation, resulting in duplicate records.
3. The Lambda function did not handle the error, and the Lambda service attempted to reprocess the data.
4. The Lambda function is not keeping up with the amount of data coming from the stream.

3


A company is providing services to many downstream consumers. Each consumer may connect to one or more services. This has resulted in a complex architecture that is difficult to manage and does not scale well. The company needs a single interface to manage these services to consumers.
Which AWS service should be used to refactor this architecture?
1. AWS Lambda
2. AWS X-Ray
3. Amazon SQS
4. Amazon API Gateway

4


A Development team has pushed out 10 applications running on several Amazon EC2 instances. The Operations team is asking for a graphical representation of one key performance metric for each application. These metrics should be available on one screen for easy monitoring.
Which steps should the Developer take to accomplish this using Amazon CloudWatch?
1. Create a custom namespace with a unique metric name for each application.
2. Create a custom dimension with a unique metric name for each application.
3. Create a custom event with a unique metric name for each application.
4. Create a custom alarm with a unique metric name for each application.

1


A Developer wants access to make the log data of an application running on an EC2 instance available to systems administrators.
Which of the following enables monitoring of this metric in Amazon CloudWatch?
1. Retrieve the log data from CloudWatch using the GetMetricData API call
2. Retrieve the log data from AWS CloudTrail using the LookupEvents API call.
3. Launch a new EC2 instance, configure Amazon CloudWatch Events, and then install the application.
4. Install the Amazon CloudWatch Logs agent on the EC2 instance that the application is running on.

4


A company maintains a REST service using Amazon API Gateway and the API Gateway native API key validation. The company recently launched a new registration page, which allows users to sign up for the service. The registration page creates a new API key using CreateApiKey and sends the new key to the user. When the user attempts to call the API using this key, the user receives a 403 Forbidden error. Existing users are unaffected and can still call the API.
What code updates will grant these new users access to the API?
1. The createDeployment method must be called so the API can be redeployed to include the newly created API key.
2. The updateAuthorizer method must be called to update the API's authorizer to include the newly created API key.
3. The importApiKeys method must be called to import all newly created API keys into the current stage of the API.
4. The createUsagePlanKey method must be called to associate the newly created API key with the correct usage plan.

4


A Developer must analyze performance issues with production-distributed applications written as AWS Lambda functions. These distributed Lambda applications invoke other components that make up the applications.
How should the Developer identify and troubleshoot the root cause of the performance issues in production?
1. Add logging statements to the Lambda functions, then use Amazon CloudWatch to view the logs.
2. Use AWS Cloud Trail and then examine the logs
3. Use AWS X-Ray, then examine the segments and errors
4. Run Amazon Inspector agents and then analyze performance

3

A Developer wants to debug an application by searching and filtering log data. The application logs are stored in Amazon CloudWatch Logs. The Developer creates a new metric filter to count exceptions in the application logs. However, no results are returned from the logs.
What is the reason that no filtered results are being returned?
1. A setup of the Amazon CloudWatch interface VPC endpoint is required for filtering the CloudWatch Logs in the VPC
2. CloudWatch Logs only publishes metric data for events that happen after the filter is created
3. The log group for CloudWatch Logs should be first streamed to Amazon Elasticsearch Service before metric filtering returns the results
4. Metric data points for logs groups can be filtered only after they are exported to an Amazon S3 bucket
 
2

A Developer is creating a template that uses AWS CloudFormation to deploy an application. This application is serverless and uses Amazon API Gateway,
Amazon DynamoDB, and AWS Lambda.
Which tool should the Developer use to define simplified syntax for expressing serverless resources?
1. CloudFormation serverless intrinsic functions
2. AWS serverless express
3. An AWS serverless application model
4. A CloudFormation serverless plugin

3


A company is running an application built on AWS Lambda functions. One Lambda function has performance issues when it has to download a 50MB file from the
Internet in every execution. This function is called multiple times a second.
What solution would give the BEST performance increase?
1. Cache the file in the /tmp directory
2. Increase the Lambda maximum execution time
3. Put an Elastic Load Balancer in front of the Lambda function
4. Cache the file in Amazon S3

1

\
An application writes items to an Amazon DynamoDB table. As the application scales to thousands of instances, calls to the DynamoDB API generate occasional
ThrottlingException errors. The application is coded in a language incompatible with the AWS SDK.
How should the error be handled?
1. Add exponential backoff to the application logic
2. Use Amazon SQS as an API message bus
3. Pass API calls through Amazon API Gateway
4. Send the items to DynamoDB through Amazon Kinesis Data Firehose

1

\
A Developer is building a web application that uses Amazon API Gateway to expose an AWS Lambda function to process requests from clients. During testing, the Developer notices that the API Gateway times out even though the Lambda function finishes under the set time limit.\
Which of the following API Gateway metrics in Amazon CloudWatch can help the Developer troubleshoot the issue? (Choose two.)
1. CacheHitCount
2. IntegrationLatency
3. CacheMissCount
4. Latency
5. Count

2,4

\
An AWS Lambda function must access an external site by using a regularly rotated user name and password. These items must be kept securely and cannot be stored in the function code.
What combination of AWS services can be used to accomplish this? (Choose two.)
1. AWS Certificate Manager (ACM)
2. AWS Systems Manager Parameter Store
3. AWS Trusted Advisor
4. AWS KMS
5. Amazon GuardDuty

2,4

\
A Developer wants to upload data to Amazon S3 and must encrypt the data in transit.
Which of the following solutions will accomplish this task? (Choose two.)
1. Set up hardware VPN tunnels to a VPC and access S3 through a VPC endpoint
2. Set up Client-Side Encryption with an AWS KMS-Managed Customer Master Key
3. Set up Server-Side Encryption with AWS KMS-Managed Keys
4. Transfer the data over an SSL connection
5. Set up Server-Side Encryption with S3-Managed Keys

2,4

\
A Developer has been asked to create an AWS Lambda function that is triggered any time updates are made to items in an Amazon DynamoDB table. The function has been created, and appropriate permissions have been added to the Lambda execution role. Amazon DynamoDB streams have been enabled for the table, but the function is still not being triggered.
Which option would enable DynamoDB table updates to trigger the Lambda function?
1. Change the StreamViewType parameter value to NEW_AND_OLD_IMAGES for the DynamoDB table
2. Configure event source mapping for the Lambda function
3. Map an Amazon SNS topic to the DynamoDB streams
4. increase the maximum execution time (timeout) setting of the Lambda function

2

\
A Developer is building a three-tier web application that should be able to handle a minimum of 5000 requests per minute. Requirements state that the web tier should be completely stateless while the application maintains session state for the users.
How can session data be externalized, keeping latency at the LOWEST possible value?
1. Create an Amazon RDS instance, then implement session handling at the application level to leverage a database inside the RDS database instance for session data storage
2. Implement a shared file system solution across the underlying Amazon EC2 instances, then implement session handling at the application level to leverage the shared file system for session data storage
3. Create an Amazon ElastiCache Memcached cluster, then implement session handling at the application level to leverage the cluster for session data storage
4. Create an Amazon DynamoDB table, then implement session handling at the application level to leverage the table for session data storage

3

\
An Amazon DynamoDB table uses a Global Secondary Index (GSI) to support read queries. The primary table is write-heavy, whereas the GSI is used for read operations. Looking at Amazon CloudWatch metrics, the Developer notices that write operations to the primary table are throttled frequently under heavy write activity. However, write capacity units to the primary table are available and not fully consumed.
Why is the table being throttled?
1. The GSI write capacity units are underprovisioned
2. There are not enough read capacity units on the primary table
3. Amazon DynamoDB Streams is not enabled on the table
4. A large write operation is being performed against another table 

1

\
A Developer created a new AWS account and must create a scalable AWS Lambda function that meets the following requirements for concurrent execution:\
✑ Average execution time of 100 seconds\
✑ 50 requests per second\
Which step must be taken prior to deployment to prevent errors?
1. Implement dead-letter queues to capture invocation errors
2. Add an event source from Amazon API Gateway to the Lambda function
3. Implement error handling within the application code
4. Contact AWS Support to increase the concurrent execution limits

4

\
A Development team would like to migrate their existing application code from a GitHub repository to AWS CodeCommit.
What needs to be created before they can migrate a cloned repository to CodeCommit over HTTPS?
1. A GitHub secure authentication token
2. A public and private SSH key file
3. A set of Git credentials generated from IAM
4. An Amazon EC2 IAM role with CodeCommit permissions

3

\
When developing an AWS Lambda function that processes Amazon Kinesis Data Streams, Administrators within the company must receive a notice that includes the processed data.
How should the Developer write the function to send processed data to the Administrators?
1. Separate the Lambda handler from the core logic
2. Use Amazon CloudWatch Events to send the processed data
3. Publish the processed data to an Amazon SNS topic
4. Push the processed data to Amazon SQS

3

\
A Developer is storing documents in Amazon S3 that will require encryption at rest. The encryption keys must be rotated annually, at least.
What is the easiest way to achieve this?
1. Encrypt the data before sending it to Amazon S3
2. Import a custom key into AWS KMS with annual rotation enabled
3. Use AWS KMS with automatic key rotation
4. Export a key from AWS KMS to encrypt the data

3

\
What type of block cipher does Amazon S3 offer for server side encryption?
1. Triple DES
2. Advanced Encryption Standard
3. Blowfish
4. RC5

2

\
A corporate web application is deployed within an Amazon VPC, and is connected to the corporate data center via IPSec VPN. The application must authenticate against the on-premise LDAP server. Once authenticated, logged-in users can only access an S3 keyspace specific to the user.
Which two approaches can satisfy the objectives? (Choose two.)
1. The application authenticates against LDAP. The application then calls the IAM Security Service to login to IAM using the LDAP credentials. The application can use the IAM temporary credentials to access the appropriate S3 bucket.
2. The application authenticates against LDAP, and retrieves the name of an IAM role associated with the user. The application then calls the IAM Security Token Service to assume that IAM Role. The application can use the temporary credentials to access the appropriate S3 bucket.
3. The application authenticates against IAM Security Token Service using the LDAP credentials. The application uses those temporary AWS security credentials to access the appropriate S3 bucket.
4. Develop an identity broker which authenticates against LDAP, and then calls IAM Security Token Service to get IAM federated user credentials. The application calls the identity broker to get IAM federated user credentials with access to the appropriate S3 bucket.
5. Develop an identity broker which authenticates against IAM Security Token Service to assume an IAM Role to get temporary AWS security credentials. The application calls the identity broker to get AWS
 
2,4

\
You are providing AWS consulting services for a company developing a new mobile application that will be leveraging Amazon SNS Mobile Push for push notifications. In order to send direct notification messages to individual devices each device registration identifier or token needs to be registered with SNS; however the developers are not sure of the best way to do this.
You advise them to:
1. Bulk upload the device tokens contained in a CSV file via the AWS Management Console.
2. Let the push notification service (e.g. Amazon Device Messaging) handle the registration.
3. Implement a token vending service to handle the registration.
4. Call the CreatePlatformEndPoint API function to register multiple device tokens.

4

\
You are writing to a DynamoDB table and receive the following exception:"
ProvisionedThroughputExceededException". though according to your Cloudwatch metrics for the table, you are not exceeding your provisioned throughput.
What could be an explanation for this?
1. You haven't provisioned enough DynamoDB storage instances
2. You're exceeding your capacity on a particular Range Key
3. You're exceeding your capacity on a particular Hash Key
4. You're exceeding your capacity on a particular Sort Key
5. You haven't configured DynamoDB Auto Scaling triggers

3

\
What AWS products and features can be deployed by Elastic Beanstalk? (Choose three.)
1. Auto scaling groups
2. Route 53 hosted zones
3. Elastic Load Balancers
4. RDS Instances
5. Elastic IP addresses
6. SQS Queues

1,3,4

\
In DynamoDB, what type of HTTP response codes indicate that a problem was found with the client request sent to the service?
1. 5xx HTTP response code
2. 200 HTTP response code
3. 306 HTTP response code
4. 4xx HTTP response code

4
\

Which DynamoDB limits can be raised by contacting AWS support? (Choose two.)
1. The number of hash keys per account
2. The maximum storage used per account
3. The number of tables per account
4. The number of local secondary indexes per account
5. The number of provisioned throughput units per account

3,5

\
An application stores payroll information nightly in DynamoDB for a large number of employees across hundreds of offices. Item attributes consist of individual name, office identifier, and cumulative daily hours.
Managers run reports for ranges of names working in their office. One query is. "Return all Items in this office for names starting with A through E".
Which table configuration will result in the lowest impact on provisioned throughput for this query?
1. Configure the table to have a hash index on the name attribute, and a range index on the office identifier
2. Configure the table to have a range index on the name attribute, and a hash index on the office identifier
3. Configure a hash index on the name attribute and no range index
4. Configure a hash index on the office Identifier attribute and no range index

2

\
How can you secure data at rest on an EBS volume?
1. Attach the volume to an instance using EC2's SSL interface.
2. Write the data randomly instead of sequentially.
3. Use an encrypted file system on top of the BBS volume.
4. Encrypt the volume using the S3 server-side encryption service.
5. Create an IAM policy that restricts read and write access to the volume.

3

\
Which of the following statements about SWF are true? (Choose three.)
1. SWF tasks are assigned once and never duplicated
2. SWF requires an S3 bucket for workflow storage
3. SWF workflow executions can last up to a year
4. SWF triggers SNS notifications on task assignment
5. SWF uses deciders and workers to complete tasks
6. SWF requires at least 1 EC2 instance per domain

1,3,5

\
Which of the following are valid arguments for an SNS Publish request? (Choose three.)
1. TopicAm
2. Subject
3. Destination
4. Format
5. Message
6. Language

1,2,5

\
EC2 instances are launched from Amazon Machine images (AMIs). A given public AMI can:
1. be used to launch EC2 Instances in any AWS region.
2. only be used to launch EC2 instances in the same country as the AMI is stored.
3. only be used to launch EC2 instances in the same AWS region as the AMI is stored.
4. only be used to launch EC2 instances in the same AWS availability zone as the AMI is stored

3

\

Which EC2 API call would you use to retrieve a list of Amazon Machine Images (AMIs)?
1. DescnbeInstances
2. DescribeAMls
3. DescribeImages
4. GetAMls
5. You cannot retrieve a list of AMIs as there are over 10,000 AMIs

3

\

Which code snippet below returns the URL of a load balanced web site created in CloudFormation with an
AWS::ElasticLoadBalancing::LoadBalancer resource name "ElasticLoad Balancer"?
1. "Fn::Join" : ["". [ "http://", {"Fn::GetAtr" : [ "ElasticLoadBalancer","DNSName"]}]]
2. "Fn::Join" : ["". [ "http://", {"Fn::GetAtr" : [ "ElasticLoadBalancer","Url"]}]]
3. "Fn::Join" : ["". [ "http://", {"Ref" : "ElasticLoadBalancerUrl"}]]
4. "Fn::Join" : [".", [ "http://", {"Ref" : "ElasticLoadBalancerDNSName"}]]

1

\
Which of the following are correct statements with policy evaluation logic in AWS Identity and Access
Management? (Choose two.)
1. By default, all requests are denied
2. An explicit allow overrides an explicit deny
3. An explicit allow overrides default deny.
4. An explicit deny does not override an explicit allow
5. By default, all request are allowed

1, 3

\
You have an environment that consists of a public subnet using Amazon VPC and 3 instances that are running in this subnet. These three instances can successfully communicate with other hosts on the Internet. You launch a fourth instance in the same subnet, using the same AMI and security group configuration you used for the others, but find that this instance cannot be accessed from the Internet.
What should you do to enable internet access?
1. Deploy a NAT instance into the public subnet.
2. Modify the routing table for the public subnet
3. Configure a publically routable IP Address In the host OS of the fourth instance.
4. Assign an Elastic IP address to the fourth instance.

4

\
After launching an instance that you intend to serve as a NAT (Network Address Translation) device in a public subnet you modify your route tables to have the NAT device be the target of internet bound traffic of your private subnet. When you try and make an outbound connection to the Internet from an instance in the private subnet, you are not successful.
Which of the following steps could resolve the issue?
1. Attaching a second Elastic Network interface (ENI) to the NAT instance, and placing it in the private subnet
2. Attaching a second Elastic Network Interface (ENI) to the instance in the private subnet, and placing it in the public subnet
3. Disabling the Source/Destination Check attribute on the NAT instance
4. Attaching an Elastic IP address to the instance in the private subnet

3

\
The release process workflow of an application requires a manual approval before the code is deployed into the production environment.
What is the BEST way to achieve this using AWS CodePipeline?
1. Use multiple pipelines to allow approval
2. Use an approval action in a stage
3. Disable the stage transition to allow manual approval
4. Disable a stage just prior the deployment stage

4

\
A company wants to implement a continuous integration for its workloads on AWS. The company wants to trigger unit test in its pipeline for commits-on its code repository, and wants to be notified of failure events in the pipeline.
How can these requirements be met?
1. Store the source code in AWS CodeCommit. Create a CodePipeline to automate unit testing. Use Amazon SNS to trigger notifications of failure events.
2. Store the source code in GitHub. Create a CodePipeline to automate unit testing. Use Amazon SES to trigger notifications of failure events.
3. Store the source code on GitHub. Create a CodePipeline to automate unit testing. Use Amazon CloudWatch to trigger notifications of failure events.
4. Store the source code in AWS CodeCommit. Create a CodePipeline to automate unit testing. Use Amazon CloudWatch to trigger notification of failure events.

4
