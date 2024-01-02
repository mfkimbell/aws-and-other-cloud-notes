# cloud-notes

# AWS

## Serverless
* SAM, DynamoDB, Fargate, Lambda, 

## EC2
* SSH into Amazon Linux containers  ```ssh -i dpp.pem ec2-user@34.201.245.118```
* Becoming root Linux ```sudo su -sh```
* SSH into Ubuntu containers ```ssh -i dpp.pem ubuntu@52.202.26.181```
* Becoming root Ubuntu  ```sudo su -```

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
* AWS equivalent of Kubernetes




  
# Azure

## Azure Function 
* like lamda functions
* serverless
* compute on demand
* scalable
* support for multiple languages
