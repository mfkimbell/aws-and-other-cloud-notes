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

## Kinesis Data Streams

## Kinesis Data Firehose

## SQS ()

## SNS ()

## Eventbridge 


# Azure

## Azure Function 
* like lamda functions
* serverless
* compute on demand
* scalable
* support for multiple languages
