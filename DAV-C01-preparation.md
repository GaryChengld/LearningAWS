#### [Security](#Security)
#### [Deployment](#Deployment)

### Security

[Security Best Practices for Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/security-best-practices.html)

#### IAM

* IAM Access Analyzer - AWS IAM Access Analyzer helps you identify the resources in your organization and accounts, such as Amazon S3 buckets or IAM roles, that are shared with an external entity. This lets you identify unintended access to your resources and data, which is a security risk.\
You can set the scope for the analyzer to an organization or an AWS account. This is your zone of trust. The analyzer scans all of the supported resources within your zone of trust. When Access Analyzer finds a policy that allows access to a resource from outside of your zone of trust, it generates an active finding.

* Access Advisor feature on IAM console - To help identify the unused roles, IAM reports the last-used timestamp that represents when a role was last used to make an AWS request. Your security team can use this information to identify, analyze, and then confidently remove unused roles. This helps improve the security posture of your AWS environments. This does not provide information about non-IAM entities such as S3


#### KMS

* KMS stores the CMK, and receives data from the clients, which it encrypts and sends back
<img src="https://media.datacumulus.com/aws-dva-pt/assets/pt1-q14-i1.jpg" />

#### Policy

* Instead of creating individual policies for each user, you can use policy variables and create a single policy that applies to multiple users (a group policy). Policy variables act as placeholders. When you make a request to AWS, the placeholder is replaced by a value from the request when the policy is evaluated.
<img src="https://media.datacumulus.com/aws-dva-pt/assets/pt1-q40-i1.jpg">

#### S3

* Protecting data using server-side encryption
  * Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3)
  * Server-Side Encryption with Customer Master Keys (CMKs) Stored in AWS Key Management Service (SSE-KMS)
  * Server-Side Encryption with Customer-Provided Keys (SSE-C)
<img src="https://media.datacumulus.com/aws-dva-pt/assets/pt1-q8-i1.jpg">

#### Lambda

* An Amazon API Gateway Lambda authorizer (formerly known as a custom authorizer) is a Lambda function that you provide to control access to your API. A Lambda authorizer uses bearer token authentication strategies, such as OAuth or SAML. Before creating an API Gateway Lambda authorizer, you must first create the AWS Lambda function that implements the logic to a

#### Cognito

* After successful authentication, Amazon Cognito returns user pool tokens to your app. You can use the tokens to grant your users access to your own server-side resources, or to the Amazon API Gateway.\
Amazon Cognito user pools implement ID, access, and refresh tokens as defined by the OpenID Connect (OIDC) open standard.\
The ID token is a JSON Web Token (JWT) that contains claims about the identity of the authenticated user such as name, email, and phone_number. You can use this identity information inside your application. The ID token can also be used to authenticate users against your resource servers or server applications.
<img src="https://media.datacumulus.com/aws-dva-pt/assets/pt1-q53-i1.jpg">

### Deployment

#### EC2

* Differences between Dedicated Hosts and Dedicated Instances
  * Dedicated Instances are Amazon EC2 instances that run in a virtual private cloud (VPC) on hardware that's dedicated to a single customer. Dedicated Instances that belong to different AWS accounts are physically isolated at a hardware level, even if those accounts are linked to a single-payer account. However, Dedicated Instances may share hardware with other instances from the same AWS account that are not Dedicated Instances.
  * A Dedicated Host is also a physical server that's dedicated for your use. With a Dedicated Host, you have visibility and control over how instances are placed on the server.
<img src="https://media.datacumulus.com/aws-dva-pt/assets/pt1-q21-i1.jpg">