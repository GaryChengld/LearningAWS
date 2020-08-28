## AWS Concepts

### AWS and cloud

#### What is cloud
"The cloud" refers to servers that are accessed over the Internet, and the software and databases that run on those servers. Cloud servers are located in data centers all over the world.

##### Service models
IaaS, PaaS, SaaS

* Non cloud IT stack: Application, Runtime, OS, Hardware, Networking, Building
* IaaS stack: Application, Runtime, OS
* PaaS: Application
* SaaS: Everything is provided by cloud (gmail)

##### Essential Characters
* On-demand self-service
* Broad network access
* Resource pooling
* Rapid elasticity
* Measured service

##### Deployment models
 * Private cloud
 * Community cloud
 * Public cloud
 * Hybird cloud

 AWS: Public cloud

#### What is AWS
AWS is a cloud service provider, also know as infrastructure as a service (IaaS.)
AWS provides Iaas, Paas, SaaS
Computer service, storage service, database service, networking service, security service, management tools, analatic service, mobile service, application service, messaging service, AI, Internet of things service, gaming service, SaaS

#### The benifits of cloud
  - High availibility
  - Falut tolerant
  - Scalibility
  - Elasticity

### Core AWS Services
 * VPC - Virtual private cloud, is your private section of AWS, where you can place AWS resources, and allow/restrict access to them.
 * EC2 - Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers. EC2 as a virtual computer that you can use for whatever you like. EC2 is good for any type of “processing” activity.
 * RDS - Amazon Relational Database Service (Amazon RDS) is a web service that makes it easier to set up, operate, and scale a relational database in the AWS Cloud. 
 * S3 - Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance.
 * Lambda - Function as a service

 ### AWS Global Infrastructure
  * AWS region
  * Availability zone
  * Edge locations
  * Data center

### Tools need to setup computer
  * Web browser
  * Remote Desktop Protocol (RDP) tool\
  * SSH tool

### Setup CLI
   * Download and install, [AWS Command Line Interface](https://aws.amazon.com/cli/)
   * Create security credentials
   * Configure the CLI tools

###  Essential Services   
#### Simple storage service - S3

The service
  * S3
  * Simple storage service
  * Cloud object storage

Use cases
  * backups
  * media files
  * log files
  * large data sets
  * web / media hosting

How it works
  * Unlimlited number of objects
  * Objects from Zero bytes to 5 TB
  * Containers are called 'buckets'
  * Access via API / HTTP

  #### S3 web hosting

  bucket-policy.txt
  ```
  {
    "Version": "2020-08-01",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::[bucket-name]/*"
        }
    ]
}
```

#### Lambda - Run functions of code in cloud

The service
  * Lambda
  * Executes functions of code
  * Functions as a Service (FaaS)

Use cases
  * Simple tasks
  * Batch tasks
  * Chained tasks
  * Serverless architectures
  * Almost anything

How it works
  * 'Single' function of code
  * Triggered by:
    * API / HTTP call
    * An AWS event
    * Timer
  * Multiple language support

#### Elastic Compute Cloud (EC2)

The Service
  * EC2
  * Elastic Compute Cloud
  * Virtual servers

Use cases
  * Web Server
  * Backend Server
  * (Database server)
  * general purpose servers

How it works
  * Pick your 'type' and 'size'
  * Pick your 'OS'
  * Select your storage
  * (plus much more)
  * Launch a instance

### All the services

#### Compute
  * EC2 (Elastic Compute Cloud)
  * Lightsail -- Virtual priovate server
  * ECS (Elastic Container Service) -- Container management service, manage Docker contaioners on a cluster
  * Lambda -- Serverless compute service
  * Batch
  * Elastic Beanstalk -- Servoce for deploying and scaling web applications and services

#### Storage
  * S3 (Simple Storage Service) - Cloud object storage
  * EFS (Elastic File System) - Cloud file storage
  * Glacier - Cloud archive service
  * Storage Gateway - Integrate existing onm-premises storage infrastructure and data with the AWS Cloud

#### Database
  * RDS (Amazon Relational Database Service)
  * DynamnoDB - Cloud NoSQL database
  * ElastiCache - In-memory data store and cache in the cloud
  * Amazon Redshift - Cloud data warehousing

#### Migration
  * AWS Migration Hub - Simpfy and accelerate migrations to the AWS Cloud
  * Application Discovery Service - Plan application cloud migration projects
  * Database Migration Service - Migrate database to AWS quickly and securely
  * SMS (Server Migration Service) - migrate your on-premises workloads to AWS
  * Snowball - Petabyte-scale data transport solution

#### Networking and Content Delivery
  * VPC (Virtual Private Cloud) - Private network in the cloud
  * CloudFront - Content distribution network
  * Route 53 - Cloud Domain Name System (DNS) web service
  * API Gateway - Create, publish,maintain, monitor and secure APIs at any scale
  * Direct Connect - Dedicated network connection from your premisses to AWS

#### Developer Tools
  * CodeStar - Develop, build and deploy applications
  * CodeCommit - Managed source control service
  * CodeBuild - Fully managed build service
  * CodeDeploy - Automates software deployments
  * CodePipeline - Continues delivery service
  * Cloud9 - Cloud-based integrated developenmt environment (IDE)
  * X-Ray - Debug and analyze your microservices applications

  #### Management Tools
    * CloudWatch - Monitoring service
    * CloudFormation - Model and provision all your cloud infrastructure resources
    * CloudTrail - Track user activity and API usage
    * Config - Record and evaluate conmfigurations of your AWS resources
    * OpsWorks - Automate Operations with Chef and Puppet
    * Service Catalog - Create and manage calalogs of IT services
    * Systems manager - Gain Operational Insights and Take Action on AWS Resources
    * Trusted Advisor - Optimizing your AWS environment
    * Managed Services - Infrastructure Operations Manmagement for AWS

  #### Media Service
    * Elastic Transcoder - Media transcoding in the cloud
    * Elemental
      * MediaConvert
      * MediaLive
      * MediaPackage
      * MediaStore
      * MediaTrailor

#### Machine Learning
  * Amazon SageMaker - Build, train and deploy machine learning models at scale
  * Amazon Comprehand - Discover insights and relationships in text
  * AWS DeepLens - Deep learning enabled video camera
  * Amazon Lex - Conversational interfaces for your applications
  * Machine Learning - Managed service for building ML models and generating predictions
  * Amazon Polly - Turn text into lifelike speech using deep learning
  * Rekognition - Deep learning-based image and video analysis
  * Amazon Transcribe - Automatic speech reconition
  * Amazon Translate - Natual and fluent language transaction

#### Analytics
  * Athena - Analyze data in Amazon S3 using standard SQL
  * EMR - Run and Scale Apache Hadoop, Spark, HBase, Presto, Hive and other big data frameworks
  * CloudSearch - Set up, manage and scale a search solution
  * ElasticSearch service - Fully managed, reliable and scalable Elasticsearch service.
  * Kinesis - Easily collect, process and analyze video and data streams in real time
  * Kinesis Video Streams - Capture, process and store video streams for analytics and machine learning
  * QuickSight - Business analytics service
  * Data Pipeline - Easily automate the movement and transformation of data
  * AWS Glue - Simple, flexible and cost effective ETL  

#### Security, Identity & Compliance
  * IAM (AWS Identity and Access management) - Securely congtrolling access to AWS service
  * Cognito - Simple and secure user sign up/Sign in
  * GuardDuty - Intelligent threat detection and continous monitoring to protect your AWS accounts and workloads
  * Inspector - Automated security accessment service to help improve the security and compliance of applications deployed on AWS
  * Amazon Macie - A machine learning-powered security service to discover, classiofy and protect sensitive data.
  * AWS single sign-on - Centrally manage single sign-on (SSO) access to multiple AWS accounts and business applications
  * Certificate Manager - Provision, manage and deploy SSL/TLS certificates
  * AWS CloudHSM - Managed hardware security module (HSM) on the AWS cloud
  * AWS Directory service - Managed microsoft Active Directory in the AWS Cloud
  * AWS WAF & Shield - Monitor web requests for Amazon CloudFront distributions and restrict access to your content
  * AWS Artifact - On-demand access to AWS's compliance reports

#### Mobile services
  * Mobile Hub - Tools that enable you tpo quickly configure AWS services and integrate them into your mobile app
  * Amazon Pinpoint - Track the ways in which users interact with your applications
  * AWS AppSync - Build Data Driven Apps with Realtime and offline capabilities
  * AWS Device Farm  - Test against real mobile devices in AWS cloud
  * Mobile Analytics - Measure app userage and app revenue

#### AR & VR
  * Amazon Sumerian - create VR, AR and 3D eperiences

#### Application Integration
  * Step Functions - Coordinage the components of distributed applications and microservices using visual workflows
  * Amaon MQ - Managedmessage broker service for Apache ActiveMQ
  * Simple Notification service( SNS) - pub/sub messaging
  * Simple Queue Service(SQS) - Fully managed message queues
  * Amazon Simple workflow service (SWF) Build, run and scale background jobs that have parallel or sequential steps

#### Customer Engagement
  * Amazon Connect - conmtact center as a service(CCaS)
  * Amazon Simple email Service (SES) - Email sending and receiving platform

#### Business Productivity
  * Alexa for Business - Empower your organization with Alexa
  * Amazon Chime - Communications service for online meetings
  * WorkDocs - Secure file collaboration and management
  * WorkMail - Managed business email and calendar services

#### Desktop & App Streaming
  * Amazon WorkSpaces - Fully managed secure virtual cloud desktops running onm AWS
  * AppStream 2.0 - Stream desktop applications to any device running a web browser

#### Internet of Things
  * AWS IoT - A system ubiquitous devices connecting the physical world to the cloud
  * IoT Device Management - Onboard, Orgamize, Monitor and remotely manage connected devices at scale
  * Amazon FreeRTOS - IoT operating system for microcontrollers
  * Amazon Greengrass - Local compute, messaging, datga caching, sync and ML inference capabilities for connected devices

#### Game Development
  * Amazon GameLift - Dedicated game server hosting