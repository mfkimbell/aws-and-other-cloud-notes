# cloud-notes

<img width="693" alt="Screenshot 2024-04-03 at 7 17 08 PM" src="https://github.com/mfkimbell/cloud-notes/assets/107063397/4853e809-e16a-4025-a47e-5b7fa8b4dfcc">

SaaS: Slack
PaaS: Elastic beanstalk, Google App Engine, OpenShift
IaaS: AWS

# Ansible
* ssh on steroids

# AWS

## Serverless
* SAM, DynamoDB, Fargate, Lambda, 

## EC2
* SSH into Amazon Linux containers  ```ssh -i dpp.pem ec2-user@34.201.245.118```
* Becoming root Linux ```sudo su -sh```
* SSH into Ubuntu containers ```ssh -i dpp.pem ubuntu@52.202.26.181```
* Becoming root Ubuntu  ```sudo su -```

## ECR
* fully managed Docker container registry that makes it easy to store, share, and deploy container images.

## ECS 
* managed container service solution that's easy to use, scalable, secure, and reliable.
* kinda like kubernetes?

## SAM (Serverless Application Model)
* The AWS Serverless Application Model (SAM) CLI is an open-source CLI tool that helps you develop serverless applications containing Lambda functions, Step Functions, API Gateway, EventBridge, SQS, SNS and more.
* AWS SAM templates provide a short-hand syntax, optimized for defining ```Infrastructure as Code (IaC)``` for serverless applications.

## Lambda

Why use lambda functions?
* billed by invocation, don't have to keep an EC2 server running
* scale automatically based on traffic
* its serverless
* supports multiple languages
  
What are some useful examples?
* create resources
* respond to event triggers
* redirect data

## Lambda Step functions
* Visual Workflow for lambda functions
* Can manage application logic
* Use declarative writiing to specify what to do, how many times to retry, where to go on failure, etc
*  Step Functions can be used to coordinate the execution of microservices within a distributed application. It helps manage the flow of data and activities between different microservices.
*  Workflow Automation: You can use Step Functions to automate and orchestrate repetitive tasks and workflows, reducing manual intervention and improving operational efficiency.
*  State Machines for Serverless Applications: When building serverless applications, Step Functions can define the logic and coordination between various AWS Lambda functions, enabling a serverless architecture without the need for a centralized coordinator.

## RDS
* PostgreSQL, MariaDB, MySQL, and Oracle

## DynamoDB
* Amazon DynamoDB Accelerator (DAX) is a fully managed, highly available, in-memory cache for DynamoDB that delivers up to a 10x performance improvement. Improves performance from milliseconds to microseconds, even at millions of requests per second.
* NoSQL service
* Serverless

## Elasticache
* Redis: more data types
* Memcached: only key value pairs
* Redis: Offers persistence options, allowing you to save data to disk for durability. It supports both snapshots and append-only files. This can be useful for scenarios where data needs to be retained even if the entire cache is restarted.
* Memcached: Does not provide native persistence. All data is stored in memory, and if the cache is restarted, the data is lost.

## Amazon Aurora
* a distributed storage system that makes it 3-5 times faster than MySQL or Postgres

## S3
* storage tiers
* for storing BIG files
![1_PZryXkcXoVj99unK-XNqUA](https://github.com/mfkimbell/cloud-notes/assets/107063397/b55b18de-fbb3-4ffc-96c7-06dc342f8de6)

## VPC (Virtual Private Cloud)
* consists of public and private subnets
* ```Routing table``` for each subnet to map IP endpoints
* Private subnets can use a ```NAT Gateway``` to connect to the internet

## Cloudfront
* Amazon CloudFront, AWS's content delivery network (CDN) service, uses a network of distributed ```edge locations to cache and deliver content closer to end-users```. These edge locations are strategically positioned around the world to reduce latency and improve the performance of content delivery.

## Cognito User Pools
* Authentication – provides users sign-up and sign-in options. Enables support for federation with Enterprise Identities (Microsoft AD), or Social Identities (Amazon, Facebook, Google, etc.)
Authorization – sets of permission or operations allowed for a user. It provides fine-grained access control to resources. 
User Management – allows management of user lifecycles, such as importing users, onboarding users, disabling users, and storing and managing user profiles.
* Cognito allows for people to login using federated identities like Google and Facebook
  
## Cognito Identity Pools
* Same use of federated entities like Google and Facebook, but its about `access to AWS Resouces`, not login to an application

## Kinesis Data Streams
* Amazon Kinesis Data Streams (KDS) is a service that captures streaming data in real-time from various data sources. KDS can be used to collect and process large streams of data records in real time
* Use Cases: Video streaming, live leaderboards, live security monitoring, passing in data for Machine Learning

## Kinesis Data Firehose
* Captures, transforms, and delivers stream data to data lakes (s3), data stores (for structured data, like Redshift), and analyitical servies
* It does batching, compressing, encrypting and loading stream data to Redshift, S3, Elastisearch, and Kinesis Analytics

## AWS Key Management Service (KMS)
-customer managed keys (CMK)
-AWS managed keys
<img width="796" alt="Screenshot 2024-04-10 at 12 41 53 PM" src="https://github.com/mfkimbell/cloud-notes/assets/107063397/aa71e19c-a3ef-4744-bb92-380a1c976fcb">

## Elasticsearch
* `Opensearch` Opensource community version
* `Distributed` search and analytics engine,
* Use Cases: Real-Time logging analytics/monitoring, "full text search" searching for instances of fraud or security ecommerce search

## SQS Simple Queue Service
*  It enables decoupling of the components of a cloud application by allowing them to communicate asynchronously.
*  SQS acts as a distributed message queue that enables different components or microservices to communicate and coordinate tasks without direct coupling.

## SNS Simple Notification Service
* It enables the distribution of messages or notifications to a distributed set of subscribers via different delivery protocols.
* SNS follows a publish-subscribe (pub-sub) messaging model, allowing publishers to send messages to topics, and subscribers to receive messages from topics.
* Topic-based Structure: Messages are sent to topics, which act as communication channels. Subscribers can subscribe to one or more topics to receive the messages they are interested in.
* Fanout: SNS supports fanout, meaning a single message can be delivered to multiple subscribers simultaneously. This is useful for broadcasting messages to multiple recipients.

## Eventbridge 
* Event Bus: EventBridge uses an event bus to accept and deliver events. An event bus collects and routes events from different sources to different targets. You can use the default event bus or create custom event buses for specific use cases.

## AWS Amplify	
* Build, deploy, host, and manage scalable web and mobile apps

## AWS AppSync	
* Accelerate app development with fully-managed, scalable GraphQL APIs

## AWS Cloud Development Kit (CDK)	
* Model cloud infrastructure using code
* IAC but with familiar languages like Python Java Etc...


## AWS CloudFormation	
* Create and manage resources with templates
* IAC more SIMILAR to terraform, uses YAML


## Elastic Beanstalk
* AWS Elastic Beanstalk is a PaaS solution for deploying and managing applications with a focus on web servers and APIs
* Elastic Beanstalk automatically handles the deployment, from capacity provisioning, load balancing, auto-scaling to application health monitoring based on the code you upload to it, where as CloudFormation is an automated provisioning engine designed to deploy entire cloud environments via a JSON script.
* Elastic beanstalk holds your hands a lot more

## AWS Cloud9	
* Write, run, and debug code on a cloud IDE
* Cloud based IDE like VSCode

## AWS CloudTrail	
* Track user activity and API usage

## AWS CodeBuild	
* Build and test code	Developer Tools
* fully managed build service that compiles source code, runs tests, and produces ready-to-deploy software artifacts.
* It is used for automating the build and test phases of the continuous integration and continuous delivery (CI/CD) pipeline.
* Infrastructure as Code (IaC): CodeBuild allows you to define build specifications using a buildspec file written in YAML. This file can include build commands, environment variables, and settings needed for the build process.
* Integration with CI/CD: CodeBuild seamlessly integrates with other AWS services, including AWS CodePipeline, AWS CodeCommit, and AWS CodeDeploy. It can be a crucial part of a CI/CD workflow, where it compiles and tests code changes automatically.
## AWS CodeCommit	
* Store code in private Git repositories	Developer Tools
* Like Github
## AWS CodeDeploy	
* Automate code deployments	Developer Tools
* Deployment Automation: AWS CodeDeploy is a deployment service that automates the deployment of applications to Amazon EC2 instances, on-premises instances, or serverless compute services like AWS Lambda.
* Deployment Strategies: CodeDeploy supports various deployment strategies, including in-place deployments, blue/green deployments, and canary deployments. These strategies allow you to control how new versions of your application are rolled out and tested.

## AWS CodePipeline	
* Release software using continuous delivery
* AWS CodePipeline is a fully managed continuous integration and continuous delivery (CI/CD) service provided by Amazon Web Services (AWS).
* It helps automate the release process for software applications by orchestrating the building, testing, and deployment of code changes.
* AWS CodePipeline is often used in conjunction with other AWS services, such as AWS CodeBuild and AWS CodeDeploy, to create end-to-end CI/CD pipelines. Here's how CodePipeline relates to other services like CodeBuild and CodeDeploy:

## AWS Copilot
* CLI container management
* AWS Copilot is a command line interface that lets you develop, release, and operate containerized applications on AWS.

## X-Ray Tracing
* XRAY Daemon can be installed locally, so a question si like, why is it working locally and not on AWS, there might be IAM permissions missing, or you Arne’t running the daemon on AWS EC2
* For lambda, all you need is an IAM execute role with correct policy, x-ray code imported, and enable Lambda X-ray “active tracing”
* X-ray annotations, have indexing and filters for searching

<img width="429" alt="Screenshot 2024-01-02 at 1 07 52 PM" src="https://github.com/mfkimbell/cloud-notes/assets/107063397/66a326cf-8676-473a-b9cb-dd9a321bed40">

## Route53
<img width="439" alt="Screenshot 2024-01-07 at 10 17 51 AM" src="https://github.com/mfkimbell/cloud-notes/assets/107063397/9f63b265-cefc-4f93-b6a5-0f958650e7e8">


We have lambda execution roles (lambda function doing stuff)
And we have Lambda resource policies (other stuff calling that function)

  * NACLs are stateless, which means that information about previously sent or received traffic is not saved. If, for example, you create a NACL rule to allow specific inbound traffic to a subnet, responses to that traffic are not automatically allowed. This is in contrast to how security groups work. Security groups are stateful, which means that information about previously sent or received traffic is saved. If, for example, a security group allows inbound traffic to an EC2 instance, responses are automatically allowed regardless of outbound security group rules

SSE-C encryption (storing keys client side, but encryptiion through )
Is only available through CLI



Dedicated Instance, WHILE YOU ARE USING the instance, no other accounts can be using it

Dedicated Host, ALWAYS it will belong to you, you practically rent a hotel room all year


SSE-S3 (default)
SSE- (can edit keys through , not automatic through amazon, but also not client side)



# Azure

(compute)

## Azure VM (aws EC2)
* instance types = VM series
* elastic block stoarge = azure disk: persistent storage volumes for your VM
* Script, aws user-data = azure custom-data: scripts that are run on the startup of your VM
* Secuirty groups, AWS Security group = Azure NIC Network Security Group
* Autoscaling, Azure VM Scale Sets = AWS Autoscaling: increase number of resources as needed

## Azure VNet (aws VPC)
* Secure your network using, Azure NSGs and ASGs = AWS NACLs and Security Groups

## Azure DNS (AWS Route 53)

## Azure Container Instances (AWS ECS & Fargate)
* run containerized applications without managing servers (serverless)

## Azure Container Registry (AWS ECR)

## Azure Kubernetes Service (AWS EKS)

## Azure Blob (AWS S3)
* Blob storage resources: Storage Account, Container, and Blob
* Replication, Azure Object Replication = AWS Cross Region Replication
* Static Website Cache, Azure CDN = AWS Cloudfront: cache content from a static website
  
## Azure SSE (aws KMS)
* Does data encryption
  
## Azure Key Vault (AWS KMS)
* Stores keys, secrets, and certificaitons

  
## Azure Files (AWS EFS)

## Azure Databox (AWS Snow Family/snowball)
* transfer petabytes and exabytes of data to the cloud.

## Azure Function (aws lambda)
* like lamda functions
* serverless
* compute on demand
* scalable
* support for multiple languages

## Azure SQL (AWS RDS)
* fully scalable relational databse in the cloud
* Azure SQL Database serverless (aws Aurora Serverless): just a serverless database
* High availability, Azure zone redundant configuration (aws Multi-Zone Deployment)
* Secondary DB, Azure active geo-replication = AWS Read Replicas

## Azure App Service (elastic beanstalk)

## CosmosDB (aws dynamodb)

## Azure AD - Active Directory (aws IAM)

## Azure Frontdoor (aws cloudfront)

## Azure Monitor (aws cloudwatch)


<img width="1272" alt="Screenshot 2024-04-10 at 12 25 44 PM" src="https://github.com/mfkimbell/cloud-notes/assets/107063397/31f97365-4f9f-444a-b9ff-4d62d24696ef">

## Azure Event Grid (aws eventbridge)

## Azure Event Hub (aws kinesis)

## Azure Service Bus (aws Event Bridge service bus or SQS+SNS)


## Azure Notification Hub (aws SNS)

## Azure Storage Queue (aws SQS)





