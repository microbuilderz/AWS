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

## check [Technical Professional](../TechnicalProfessional/AWS-core.md) for further documentation

## AWS Cloud practitioner domain

> ![examDomain](../images/examDomain.jpg)

### **Recommended experience**

Candidates for the AWS Certified Cloud Practitioner exam should have a basic understanding of IT services and their uses in the AWS Cloud platform. 

We recommend that you have at least **six months of experience** with the AWS Cloud in any role, including project managers, IT managers, sales managers, decision makers, and marketers. These roles are in addition to those working in finance, procurement, and legal departments.


### **Exam details**

The AWS Certified Cloud Practitioner exam consists of **65 questions** to be completed in 90 minutes. The minimum passing score is 70%.

### **Whitepapers and resources**

- [Overview of Amazon Web Services](https://d1.awsstatic.com/whitepapers/aws-overview.pdf) 
- [How AWS pricing Works](http://d1.awsstatic.com/whitepapers/aws_pricing_overview.pdf)
- [Compare AWS Supportplan](https://aws.amazon.com/premiumsupport/plans/)

## Exam Practice 

- [20 AWS Practitioner questions](https://digitalcloud.training/aws-cloud-practitioner-free-practice-questions/)
- [Free Practitioner exams](https://www.awsboy.com/aws-practice-exams/practitioner/)

## Remarks and more stuff

- AWS **Elastic Beanstalk** Provide code and configuration settings, Developers upload applications, and **BeanStalk** deploys the resources necessary to Adjust capacity, load balance, perform Automatic scaling and Application health monitoring. **ZIP and WAR** files can be uploaded.
- AWS **CloudFormation** It can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources, It enables Customers to frequently build their infrastructure and applications without having to perform manual actions or write custom scripts
- AWS **CodeCommit** is a fully-managed source control service that hosts secure Git-based repositories. It does not actually automate the build of the code or infrastructure on which it runs.
- AWS **CodeDeploy** is a fully managed deployment service that automates software deployments to a variety of compute services such as Amazon EC2, AWS Lambda, and on-premises servers
- AWS **CloudWatch** is a monitoring service for AWS cloud resources and the applications run on AWS.CloudWatch is used for performance monitoring, not automating operational tasks
- AWS **OpsWorks** is a configuration management service that provides managed instances of Chef and Puppet.
- AWS **Config** is a fully-managed service that provides an AWS resource inventory, configuration history, and configuration change notifications to enable security and regulatory compliance.
- AWS **Artifact** is a central resource for compliance-related information that matters to customers.
- AWS **CloudHSM** is a cloud-based **hardware security module** (HSM) that enables the easy generation and use of own encryption keys on the AWS Cloud
- AWS **Cognito** adds user sign-up, sign-in, and access control to web and mobile apps quickly and easily.
- AWS **DirectoryService** for Microsoft Active Directory, also known as AWS Managed Microsoft Active Directory (AD), enables your directory-aware workloads and AWS resources to use managed Active Directory (AD) in AWS
- AWS **ElastiCache** provides in-memory cache and database services.
- AWS **RedShift** is a fast, scalable data warehouse
- AWS **Systems Manager** gives you visibility and control of the infrastructure on AWS. Systems Manager provides a unified user interface so customers can view operational data from multiple AWS services and it allows to automate operational tasks across AWS resources.
- AWS **Glacier** encrypts data automatically
- AWS **Inspector** automatically assesses applications for exposure, vulnerabilities, and deviations from best practices.
- AWS **QuickSight** is a scalable, serverless, embeddable, machine learning-powered business intelligence (BI) service built for the cloud. QuickSight lets you easily create and publish interactive BI dashboards that include Machine Learning-powered insights
- AWS **CloudTrail** is a service that enables **governance, compliance, operational auditing, and risk auditing** of your AWS account. With CloudTrail, you can **log**, continuously monitor, and retain account activity related to actions across your AWS infrastructure. CloudTrail provides event history of your AWS account activity, including actions taken through the AWS Management Console, AWS SDKs, command line tools, and other AWS services
- AWS **Trusted Advisor** compares its findings to AWS best practices in five categories: **cost optimization**, **performance**, **security**, **fault tolerance**, and **service limits**. For the checks in each category, Trusted Advisor offers a list of recommended actions and additional resources to learn more about AWS best practices. 
- **Amazon Kinesis Data Streams** (KDS) is a massively scalable and durable real-time data streaming service. KDS can continuously capture gigabytes of data per second from hundreds of thousands of sources such as website clickstreams, database event streams, financial transactions, social media feeds, IT logs, and location-tracking events. The data collected is available in milliseconds to enable real-time analytics use cases such as real-time dashboards, real-time anomaly detection, dynamic pricing, and more. 
- **LightSail** Lightsail is an easy-to-use cloud platform that offers you everything needed to build an application or website, plus a cost-effective, monthly plan.
- AWS **Health DashBoard**
- HyperVisorLayer


