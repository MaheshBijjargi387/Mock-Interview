# What is EC2?
->EC2 is an AWS service that provides resizable virtual servers in the cloud. We can use these servers to deploy and run applications.

# Is EC2 a physical server?
->No. EC2 provides virtual servers that run on AWS infrastructure.

# What is an AMI? AMI (Amazon Machine Image)
->AMI is a template that contains the operating system and configurations needed to create an EC2 instance.

# What is an EC2 instance type?
->An EC2 instance type defines the hardware resources allocated to an EC2 instance, such as CPU, memory, networking, and sometimes storage performance. We choose an instance type based on the requirements of our application.

# What is a key pair in AWS EC2?
->A key pair is a security mechanism used to securely connect to an EC2 instance. It consists of a public key, which AWS stores on the instance, and a private key, which the user keeps securely and uses for authentication.

# What is a Security Group in AWS?
->A Security Group is a virtual firewall in AWS that controls inbound and outbound traffic to resources like EC2 instances.

# What is the difference between public and private IP in AWS?
->A public IP is used for communication between an AWS resource and the internet, while a private IP is used for communication within the private network, such as between EC2 instances and databases in the same VPC.

# What is a VPC?
->VPC, or Virtual Private Cloud, is a logically isolated virtual network in AWS where we can launch and manage resources such as EC2 instances. It allows us to control IP addressing, subnets, routing, and network security.

# What is a subnet in AWS?
->A subnet is a logical subdivision of a VPC's IP address range. It is used to organize resources within the VPC and control their network connectivity. Subnets can be configured as public or private based on their routing.

# What is an Internet Gateway in AWS?
->An Internet Gateway is a VPC component that provides a path for communication between resources in a VPC and the internet. It is commonly used with public subnets to provide internet connectivity to resources such as EC2 instances.

# What is a Route Table in AWS?
->A Route Table is a set of rules that controls where network traffic from a subnet should go.

# What is a NAT Gateway in AWS?
->A NAT Gateway allows resources in a private subnet to access the internet, but the internet cannot directly access those resources.

# What is an Availability Zone in AWS?
->An Availability Zone is an isolated location within an AWS Region that contains one or more data centers. Multiple Availability Zones are used to build highly available and fault-tolerant applications.

# What is an AWS Region?
->An AWS Region is a geographic area that contains multiple isolated Availability Zones. We choose a Region based on factors such as latency, compliance requirements, availability, and cost.

# What is an Elastic IP in AWS?
->An Elastic IP is a static public IPv4 address provided by AWS that can be associated with an EC2 instance or other supported resource. It allows the application to maintain a stable public IP address even when the underlying instance is stopped and started.

# What is EBS in AWS?
->EBS is a block storage service in AWS that provides persistent storage for EC2 instances.

# What is Amazon S3?
->Amazon S3, or Simple Storage Service, is a highly scalable object storage service used to store and retrieve data such as images, videos, documents, backups, and application files. Data in S3 is stored as objects inside buckets.

# What is an S3 bucket?
->An S3 bucket is a container used to store objects in Amazon S3.

# What is an S3 object?
->An S3 object is the actual data stored in a bucket, such as an image, document, video, or backup, along with its metadata and unique key.

S3 is an AWS object storage service. A bucket is a container within S3 used to store objects, and an object is the actual data or file stored inside the bucket.

# What are S3 storage classes?
->S3 Storage Classes are different storage options designed for different access patterns and costs.

# What is IAM in AWS?
->IAM, or Identity and Access Management, is an AWS service used to securely control access to AWS resources. It allows us to manage identities and define permissions using users, groups, roles, and policies.

# What is the difference between an IAM User and an IAM Role?
->An IAM User is mainly used to represent a person, while an IAM Role is used to provide temporary permissions to users, applications, or AWS services.

# What is an IAM Policy?
->An IAM Policy is a JSON-based permission document that defines which actions are allowed or denied on specific AWS resources. Policies can be attached to IAM users, groups, or roles.

# What is an IAM Group?
->An IAM Group is a collection of IAM users that allows us to manage permissions for multiple users collectively. Instead of attaching the same policies to individual users, we can attach policies to the group and assign users to it.

# What is the difference between an IAM Role and an IAM Policy?
->An IAM Policy defines the permissions, such as which actions are allowed or denied on specific AWS resources. An IAM Role is an identity that can be assumed by a trusted entity and has policies attached to define what permissions it receives.

# What is AWS CLI?
->AWS CLI is a command-line tool that allows users and applications to interact with AWS services by executing commands from a terminal. It communicates with AWS through APIs and can be used to create, manage, and monitor AWS resources.

# What is AWS SDK?
->AWS SDK is a set of libraries and tools that allows developers to integrate AWS services directly into their applications. For example, the AWS SDK for Java can be used by a Java or Spring Boot application to upload files to S3 or interact with other AWS services.

# What is Amazon RDS?
->Amazon RDS is a managed relational database service that makes it easier to set up, operate, and scale relational databases in AWS. It supports database engines such as MySQL and PostgreSQL, and provides features such as automated backups, patching, and high-availability options.

# What is the difference between MySQL on EC2 and RDS MySQL?
->With MySQL on EC2, we manage the server, operating system, database installation, configuration, backups, and maintenance ourselves. With Amazon RDS for MySQL, AWS manages much of the underlying database infrastructure and provides features such as automated backups, patching, monitoring, and high-availability options.

# What is a Load Balancer?
->A load balancer distributes incoming network traffic across multiple backend targets, such as EC2 instances. It helps improve application availability, scalability, and reliability, and can use health checks to route traffic away from unhealthy targets.

# What is Auto Scaling in AWS?
->Auto Scaling automatically adjusts the number of EC2 instances based on configured scaling policies and application demand. It helps maintain application availability during increased traffic and can reduce unnecessary resource usage when demand decreases.

 # What is Amazon CloudWatch?
->Amazon CloudWatch is a monitoring service in AWS used to monitor resources, applications, logs, and performance.

# What is Amazon CloudFront?
->Amazon CloudFront is a content delivery network service from AWS that delivers content faster by caching it at locations close to users.

# What is Amazon ECR?
->Amazon ECR, or Elastic Container Registry, is a fully managed AWS container registry used to store, manage, and deploy Docker container images. It integrates with AWS services such as ECS, EKS, and EC2.

# What is Amazon ECS?
->Amazon ECS, or Elastic Container Service, is a managed container orchestration service used to deploy, run, and manage containerized applications on AWS. It supports running containers using AWS Fargate or EC2-based compute.

# What is the difference between EC2 and ECS?
->EC2 is a cloud-based virtual server where we manage the operating system and software environment. ECS is a managed container orchestration service used to deploy and manage containerized applications. ECS can run containers using either AWS Fargate or EC2-based infrastructure.

# What is Amazon EKS?
->Amazon EKS is a managed Kubernetes service provided by AWS. It allows us to deploy, manage, and scale containerized applications using Kubernetes without managing the Kubernetes control plane ourselves.

# What is the difference between ECS and EKS?
->ECS is AWS's native container orchestration service, while EKS is AWS's managed Kubernetes service. ECS is generally simpler for AWS-specific container deployments, whereas EKS is useful when we need Kubernetes and its ecosystem.

# What is AWS Fargate?
->Fargate is a serverless compute engine for containers that allows us to run containers without managing the underlying EC2 servers. It works with services such as ECS and EKS.

# How would you deploy a Dockerized Spring Boot application on AWS ECS Fargate?
->First, I create a Docker image for the Spring Boot application. Then I push the image to Amazon ECR. After that, I create an ECS task definition referencing the ECR image and configure CPU, memory, port, and networking. Finally, I create an ECS service using Fargate to run and maintain the required number of container tasks. A load balancer can be used to expose the application and distribute traffic.

# What is the difference between ECS Cluster, Task Definition, Task, and Service?
->An ECS Cluster is a logical grouping for ECS resources. A Task Definition is the blueprint that defines how a container should run. A Task is a running instance created from that definition. An ECS Service manages the desired number of tasks and replaces failed tasks when necessary.

# What is the difference between an ECS Task and a Docker Container?
->A Docker container is a running instance of a Docker image, while an ECS Task is the unit used by ECS to run one or more containers according to a Task Definition.

# What is the difference between a Dockerfile and an ECS Task Definition?
->A Dockerfile contains instructions for building a Docker image, while an ECS Task Definition defines how ECS should run that container, including the image, CPU, memory, ports, environment variables, and other runtime settings.

# How does a Load Balancer work with ECS?
->An Application Load Balancer receives incoming HTTP or HTTPS requests and distributes them across healthy ECS tasks. The ECS Service maintains the desired number of tasks, and the load balancer performs health checks so traffic is sent only to healthy targets.

# What is a Target Group in AWS?
->A Target Group is a collection of backend targets that a Load Balancer routes traffic to. It also performs health checks on those targets and helps the Load Balancer send traffic only to healthy targets.

# What is an ALB Listener?
->A listener is a component of an Application Load Balancer that listens for incoming traffic on a configured protocol and port, such as HTTP on port 80 or HTTPS on port 443, and uses listener rules to forward requests to the appropriate target group.

# What is a health check in a Load Balancer?
->A health check periodically tests whether a backend target is available and healthy. If a target fails the configured health checks, the Load Balancer stops sending traffic to that target until it becomes healthy again.

# What is ECS Auto Scaling?
->ECS Auto Scaling automatically adjusts the desired number of ECS tasks based on application demand and configured scaling policies. It can use metrics such as CPU, memory, or request count to scale the application up or down.

# What is AWS Lambda?
->AWS Lambda is a serverless compute service that runs code in response to events without requiring us to manage the underlying servers. It is commonly used for event-driven applications and short-running tasks.

# What is Amazon API Gateway?
->API Gateway is a managed AWS service used to create, publish, secure, monitor, and manage APIs. It can receive client requests and route them to services such as Lambda or backend applications.

# What is the difference between API Gateway and ALB?
->ALB is primarily used to distribute application traffic across healthy backend targets, while API Gateway is designed to expose and manage APIs and provides features such as API routing, throttling, and authorization integration. ALB is commonly used with EC2 or ECS, while API Gateway is commonly used with Lambda and serverless architectures.

# What is DynamoDB?
->DynamoDB is a fully managed, serverless NoSQL database service provided by AWS. It is designed for high scalability and low-latency access and stores data as items and attributes using a key-based data model.

# What is the difference between RDS and DynamoDB?
->RDS is a managed relational database service that supports relational database engines such as MySQL and PostgreSQL and uses SQL. DynamoDB is a managed NoSQL database designed for highly scalable, low-latency key-based access. The choice depends on the application's data model and access patterns.

# What is Amazon SQS?
->Amazon SQS is a managed message queuing service used to decouple applications and microservices. A producer sends messages to the queue, and a consumer processes them asynchronously. This improves reliability because the producer and consumer don't need to be available at the same time.

# What is SQS Visibility Timeout?
->Visibility Timeout is the period during which an SQS message becomes temporarily invisible to other consumers after a consumer receives it. If the consumer successfully processes the message, it deletes it. If processing fails and the message isn't deleted, it becomes visible again after the visibility timeout.

# What is an SQS Dead-Letter Queue?
->A Dead-Letter Queue is a separate SQS queue used to store messages that cannot be successfully processed after a configured number of delivery attempts. It helps isolate failed messages, prevent repeated retries, and troubleshoot processing failures.

# What is Amazon SNS?
->Amazon SNS is a managed publish/subscribe messaging service. A publisher sends a message to an SNS topic, and the topic can deliver that message to multiple subscribers such as SQS queues, Lambda functions, HTTP endpoints, or supported notification endpoints.

# What is AWS Secrets Manager?
->AWS Secrets Manager is a managed service used to securely store, retrieve, and manage sensitive information such as database credentials, API keys, and application secrets. It also supports secret rotation for supported use cases.

# What is AWS Parameter Store?
->AWS Systems Manager Parameter Store is a service used to centrally store and manage configuration parameters such as application settings, URLs, and environment-specific values. It can also store encrypted parameters using SecureString.

# When would you use Secrets Manager instead of Parameter Store?
->I would generally use Secrets Manager when I need dedicated secret management features such as credential handling and secret rotation. I would use Parameter Store for application configuration and parameters, especially when advanced secret-management features aren't required.

# What is AWS KMS?
->AWS Key Management Service is a managed service used to create and control cryptographic keys and perform encryption-related operations. AWS services such as S3 and Secrets Manager can use KMS keys to protect data.

# What is Amazon Route 53?
->Amazon Route 53 is a highly available and scalable AWS DNS service used for domain registration, DNS resolution, health checks, and routing traffic to resources such as load balancers.

# What is AWS Certificate Manager?
->AWS Certificate Manager is a managed service used to provision, manage, and deploy SSL/TLS certificates for securing applications with HTTPS. For example, an ACM certificate can be attached to an HTTPS listener on an Application Load Balancer.

# What is AWS CloudFormation?
->AWS CloudFormation is an Infrastructure as Code service that allows us to define and provision AWS resources using templates. It helps automate and consistently create infrastructure such as VPCs, EC2 instances, S3 buckets, and databases.

# "How would you deploy a Spring Boot application using AWS?"
->I would containerize the Spring Boot application using Docker and push the image to Amazon ECR. Then I would run the container using ECS with Fargate. I would use an Application Load Balancer to distribute traffic to the ECS tasks. Route 53 would handle the domain, ACM would provide the HTTPS certificate, and RDS could be used for the relational database. S3 could be used for file storage, while Secrets Manager would securely store sensitive credentials.

# "How would you implement CI/CD for a Dockerized Spring Boot application on AWS?"
->I would use GitHub Actions for CI/CD. When code is pushed to GitHub, the pipeline would build and test the Spring Boot application, create a Docker image, authenticate with AWS, and push the image to Amazon ECR. Then the ECS service running on Fargate would deploy the new image. An Application Load Balancer would distribute traffic to the running tasks.

# Your Spring Boot application running on ECS needs to upload images to S3. How would you provide AWS permissions?
->I would create an IAM role for the ECS task and attach a policy that provides only the required S3 permissions. The application would use the task role instead of storing AWS access keys in the source code.

# AWS IAM security best practices include following least privilege, using IAM roles instead of long-term access keys for AWS workloads, enabling MFA, protecting the root user, avoiding hardcoded credentials, and regularly reviewing permissions.

# You have a Spring Boot application running on your local machine. Your company wants to deploy it to AWS. How would you deploy it?
->First, I would containerize the Spring Boot application using Docker. I would build the Docker image and push it to Amazon ECR. Then I would create an ECS service using Fargate to run the container. I would use an Application Load Balancer to receive and distribute traffic to the ECS tasks. Route 53 can be used for the domain, ACM for HTTPS, and RDS for the relational database. I would use IAM roles and Secrets Manager to securely provide required permissions and credentials.

# Your Spring Boot application normally gets 1,000 requests per minute, but suddenly traffic increases to 10,000 requests per minute. What would you do?
->I would first monitor the application using CloudWatch to identify CPU, memory, request count, and other relevant metrics. I would use an Application Load Balancer to distribute traffic across multiple ECS tasks, and configure ECS Auto Scaling to automatically increase the number of tasks based on demand. I would also check the database performance and scale or optimize RDS if it becomes the bottleneck.

# Your Spring Boot application is running on ECS, but users are getting 503 Service Unavailable from the Application Load Balancer. How would you troubleshoot it?
->I would not immediately restart the application. I would trace the request from ALB to the target group and ECS task. I would check target health, health-check configuration, port mappings, security groups, ECS task status, and CloudWatch logs to identify the root cause.

# Your Spring Boot application is running on ECS, but it cannot connect to RDS. What will you do?
->First, I will check whether the RDS database is running and whether the database details like host, port, username, and password are correct. Then I will check the security groups and network configuration to make sure ECS is allowed to connect to RDS. Finally, I will check the application logs to find the exact connection error.

# Your database is becoming slow. What will you do?
->First, I will check the database performance and CloudWatch metrics. Then I will check slow queries, CPU usage, memory, and database connections. I will optimize the slow queries and indexes. If the database still cannot handle the load, I will consider scaling the RDS instance.

# Your ECS container is continuously crashing. What will you do?
->First, I will check the ECS task status and CloudWatch logs to find the error. Then I will check the application configuration, environment variables, memory, and database connection. After finding the root cause, I will fix it and redeploy the container.

# Your application is working, but users are getting slow responses. What will you do?
->First, I will check CloudWatch metrics and application logs to find where the delay is happening. Then I will check the application, database, and network performance. If the application is overloaded, I will scale the ECS tasks. If the database is slow, I will optimize the queries or scale the RDS instance.


# Your application is working, but after deployment users are getting errors. What will you do?
->First, I will check the application logs and CloudWatch to find the error. Then I will compare the new deployment with the previous version and check the configuration, environment variables, and database connection. If the new version is causing the problem, I will roll back to the previous working version.


# Your application needs to store user profile images. Where would you store them in AWS?
->I would store the images in Amazon S3 because S3 is designed for storing files and objects. I would store the image in an S3 bucket and save its URL or key in the database.

# Your application needs to store database passwords securely. What would you use?
->I would use AWS Secrets Manager to store the database password securely. The application can access the secret using an IAM role instead of storing the password directly in the code.

# Your application needs to send an email when a new order is created. How would you design it?
->I would use Amazon SNS to publish an order-created message. An email service can receive that message and send the email. This keeps the order service separate from the email service and allows them to work independently.

# Your order service is sending requests directly to the email service, but the email service is temporarily down. What would you do?
->I would use Amazon SQS between the services. The order service sends the message to the queue, and the email service processes it when it is available. This prevents the order service from failing when the email service is down.

# A message in your SQS queue is failing repeatedly. What would you do?
->I would configure a Dead-Letter Queue. After the message fails a certain number of times, SQS moves it to the DLQ. Then I can check the failed message and find the reason for the failure.

# A developer accidentally deleted an important EC2 instance. How would you find out who deleted it?
->I would check AWS CloudTrail. CloudTrail records AWS API activities, so I can find who performed the delete action, when it happened, and which resource was affected.

# Your application needs to access an S3 bucket from ECS. How would you give it permission?
->I would create an IAM role for the ECS task and attach a policy with the required S3 permissions. The application can then access S3 through the IAM role without storing AWS access keys in the code.

# Your application needs to run a small piece of code whenever a file is uploaded to S3. What would you use?
->I would use AWS Lambda. I can configure S3 to trigger the Lambda function whenever a new file is uploaded. Lambda will then automatically run the required code without managing a server.

# Your application has many users, and you want to automatically run more containers when traffic increases. What would you use?
->I would use ECS Auto Scaling. It can automatically increase or decrease the number of ECS tasks based on application demand, such as CPU or memory usage.


# Your company wants to make sure users always access your application using HTTPS. What would you use?
->I would use AWS Certificate Manager to get an SSL/TLS certificate and attach it to the Application Load Balancer. The ALB can then handle HTTPS traffic for the application.


# Your company wants users to access the application using www.example.com instead of an IP address. What would you use?
->I would use Amazon Route 53 to manage the domain name and point it to the Application Load Balancer. Then users can access the application using the domain name instead of the IP address.

# Your application is running on two ECS containers, but one container becomes unhealthy. What will happen?
->The load balancer will stop sending traffic to the unhealthy container. ECS will detect that the task is unhealthy and can start a new task to maintain the required number of running containers.

# Your application needs to run the same infrastructure in development, testing, and production. How would you do it?
->I would use AWS CloudFormation to define the infrastructure as code. Then I can use the template to create the same infrastructure in different environments with different configuration values.

# Your company wants to monitor CPU usage and application logs of an EC2 server. Which AWS service would you use?
->I would use Amazon CloudWatch. It can monitor metrics like CPU usage and also collect application and system logs. I can also create alarms when a metric crosses a specific limit.

# Your application needs a database, but you don't want to manage the database server yourself. What would you use?
->I would use Amazon RDS. It is a managed relational database service, so AWS handles tasks like backups, patching, and much of the database infrastructure management.

# Your application needs very fast access to data and does not require a relational database. Which AWS database service could you use?
->I could use Amazon DynamoDB. It is a managed NoSQL database designed for fast and scalable access to data using keys.

# Your application has a React frontend and Spring Boot backend. How would you deploy both on AWS?
->I would host the React frontend using S3 and optionally CloudFront for faster delivery. I would deploy the Spring Boot backend as a Docker container using ECR and ECS with Fargate. Route 53 can handle the domain, and the backend can use RDS for the database.

# Your application is running on AWS, but you want to deploy a new version without causing much downtime. What would you do?
->I would use ECS with multiple running tasks and an Application Load Balancer. I would deploy the new version to new tasks and let the load balancer send traffic to the healthy tasks. After the new version is working correctly, the old tasks can be removed.

# Your application is running in a private subnet, but it needs to download updates from the internet. How can it access the internet securely?
->I would use a NAT Gateway in a public subnet. The private subnet would route its outgoing internet traffic through the NAT Gateway, while the application would still not be directly accessible from the internet.

# Your company wants the application to continue working even if one Availability Zone has a problem. What would you do?
->I would deploy the application across multiple Availability Zones. For example, I can run ECS tasks in different Availability Zones and use a load balancer to distribute traffic between them. This improves the application's availability if one AZ has a problem.

# Your application needs to store large files like videos, images, and PDFs. Would you use EBS or S3?
->I would use Amazon S3 because it is designed for storing files and objects. EBS is mainly block storage attached to EC2 instances, while S3 is better for large files and objects.

# Your EC2 instance needs to store application data that should remain available even after the instance is stopped. What would you use?
->I would use Amazon EBS because it provides persistent block storage for EC2. The data can remain on the EBS volume even when the EC2 instance is stopped.


