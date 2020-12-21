# AWS Cloud Practitioner

## [Cloud Computing](../TechnicalProfessional/AWS-core.md#cloud-) 
## EC2
### [EC2 Instance](../TechnicalProfessional/AWS-core.md#aws-compute-services)
### [EC2 Instance Benefits](../TechnicalProfessional/AWS-core.md#aws-ec2-benefits-)
### [EC2 Instance Types](../TechnicalProfessional/AWS-core.md#aws-ec2-instance-types--)
### EC2 Pricing

+ **on Demand** :

    On-Demand Instances are ideal for **short-term, irregular workloads that cannot be interrupted**. No upfront costs or minimum contracts apply. The instances run continuously until stopped, and customers pay for only the compute time they use.
    
    On-Demand Instances **are not recommended** for workloads that last a year or longer because these workloads can experience **greater cost savings using Reserved Instances**.

+ **EC2 Saving plans** ( Contract based)

    AWS offers Savings Plans for several compute services, including Amazon EC2. Amazon EC2 Savings Plans enable you to reduce your compute costs by committing to a **consistent amount of compute usage for a 1-year or 3-year term**. This term commitment results in **savings of up to 72% over On-Demand costs**.

+ **Reserved Instances**

    Reserved Instances are a **billing discount** applied to the use of On-Demand Instances in your account. Customers can purchase Standard Reserved and Convertible Reserved Instances for a 1-year or 3-year term, and Scheduled Reserved Instances for a 1-year term. **Customers realize greater cost savings with the 3-year option**.

+ **Spot Instances** ( No need for contract)

    Spot Instances are ideal for workloads with flexible start and end times, or that can withstand interruptions. Spot Instances use unused Amazon EC2 computing capacity and offer you **cost savings at up to 90% off of On-Demand prices**. They may be interrupted with a 2 min Warning in advance.

+ **Dedicated Hosts**

    Dedicated Hosts are physical servers with Amazon EC2 instance capacity that is fully dedicated to your Customers. **They are the most expensive**. 

+ **AWS Cost Explorer**

    It can analyze your Amazon EC2 usage over the past 7, 30, or 60 days. AWS Cost Explorer also provides customized recommendations for Savings Plans.

### [EC2 Scaling](../TechnicalProfessional/AWS-core.md#scalable-architecture-)

- When Customers create an Auto Scaling group, Customers can set the minimum number of Amazon EC2 instances. The minimum capacity is the number of Amazon EC2 instances that launch immediately after Customers created the Auto Scaling group. 
- Customers can set a desired capacity
- Custumers sets a maximum capacity for peak workloads or capacity.

### [EC2 Load Balancer](../TechnicalProfessional/AWS-core.md#aws-compute-services)

### Messaging and Queuing

+   **Amazon Simple Notification Service** (Amazon SNS)
     
     It is a **publish/subscribe service**. Using Amazon SNS topics, a publisher publishes messages to subscribers.
     eMails/Push Notifications/text messages/ https requests.

+   **Amazon Simple Queue Service** (Amazon SQS)

     Using Amazon SQS, Customers can send, store, and receive messages between software components, without losing messages or requiring other services to be available. In Amazon SQS, an application sends messages into a queue. A Customer or service retrieves a message from the queue, processes it, and then deletes it from the queue.
    

### [EC2 Compute](../TechnicalProfessional/AWS-core.md#compute-services-ec2)
### [Amazon Orchestration Tools](../TechnicalProfessional/AWS-core.md#aws-compute-services)

+ **Amazon ECS** : Elastic Container service.
+ **Amazon EKS** : Elastic Kubernetes service
+ **Amazon FarGate**



