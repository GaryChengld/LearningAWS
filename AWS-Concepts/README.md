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
