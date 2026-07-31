> **Shared Responsibility Model** A security framework most cloud providers follow to divide duties between the customer and the provider. The provider secures the underlying infrastructure, while the customer secures their own data and configurations. 


# Amazon Elastic Cloud Compute - EC2
- An EC2 instance offers a client a virtual machine to run their application. There are different types of instances suited for different types of applications. General Purpose, Compute-optimised, and Memory-optimised are some examples.
#### EC2 Pricing
- EC2 also provides different pricing options suitable for clients' needs.
  - On-Demand: Pay as you go. Only pay for the time instances are running
  - Spot: allows us to use spare AWS instances for very cheap, provided AWS can reclaim them at any time.
  - Savings plan: allows us to reduce the bill by 70% compared to on-demand in exchange for user commitment.
- EC2 falls under an unmanaged service in AWS, meaning in the SR model, AWS is only responsible for providing the hardware and software for compute, and the client should configure everything else from OS to the actual application.
#### Scaling and Load Balancing
-  Amazon EC2 Auto Scaling automatically adjusts the number of EC2 instances based on changes in application demand, providing better availability. It offers two approaches:
    - Dynamic scaling adjusts in real time to fluctuations in demand.
    - Predictive scaling preemptively schedules the right number of instances based on anticipated demand.
- **Elastic Load Balancing (ELB)** automatically distributes incoming application traffic across multiple resources, such as EC2 instances, to optimise performance and reliability. A load balancer serves as the single point of contact for all incoming web traffic to an Auto Scaling group.
#### Messaging and Queuing
 -  **EventBridge** is a serverless service that helps connect different parts of an application using events
 -  **Amazon SQS** is a message queuing service that facilitates reliable communication between software components. It can send, store, and receive messages at any scale, making sure messages are not lost and that other services don't need to be available for processing.
 -  **Amazon SNS** is a publish-subscribe service that publishers use to send messages to subscribers through SNS topics. In Amazon SNS, subscribers can include web servers, email addresses, Lambda functions, and various other endpoints.
---
# Compute Services in AWS 
AWS offers managed, unmanaged, and fully managed services, which reduce the client's responsibilities accordingly.
 ### AWS Lambda
  - One of these is AWS Lambda, a serverless compute service that runs code in response to events without the need to provision or manage servers
  - It automatically manages the underlying infrastructure, scaling resources based on the volume of requests. You are charged only for the compute time consumed, down to the millisecond.
### Containers on AWS
  - Amazon Elastic Container Service **(Amazon ECS)** is a scalable container orchestration service for running and managing containers on AWS.
  - Amazon Elastic Kubernetes Service **(Amazon EKS)** is a fully managed service for running Kubernetes on AWS.
  - Amazon Elastic Container Registry **(Amazon ECR)** is where you can store, manage, and deploy container images.
  - **AWS Fargate** is a serverless compute engine for containers. It works with both Amazon ECS and Amazon EKS. Fargate is a container hosting platform, unlike Amazon ECS and Amazon EKS, which are both container orchestration services.
  - The client can run their containers in EC2, where they configure the infrastructure and networking, or run them on Fargate, which is serverless.
### Other Compute Services.
1. **Elastic Beanstalk** is a fully managed service that streamlines the deployment, management, and scaling of web applications. Developers can upload their code, and Elastic Beanstalk automatically handles the provisioning of infrastructure, scaling, load balancing, and application health monitoring.
    >  Good for: Deploying and managing web applications, RESTful APIs, mobile backend services, and microservices architectures
2. **AWS Batch** is a fully managed service that you can use to run batch computing workloads on AWS.
    >  Good for: Processing large-scale, parallel workloads in areas like scientific computing, financial risk analysis, media transcoding, big data processing, machine learning training, and genomics research
3. **Amazon Lightsail** is a cloud service offering virtual private servers (VPSs), storage, databases, and networking at a predictable monthly price.
4. **AWS Outposts** is a fully managed hybrid cloud solution that extends AWS infrastructure and services to on-premises data centres.
---
# AWS GLOBAL
- Compliance, Proximity, Feature Availability and Pricing are the main factors to decide which region to deploy from.
- In addition to AWS Regions that contain Availability Zones, AWS has a global edge network that provides quicker content access to users outside of standard Regions.
- These edge locations are strategically placed in areas like Atlanta, Georgia, USA or Shanghai, China, to provide low-latency access to AWS services and content delivery.
- Edge locations offer multiple services to run closer to end users, including AWS networking services like Amazon CloudFront.
1. **AWS Regions** are geo-locations around the world that consist of data centres. Each region has around 3 availability zones, which are each isolated from one another to provide high availability and fault tolerance.
2. **Availability Zones** are distinct locations within a Region, each designed as an independent zone with its own power, networking, and connectivity. Each AZ has 1 or more data centres.
3. **Edge Locations** are strategically placed sites around the world that cache content to deliver data, video, and applications with lower latency and higher transfer speeds. Edge locations are considered a vital part of the AWS content delivery network (CDN) and use services like CloudFront to efficiently distribute data to end users.
### Interacting with AWS resources
1. **AWS CLI** provides a command-line interface to run scripts and automate batch tasks.
2. **AWS SDK** can help integrate AWS services into your applications by providing APIs for various programming languages. Like directly storing user data into S3 buckets.
3. **Management Console** is a web application/dashboard for all AWS services; it can be used to set up, perform cost optimisations and use services focused on graphical representation.
4. **Infrastructure as code**: with IAC tools like CloudFormation, you can automate resource management across your organisation with AWS service integrations offering efficient and repeatable resource creation and management.
    1. Managing infrastructure with DevOps such as continuous integration and delivery (CI/CD) pipelines
    2. Managing infrastructure with DevOps such as continuous integration and delivery (CI/CD) pipelines

# AWS Networking
**Virtual Private Cloud**(VPC) provides an isolated private cloud space to clients to host their resources without access to the internet.
**Subnets** are a subsection of VPCs that help divide components that need to be private, like DBs, from public components like Web Apps.

**Network Access Control Lists** are a firewall at the subnet level that maintains a stateless list of all the allowed addresses for the subnet. It checks incoming and outgoing packets for permission.
**Security Groups** are a firewall at an instance level inside the subnet that maintains a stateful list of allowed addresses for the instance. It only checks incoming packets. 

   
