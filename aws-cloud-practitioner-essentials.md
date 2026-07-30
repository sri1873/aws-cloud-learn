> **Shared Responsibility Model** A security framework most cloud providers follow to divide duties between the customer and the provider. The provider secures the underlying infrastructure, while the customer secures their own data and configurations. 

# Amazon Elastic Cloud Compute - EC2
- An EC2 instance offers a client a virtual machine to run their application. There are different types of instances suited for different types of applications. General Purpose, Compute-optimised, and Memory-optimised are some examples.
### EC2 Pricing
- EC2 also provides different pricing options suitable for clients' needs.
  - On-Demand: Pay as you go. Only pay for the time instances are running
  - Spot: allows us to use spare AWS instances for very cheap, provided AWS can reclaim them at any time.
  - Savings plan: allows us to reduce the bill by 70% compared to on-demand in exchange for user commitment.
- EC2 falls under an unmanaged service in AWS, meaning in the SR model, AWS is only responsible for providing the hardware and software for compute, and the client should configure everything else from OS to the actual application.
### Scaling and Load Balancing
-  Amazon EC2 Auto Scaling automatically adjusts the number of EC2 instances based on changes in application demand, providing better availability. It offers two approaches:
    - Dynamic scaling adjusts in real time to fluctuations in demand.
    - Predictive scaling preemptively schedules the right number of instances based on anticipated demand.
- **Elastic Load Balancing (ELB)** automatically distributes incoming application traffic across multiple resources, such as EC2 instances, to optimise performance and reliability. A load balancer serves as the single point of contact for all incoming web traffic to an Auto Scaling group.
### Messaging and Queuing
 -  **EventBridge** is a serverless service that helps connect different parts of an application using events
 -  **Amazon SQS** is a message queuing service that facilitates reliable communication between software components. It can send, store, and receive messages at any scale, making sure messages are not lost and that other services don't need to be available for processing.
 -  **Amazon SNS** is a publish-subscribe service that publishers use to send messages to subscribers through SNS topics. In Amazon SNS, subscribers can include web servers, email addresses, Lambda functions, and various other endpoints. 
