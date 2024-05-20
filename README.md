# Services I have worked with
* RDS (used postgres to manage user login information for serverless django webapp)
* Dynamo DB (aws amplify project storing of user comments)
* Amplify
* Fargate (serverless django, uses ECS to manage containers in a serverless fashion)
* EC2 (running various instances, mainly ubuntu, but also NGINX)
* S3 (storing of images in file sharing service) (storing of images in Amplify file sharing dashbaord)
* EKS (running kubernetes in both pipeline projects)
* KubeCTL (command line for eks for testing)
* ECS (used in django serverless webapp to deploy container in fargate task)
* ECR (serverless django pushing from local terminal manually)
* IAM (various roles made for permission purposes)
* 
* Not used SAM, but I've used Terraform, which is pretty similar. Azure's equivalent would be ARM.

  
<img width="646" alt="Screenshot 2024-05-20 at 1 08 02 PM" src="https://github.com/mfkimbell/aws-and-other-cloud-notes/assets/107063397/dbe26161-4597-4b36-9ec3-c9196134a104">

* Application Load Balancer: (serverless django app uses a load balancer -> Listener -> target group -> directs to port 8000 so it can communicate with docker containers deployed through ECS and fargate by extension). 
* Elastic Load Balancer (older/somewhat outdated)
* Network Load Balancer (Best suited for TCP, UDP, and TLS traffic. NLBs distribute traffic based on network conditions. For example, if you have multiple database servers with duplicate data, the NLB routes traffic based on predetermined server IP addresses or server availability.)
* Gateway Load Balancer (

# Spaceify
* EC2 instances all with docker installed all running different containers
* All instances were Ubuntu distributions
* NGINX acting as a reverse proxy to send to our backend endpoints as well as redirecting to our frontend. 
* container for NGINX, React, and FastAPI, we pulled the containers from dockerhub. We ran them on separate EC2s for performance sake since we were using the free tier.

# terraform-aws-DevOps
* AWS accessed via terraform (and some manually)
* Used Terraform to establish a VPC, subnets, and security groups, and to build the base EC2 servers for Jenkins-Master, Jenkins-BuildSlave, and Ansible



# AWS Lambda .NET video
* remember with AWS lambda on .NET, you have to install a couple modules
* there is a module that enables the publish (i'm pretty sure that's what we did) but the guy in the video does it programatically
https://www.youtube.com/watch?v=PTnWbKWm3uo&ab_channel=RahulNath
<img width="681" alt="Screenshot 2024-05-07 at 9 37 15 AM" src="https://github.com/mfkimbell/aws-and-other-cloud-notes/assets/107063397/9742d54a-f9ae-40ab-8865-91120ed10114">


# cloud-notes

<img width="693" alt="Screenshot 2024-04-03 at 7 17 08 PM" src="https://github.com/mfkimbell/cloud-notes/assets/107063397/4853e809-e16a-4025-a47e-5b7fa8b4dfcc">

SaaS: Slack
PaaS: Elastic beanstalk, Google App Engine, OpenShift
IaaS: AWS

# Ansible
* ssh on steroids
* No requirement for ansible agent on recieving VM


# aws-notes
aws-notes

AWS


# EC2

## Amazon Linux

```
ssh -i <path to pem>.pem ec2-user@<public IP>
```
ssh -i dpp.pem ec2-user@34.201.245.118

Becoming root: “sudo su -sh”

## Ubuntu
```
ssh -i <path to pem>.pem ubuntu@<public IP>
```

ssh -i pras-vivo-key-2.pem ubuntu@52.202.26.181


ssh -i dpp.pem ubuntu@52.202.26.181

Becoming root: “sudo su -“


scp -i /Users/mitchellkimbell/desktop/devops-files dpp.pem ubuntu@52.90.8.209:/opt/


ssh user-fqdn@LinuxBastion-fqdn -L 2222:52.90.8.209:22

## Serverless
* SAM, DynamoDB, Fargate, Lambda, 

## EC2
* SSH into Amazon Linux containers  ```ssh -i dpp.pem ec2-user@34.201.245.118```
* Becoming root Linux ```sudo su -sh```
* SSH into Ubuntu containers ```ssh -i dpp.pem ubuntu@52.202.26.181```
* Becoming root Ubuntu  ```sudo su -```

## ECR (elastic container registry)
* fully managed Docker container registry that makes it easy to store, share, and deploy container images.

## ECS (elastic container service)
* managed container service solution that's easy to use, scalable, secure, and reliable.
* kinda like kubernetes?

## WAF (web application firewall)
* 3 uses, api gateway, cloudfront, and a loadbalancer
* AWS WAF operates at the application layer, making decisions based on content of the HTTP/HTTPS requests, while security groups (virtual firewalls) operate at the network and transport layers, making decisions based on IP protocol data.
* AWS WAF provides protection against web exploits (SSL injection, XXS cross-site-scripting) and can be configured to understand the application-specific patterns and attacks, whereas security groups provide basic access control and are not aware of the application-specific details
* AWS WAF offers granular control over the HTTP and HTTPS traffic, allowing for complex rule sets based on the content of the traffic, while security groups offer broad control over general network access based on IPs and ports.
<img width="1169" alt="Screenshot 2024-05-06 at 2 53 56 PM" src="https://github.com/mfkimbell/aws-and-other-cloud-notes/assets/107063397/eecd2bc7-b11a-496c-94c2-ef5021ba79fd">

## Cloudwatch

AWS CloudWatch is a monitoring and observability service that provides data and actionable insights for AWS, hybrid, and on-premises applications and infrastructure resources. Here's an overview of how it works:

Key Components and Features
Metrics Collection

Default Metrics: CloudWatch automatically collects metrics from AWS services like EC2, RDS, S3, Lambda, and more.
Custom Metrics: Users can publish their own metrics using the AWS SDK, CloudWatch API, or the CloudWatch Agent.
Logs Monitoring

CloudWatch Logs: Collects and stores logs from AWS resources, applications, and services. You can use the CloudWatch Logs Agent to send log data from your instances.
Log Insights: Allows you to interactively search and analyze log data.
Alarms

Threshold-based Alarms: Set thresholds on metrics to trigger actions, such as sending notifications via SNS or triggering Auto Scaling actions.
Composite Alarms: Combine multiple alarms into a single alarm to reduce alarm noise and complexity.
Dashboards

Visualization: Create custom dashboards to visualize metrics and logs. Dashboards can include graphs, text, and other widgets to display real-time data.
Events

CloudWatch Events: Respond to changes in your AWS resources. For example, you can automatically trigger Lambda functions, send notifications, or take corrective actions based on events.
Anomaly Detection

Anomaly Detection: Uses machine learning to continuously analyze metrics and create models that predict normal behavior. Alerts are generated when anomalies are detected.

## Xray
* Helps developers analyze and debug distributed applications, such as those built using a microservices architecture. It provides end-to-end tracing of requests as they move through your application, enabling you to identify performance bottlenecks, errors, and other issues.
* End-to-End Tracing
Trace Requests: Tracks requests from the point they enter your application to when they exit, capturing data at each step along the way.
* Service Map: Visualizes the relationships between services in your application, showing how requests flow and where bottlenecks occur.
* Focuses on tracing and analyzing the flow of requests across a distributed system. It provides a high-level overview of application performance, service dependencies, and end-to-end request paths. X-Ray is designed to help identify bottlenecks, performance issues, and errors in complex, microservices-based applications.
* **CloudWatch Logs:** DIFFERENT, Primarily used for collecting and storing log data from AWS resources, applications, and services. It provides detailed, granular log information that can be used for troubleshooting, auditing, and log analysis. CloudWatch Logs helps with tracking events and debugging at the level of individual log entries.
* **AWS X-Ray:** Captures data at the level of individual requests and their interactions with various services and components. It provides insights into the structure and performance of distributed systems.
* **CloudWatch Logs:** Collects log entries that detail specific events, errors, and operational data. It provides a log-level view of what is happening within your applications and infrastructure.


## SAM (Serverless Application Model)
* Similar to Terraform, builds up Cloudformation YAML
* NOT SAML (Security Assertion Markup Language)
Security Assertion Markup Language (SAML) is an open standard for exchanging authentication and authorization data between parties, particularly between an identity provider and a service provider. Think Single Sign On (SSO). 
* The AWS Serverless Application Model (SAM) CLI is an open-source CLI tool that helps you develop serverless applications containing Lambda functions, Step Functions, API Gateway, EventBridge, SQS, SNS and more.
* AWS SAM templates provide a short-hand syntax, optimized for defining ```Infrastructure as Code (IaC)``` for serverless applications.

## API Gateway
* Used for HTTP, REST (CRUD), and Websocket connections (real time)
* HTTP and REST are for request and response model interactions
* REST is more advanced than HTTP, it can do things like integrate with authorizers for amazon cognito, work with web application firewalls, API keys with usage plans
* Websockets are more "bi-directional" so transactions or real-time chat
* BE CAREFUL, it has a 30 second integration (with other services) timeout (hard limit).
* 10MB payload size (hard limit)
 <img width="1227" alt="Screenshot 2024-05-06 at 3 15 36 PM" src="https://github.com/mfkimbell/aws-and-other-cloud-notes/assets/107063397/6d7b6900-142b-4065-b7d6-9a8ff8869572">

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
* **Subnet:**
* A subnet is a range of IP addresses in your VPC.
* You can create multiple subnets within a VPC, each associated with a specific Availability Zone.
* Subnets can be classified as either public or private based on their connectivity to the internet.

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









