### Security

#### KMS

* KMS stores the CMK, and receives data from the clients, which it encrypts and sends back

<img src="https://media.datacumulus.com/aws-dva-pt/assets/pt1-q14-i1.jpg" />

* Instead of creating individual policies for each user, you can use policy variables and create a single policy that applies to multiple users (a group policy). Policy variables act as placeholders. When you make a request to AWS, the placeholder is replaced by a value from the request when the policy is evaluated.

<img src="https://media.datacumulus.com/aws-dva-pt/assets/pt1-q40-i1.jpg">

#### Lambda

* An Amazon API Gateway Lambda authorizer (formerly known as a custom authorizer) is a Lambda function that you provide to control access to your API. A Lambda authorizer uses bearer token authentication strategies, such as OAuth or SAML. Before creating an API Gateway Lambda authorizer, you must first create the AWS Lambda function that implements the logic to authorize and, if necessary, to authenticate the caller.