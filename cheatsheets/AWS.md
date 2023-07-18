# AWS

## EC2
Amazon Elastic Compute Cloud

bietet skalierbare Rechenkapazität in der AWS Cloud

## EKS
Elastic Container Service for Kubernetes

## IAM
AWS Identity and Access Management (IAM)

## AWS Serverless
AWS offers technologies for running code, managing data and integrating applications all without managing servers.

This eliminates infrastructure management tasks like capacity provisioning and patching, so you can focus on writing code that serves your customers.

### Compute

#### AWS Lambda
AWS Lambda is a serverless, event-driven compute service that lets you run code for virtually any type of application or backend service without provisioning or managing servers. 

#### AWS Fargate
AWS Fargate is a serverless, pay-as-you-go compute engine that lets you focus on building applications without managing servers.

While Fargate is a Container as a Service (CaaS) offering, AWS Lambda is a Function as a Service (FaaS offering). 

### Application integration

#### Amazon EventBridge
Amazon EventBridge Event Bus is a serverless event bus that helps you receive, filter, transform, route, and deliver events.

#### Amazon SQS
Amazon Simple Queue Service (Amazon SQS) lets you send, store, and receive messages between software components at any volume, without losing messages or requiring other services to be available.

#### Amazon SNS
Amazon Simple Notification Service (Amazon SNS) sends notifications two ways, A2A and A2P. A2A provides high-throughput, push-based, many-to-many messaging between distributed systems, microservices, and event-driven serverless applications. These applications include Amazon Simple Queue Service (SQS), Amazon Kinesis Data Firehose, AWS Lambda, and other HTTPS endpoints. A2P functionality lets you send messages to your customers with SMS texts, push notifications, and email.
(archiving, retry, DLQ)
A2A = Application-To-Application
A2P = Application-To-Person (Push Notifications)

#### Amazon API Gateway 
is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as the "front door" for applications to access data, business logic, or functionality from your backend services. Using API Gateway, you can create RESTful APIs and WebSocket APIs that enable real-time two-way communication applications. API Gateway supports containerized and serverless workloads, as well as web applications.

API Gateway handles all the tasks involved in accepting and processing up to hundreds of thousands of concurrent API calls, including traffic management, CORS support, authorization and access control, throttling, monitoring, and API version management. API Gateway has no minimum fees or startup costs. You pay for the API calls you receive and the amount of data transferred out and, with the API Gateway tiered pricing model, you can reduce your cost as your API usage scales.

### Datastore

#### Amazon S3 -  Amazon Simple Storage Service 
is an object storage service designed to store and protect any amount of data. 

#### Amazon DynamoDB
is a key-value and document database service, delivering single-digit millisecond performance at any scale. 

#### Amazon Aurora Serverless
is a MySQL and PostgreSQL-compatible relational database that automatically scales capacity based on your application's needs. 

