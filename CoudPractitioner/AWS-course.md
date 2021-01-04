# AWS Cloud Practitioner
## AWS **Acceptable Use Policy** 

The Acceptable Use Policy describes prohibited uses of the web services offered by Amazon Web Services, Inc. and its affiliates (the “Services”) and the website located at http://aws.amazon.com (the “AWS Site”). 
This policy is present at [aup](https://aws.amazon.com/aup/) and is updated on a need basis by AWS.
- No illegal, harmfull or Offensive User or content
- No security violations.
- No Network, e-Mail or Message absue

## Types of cloud computing

- IaaS : Virtualisation, Servers, Storage and Networking is managed by the cloud company (example EC2)
- PaaS : IaaS + OS + MiddleWare + Runtime is managed by the cloud company (example Elastik bean stalk)
- SaaS : eveything is managed by the cloud company (example Rekognition)
## Pricing fundamentals

- For compute -> pay for compute time
- For Storage -> pay for data stored in the cloud
- Network -> Data transfer out of the cloud (**data transfer in is free**)

## AWS Identity and access management ([IAM](https://aws.amazon.com/iam/)) 

It is a **global service**.
Root users **should not be used** or shared.
Users and groups should be created. groups only **contains users**.
Users and groups can be assigned json documents called **policies**.Policies defines permissions.
In AWS the **least privilege principle** should be used.
Following **best practice**, groups should be created.
IAM Password Policies can be setup & Multi factor authentication.
MFA = password+ security device. the account will not be compromised if the password is lost.
MFA options : 
- **Virtual MFA device** ( google authenticator for mobile or Authy for multi devices)
- **U2F** : usb physical device
- **Hardware Key Fab** MFA & Hard Key Fab MFA for AWS govCloud(US).
### IAM Roles

Some AWS services needs access on the users behalf. Example give permission to EC2 instances, Lambda or cloudFomation.
They grant permissions to trusted entities.
### IAM Security tools :

- IAM **credential report** (Account level) : it lists all users and credential reports
- IAM **access advisor** (User level) : it shows the service permissions granted to a user and last access time.  
### Acessing AWS account

- AWS management console using password and MFA. (AWS Internet site)
- AWS command line User interface (CLI) using access keys. ( CLI can be installed on multiple OS)
- AWS SDK (used when you write code) by using access keys. ( Software developper Kit )

Acess Keys ID = username
Secret Acess Keys = password
### IAM Best practices

- do not use root account only for AWS setup account.
- one physical user = one user.
- assign users to group
- user strong password policies
- use MFA
- create roles for applications.
- use access keys for programmatic access
- use IAM **credential report** and IAM **access advisor** to audit user access.

## [Cloud Computing](../TechnicalProfessional/AWS-core.md#cloud-) 
## Elastic Cloud Compute (EC2)

It is an IaaS.

### [EC2 Instance](../TechnicalProfessional/AWS-core.md#aws-compute-services)
### [EC2 Instance Benefits](../TechnicalProfessional/AWS-core.md#aws-ec2-benefits-)
### [EC2 Instance Types](../TechnicalProfessional/AWS-core.md#aws-ec2-instance-types--)
### EC2 Security groups

They are **active firewalls** on EC2 instances
Control the traffic into and outo EC2 instances.
They have rules by ip or by security groups.
They can be attached to multiple instances.

### EC2 instance connect

Browser based ssh connection.

### EC2 Pricing

+ **on Demand** :

    On-Demand Instances are ideal for **short-term, irregular workloads that cannot be interrupted**. No upfront costs or minimum contracts apply. The instances run continuously until stopped, and customers pay for only the compute time they use.
    
    On-Demand Instances **are not recommended** for workloads that last a year or longer because these workloads can experience **greater cost savings using Reserved Instances**.

+ **EC2 Saving plans** ( Contract based)

    AWS offers Savings Plans for several compute services, including Amazon EC2. Amazon EC2 Savings Plans enable you to reduce your compute costs by committing to a **consistent amount of compute usage for a 1-year or 3-year term**. This term commitment results in **savings of up to 72% over On-Demand costs**.

+ **Reserved Instances**

    Reserved Instances are a **billing discount** applied to the use of On-Demand Instances in your account. Customers can purchase Standard Reserved and Convertible Reserved Instances for a 1-year or 3-year term, and Scheduled Reserved Instances for a 1-year term. **Customers realize greater cost savings with the 3-year option**.

    + **convertible** reserved instance : change the EC2 instance type 54% discount
    + **scheduled reserved instances** : launched withtin a timeslot.
    

+ **Scheduled Reserved Instances** 

    Scheduled Reserved Instances (Scheduled Instances) enable you to purchase capacity reservations that recur on a daily, weekly, or monthly basis, with a specified start time and duration, for a one-year term. Scheduled Instances are a good choice for workloads that do not run continuously, but do run on a regular schedule

+ **Spot Instances** ( No need for contract)

    Spot Instances are ideal for workloads with flexible start and end times, or that can withstand interruptions. Spot Instances use unused Amazon EC2 computing capacity and offer you **cost savings at up to 90% off of On-Demand prices**. They may be interrupted with a 2 min Warning in advance.

+ **Dedicated Hosts**

    Dedicated Hosts are **physical servers** with Amazon EC2 instance capacity that is fully dedicated to your Customers. **They are the most expensive**. Dedicated Hosts allow you to use your eligible software licenses from vendors such as Microsoft and Oracle on Amazon EC2.
    **3 years allocation time**.

+ **dedicated Instances**

    like dedicated Hosts, but no access to the hardware. hardware will no be shared.

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
    
     ![sns](../images/sns.jpg)

+   **Amazon Simple Queue Service** (Amazon SQS)

     Using Amazon SQS, Customers can send, store, and receive messages between software components, without losing messages or requiring other services to be available. In Amazon SQS, an application sends messages into a queue. A Customer or service retrieves a message from the queue, processes it, and then deletes it from the queue.
    

### [EC2 Compute](../TechnicalProfessional/AWS-core.md#compute-services-ec2)
### [Amazon Orchestration Tools](../TechnicalProfessional/AWS-core.md#aws-compute-services)

+ **Amazon ECS** : Elastic Container service.
    It is a highly scalable, high-performance container management service that supports Docker containers and allows you to easily run applications on a managed cluster of Amazon EC2 instances
+ **Amazon EKS** : Elastic Kubernetes service
+ **Amazon Elastic Container Registry** (ECR) can be used to store, manage, and deploy Docker container images. Amazon ECR eliminates the need to operate your container repositories. You can then pull your docker images from ECR and run those on Amazon Elastic Container Service (ECS).
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

- AWS **Shield**  is a managed Distributed Denial of Service (DDoS) protection service that safeguards applications running on AWS. AWS Shield provides always-on detection and automatic inline mitigations that minimize application downtime and latency, so there is no need to engage AWS Support to benefit from DDoS protection.
- AWS **[WAF](https://aws.amazon.com/waf/)** - By using AWS WAF, you can configure web access control lists (Web ACLs) on your **CloudFront distributions** or **Application Load Balancers** to filter and block requests based on request signatures. Besides, by using AWS WAF's rate-based rules, you can automatically block the IP addresses of bad actors when requests matching a rule exceed a threshold that you define.
![waf](../images/waf.jpg)
- **Amazon CloudFront with Route 53** - AWS hosts CloudFront and Route 53 services on a distributed network of proxy servers in data centers throughout the world called edge locations. Using the global Amazon network of edge locations for application delivery and DNS service plays an important part in building a comprehensive defense **against DDoS attacks** for your dynamic web applications.
- AWS **Elastic Beanstalk** Provide code and configuration settings, Developers upload applications, and **BeanStalk** deploys the resources necessary to Adjust capacity, load balance, perform Automatic scaling and Application health monitoring. **ZIP and WAR** files can be uploaded. At the same time, you retain full control over the AWS resources powering your application and can access the underlying resources at any time.
- AWS **CloudFormation** It can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources, It enables Customers to frequently build their infrastructure and applications without having to perform manual actions or write custom scripts
![cloudFormation](../images/cloudFormation.jpg)
- AWS **CodeCommit** is a fully-managed source control service that hosts secure Git-based repositories. It does not actually automate the build of the code or infrastructure on which it runs.
- AWS **CodeDeploy** is a fully managed deployment service that automates software deployments to a variety of compute services such as Amazon EC2, AWS Lambda, and on-premises servers
- AWS **CodePipeline** is a continuous delivery service that enables you to model, visualize, and automate the steps required to release your software. With AWS CodePipeline, you model the full release process for building your code, deploying to pre-production environments, testing your application and releasing it to production.
- AWS **CloudWatch** is a monitoring service for AWS cloud resources and the applications run on AWS.CloudWatch is used for performance monitoring, not automating operational tasks. It is built for DevOps engineers, developers, site reliability engineers (SREs), and IT managers.CloudWatch provides data and actionable insights to monitor applications, respond to system-wide performance changes, optimize resource utilization, and get a unified view of operational health. This is an excellent service for building Resilient systems. Think resource performance monitoring, events, and alerts; think CloudWatch. It cannot provide the status of your AWS resources.
- AWS **OpsWorks** is a configuration management service that provides managed instances of Chef and Puppet.  OpsWorks lets you use Chef and Puppet to automate how servers are configured, deployed and managed across your Amazon EC2 instances or on-premises compute environments.
- AWS **Config** is a fully-managed service that provides an AWS resource inventory, configuration history, and configuration change notifications to enable security and regulatory compliance.
- AWS **[Artifact](https://aws.amazon.com/artifact/)** is a central resource for compliance-related information that matters to customers.
- AWS **CloudHSM** is a fully managed cloud-based **hardware security module** (HSM) that enables the easy generation and use of own encryption keys on the AWS Cloud
- AWS **Key Management Service (KMS)** makes it easy for you to create and manage cryptographic keys and control their use across a wide range of AWS services and in your applications. AWS KMS is a secure and resilient service that uses hardware security modules that have been validated under FIPS 140-2, or are in the process of being validated, to protect your keys
- AWS **Cognito** adds user sign-up, sign-in, and access control to web and mobile apps quickly and easily.
- AWS **DirectoryService** for Microsoft Active Directory, also known as AWS Managed Microsoft Active Directory (AD), enables your directory-aware workloads and AWS resources to use managed Active Directory (AD) in AWS
- AWS **ElastiCache** provides in-memory cache and database services.
- AWS **RedShift** is a fast, scalable data warehouse
- AWS **Systems Manager** gives you visibility and control of the infrastructure on AWS. Systems Manager provides a unified user interface so customers can view operational data from multiple AWS services and it allows to automate operational tasks across AWS resources. With Systems Manager, you can group resources, like Amazon EC2 instances, Amazon S3 buckets, or Amazon RDS instances, by application, view operational data for monitoring and troubleshooting, and take action on your groups of resources.
- AWS **Glacier** encrypts data automatically
- AWS **Inspector** automatically assesses applications for exposure, vulnerabilities, and deviations from best practices.
- AWS **QuickSight** is a scalable, serverless, embeddable, machine learning-powered business intelligence (BI) service built for the cloud. QuickSight lets you easily create and publish interactive BI dashboards that include Machine Learning-powered insights
- AWS **CloudTrail** is a service that enables **governance, compliance, operational auditing, and risk auditing** of your AWS account. With CloudTrail, you can **log**, continuously monitor, and retain account activity related to actions across your AWS infrastructure. CloudTrail provides event history of your AWS account activity, including actions taken through the AWS Management Console, AWS SDKs, command line tools, and other AWS services. By default, the log files delivered by CloudTrail to your S3 bucket **are encrypted** using server-side encryption with Amazon S3–managed encryption keys (SSE-S3).
- AWS **Trusted Advisor** compares its findings to AWS best practices in five categories: **cost optimization**, **performance**, **security**, **fault tolerance**, and **service limits**. For the checks in each category, Trusted Advisor offers a list of recommended actions and additional resources to learn more about AWS best practices. Whether establishing new workflows, developing applications, or as part of ongoing improvement, recommendations provided by Trusted Advisor regularly help keep your solutions provisioned optimally
- **Amazon Kinesis Data Streams** (KDS) is a massively scalable and durable real-time data streaming service. KDS can continuously capture gigabytes of data per second from hundreds of thousands of sources such as website clickstreams, database event streams, financial transactions, social media feeds, IT logs, and location-tracking events. The data collected is available in milliseconds to enable real-time analytics use cases such as real-time dashboards, real-time anomaly detection, dynamic pricing, and more. 
- **LightSail** Lightsail is an easy-to-use cloud platform that offers you everything needed to build an application or website, plus a cost-effective, monthly plan.
- AWS **Health DashBoard**
- HyperVisorLayer
- Resource Group

- **Elasticity** is The ability to acquire resources as you need and release when they are no longer needed is termed as Elasticity of the Cloud. With cloud computing, you don’t have to over-provision resources upfront to handle peak levels of business activity in the future. Instead, you provision the number of resources that you need. You can scale these resources up or down instantly to grow and shrink capacity as your business needs change.
- **Agility** refers to the ability to rapidly develop, test and launch software applications that drive business growth Another way to explain "Agility" - AWS provides a massive global cloud infrastructure that allows you to quickly innovate, experiment and iterate. Instead of waiting weeks or months for hardware, you can instantly deploy new applications. This ability is called Agility.
- **Reliability** - Refers to the ability of a system to recover from infrastructure or service disruptions, by dynamically acquiring computing resources to meet demand, and mitigate disruptions.
- **Durability** - Refers to the ability of a system to assure data is stored and data remains consistently on the system as long as it is not changed by legitimate access, i.e. data should not get corrupt or disappear from the cloud because of a system malfunction.
- **Resiliency** - Describes the ability of a system to recover from a failure induced by the load (data or network), attacks, and failures (hardware, software, or network failures).
- **Region vs Global Services** : Most of the services that AWS offers are Region specific. But few services, by definition, need to be in a global scope because of the underlying service they offer. AWS IAM, Amazon CloudFront, Route 53 and WAF are some of the global services.
- **Amazon CloudFront** is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment.
- **Amazon Elastic Compute Cloud** (Amazon EC2) - Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable compute capacity in the cloud. It comes under Infrastructure as a Service type of Cloud Computing. This is a regional service.
- **Amazon S3** - Amazon S3 is a unique service in the sense that it follows a **global namespace but the buckets are regional**. You specify an AWS Region when you create your Amazon S3 bucket. **This is a regional service**.
- **Performance Efficiency** - Is the ability to use computing resources efficiently to meet system requirements and to maintain that efficiency as demand changes and technologies evolve.
- **Access keys** are long-term credentials for an IAM user or the AWS account root user. You can use access keys to sign programmatic requests to the AWS CLI or AWS API (directly or using the AWS SDK). Access keys consist of **two parts**: an **access key ID** (for example, AKIAIOSFODNN7EXAMPLE) and a **secret access key** (for example, wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY). As a user name and password, you must use both the access key ID and secret access key together to authenticate your requests. Access Keys are secret, just like a password. You should never share them. **Access keys are not tied to the IAM role, IAM group, or AWS policy**.
- AWS **Personal Health Dashboard** provides alerts and remediation guidance when AWS is experiencing events that may impact you. With Personal Health Dashboard, alerts are triggered by changes in the health of your AWS resources, giving you event visibility, and guidance to help quickly diagnose and resolve issues.
- AWS **Service Health Dashboard** publishes most up-to-the-minute information on the status and availability of all AWS services in tabular form for all Regions that AWS is present in. You can check on this [page](https://status.aws.amazon.com/) any time to get current status information or subscribe to an RSS feed to be notified of interruptions to each service.
- The **[Well-Architected Framework](https://aws.amazon.com/blogs/apn/the-5-pillars-of-the-aws-well-architected-framework/)** pillars :
   - **Reliability** - This design principle includes the ability of a system to recover from infrastructure or service disruptions, dynamically acquire computing resources to meet demand (keep the systems available, plan for failure). The Reliability pillar cannot help with traceability of action by any user on the system.
   - **Operational Excellence** - This design principle includes the ability to run and monitor systems to deliver business value (monitor systems and proactively take actions). Operational Excellence pillar cannot help with traceability of action by any user on the system.
   - **Performance Efficiency** - This design principle includes the ability to use computing resources efficiently and maintain efficiency as demand changes. Performance Efficiency pillar cannot help with traceability of action by any user on the system.
   - **Cost Optimization**
   - **Security**
- AWS **Service Catalog** allows organizations to create and manage catalogs of IT services that are approved for use on AWS. These IT services can include everything from virtual machine images, servers, software, and databases to complete multi-tier application architectures. Service Catalog cannot be used to review the compliance and governance-related documents on AWS.
- AWS **Secrets Manager** helps you protect secrets needed to access your applications, services, and IT resources. The service enables you to easily rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle. Users and applications retrieve secrets with a call to Secrets Manager APIs, eliminating the need to hardcode sensitive information in plain text. Secrets Manager cannot be used to review the compliance and governance-related documents on AWS.
- **Amazon API Gateway** is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale.
- **Amazon EMR** is the industry-leading cloud big data platform for processing vast amounts of data using open source tools such as Hadoop, Apache Spark, Apache Hive, Apache HBase, Apache Flink, Apache Hudi, and Presto. Amazon EMR can be used to provision resources to run big data workloads on Hadoop clusters.
- **AWS Step Function** lets you coordinate multiple AWS services into **serverless workflows**. You can design and run workflows that stitch together services such as AWS Lambda, AWS Glue and Amazon SageMaker.
- **[AWS Batch](https://aws.amazon.com/batch/)** can be used to plan, schedule and execute your batch computing workloads across the full range of AWS compute services. AWS Batch dynamically provisions the optimal quantity and type of compute resources (e.g., CPU or memory optimized instances) based on the volume and specific resource requirements of the batch jobs submitted. AWS Batch provisions compute resources and optimizes the job distribution based on the volume and resource requirements of the submitted batch jobs.
    
    > AWS Batch runs batch computing workloads by provisioning the compute resources. AWS Step Function does not provision any resources. Step Function only orchestrates AWS services required for a given workflow. You cannot use Step Functions to plan, schedule and execute your batch computing workloads by provisioning underlying resources.
- A VPC spans all of the Availability Zones in the Region whereas a [subnet](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html) spans only one Availability Zone in the Region
- AWS **WAF is a web application firewall** that helps protect your web applications or APIs against common web exploits that may affect availability, compromise security, or consume excessive resources. AWS WAF gives you control over how traffic reaches your applications by enabling you to create security rules that block common attack patterns such as SQL injection or cross-site scripting. You can also use rate-based rules to mitigate the Web layer DDoS attack.
- Amazon **[GuardDuty](https://aws.amazon.com/guardduty/)** is a threat detection service that monitors malicious activity and unauthorized behavior to protect your AWS account. GuardDuty analyzes billions of events across your AWS accounts from AWS CloudTrail (AWS user and API activity in your accounts), Amazon VPC Flow Logs (network traffic data), and DNS Logs (name query patterns). GuardDuty cannot be used to protect from web exploits such as SQL injection and cross-site scripting.
![guardDutie](../images/guardDutie.jpg)
- AWS **[Global Accelerator](https://aws.amazon.com/global-accelerator/)** is a service that improves the availability and performance of your applications with local or global users. It provides static IP addresses that act as a fixed entry point to your application endpoints in a single or multiple AWS Regions, such as your Application Load Balancers, Network Load Balancers, or Amazon EC2 instances. AWS Global Accelerator uses the AWS global network to optimize the path from your users to your applications, improving the performance of your traffic by as much as 60%.
Global Accelerator improves performance for a wide range of applications over TCP or UDP by proxying packets at the edge to applications running in one or more AWS Regions.
     > ![exam alert](../images/gobalAccelerator.jpg)
     > ![globalAccelerator](../images/globalAccelerator.jpg)
- There are **three fundamental drivers** of cost with AWS: **compute, storage, and outbound data transfer**. In most cases, there is **no charge** for inbound data transfer or **data transfer between other AWS services within the same region**. Outbound data transfer is aggregated across services and then charged at the outbound data transfer rate.
- AWS **Partner Network** - Organizations can take help from the AWS Partner Network (APN) to identify the right AWS services to build solutions on AWS Cloud. APN is the global partner program for technology and consulting businesses that leverage Amazon Web Services to build solutions and services for customers.
- Amazon **Concierge Support Team** are AWS billing and account experts that specialize in working with enterprise accounts. They will quickly and efficiently assist you with your billing and account inquiries. The Concierge Support Team is only available for the Enterprise Support plan
- Amazon **[Rekognition](https://aws.amazon.com/rekognition/)**, you can identify objects, people, text, scenes, and activities in images and videos, as well as detect any inappropriate content. Amazon Rekognition also provides highly accurate facial analysis and facial search capabilities that you can use to detect, analyze, and compare faces for a wide variety of user verification, people counting, and public safety use cases.
- AWS **[Total Cost of Ownership (TCO) Calculator](https://awstcocalculator.com/)** - AWS helps reduce Total Cost of Ownership (TCO) by reducing the need to invest in large capital expenditures and providing a pay-as-you-go model that empowers to invest in the capacity you need and use it only when the business requires it. TCO calculator helps to compare the cost of your applications in an on-premises or traditional hosting environment to AWS. Once you describe your on-premises or hosting environment configuration, it produces a detailed cost comparison with AWS.
- AWS **Simple Monthly Calculator** provides an **estimate** of usage charges for AWS services based on certain information you provide. It **helps** customers and prospects **estimate their monthly AWS bill** more efficiently.
- The **AWS Professional Services** organization is a global team of experts that can help you realize your desired business outcomes when using the AWS Cloud. AWS Professional Services consultants can supplement your team with specialized skills and experience that can help you achieve quick results.
- AWS **Landing Zone** is a solution that helps customers more quickly set up a secure, multi-account AWS environment based on AWS best practices. This solution can help save time by automating the set-up of an environment for running secure and scalable workloads while implementing an initial security baseline through the creation of core accounts and resources.
- Amazon **Macie** is a fully managed data security and data privacy service that uses machine learning and pattern matching to discover and protect your sensitive data in AWS. Macie helps identify and alert you to sensitive data, such as personally identifiable information (PII). This service is for securing data.
- Amazon **Polly** is used to turn text into lifelike speech. 
- Amazon **Transcribe** is used to convert speech to text quickly and accurately
- Amazon **Translate** is used for language translation.
- Amazon **Elasticsearch** - The term "Elasticsearch" is used to define a distributed, open source search and analytics engine for all types of data, including textual, numerical, geospatial, structured, and unstructured. Amazon Elasticsearch Service is a fully managed service that makes it easy to deploy, secure, and run Elasticsearch cost effectively at scale. **It is a search and analytics service from Amazon**.
- AWS **X-Ray** is used to analyze and debug serverless and distributed applications such as those built using a microservices architecture. With X-Ray, you can understand how your application and its underlying services are performing to identify and troubleshoot the root cause of performance issues and errors.
- Amazon **Pinpoint** allows marketers and developers to deliver customer-centric engagement experiences by capturing customer usage data to draw real-time insights.
- Cross-Region replication (CRR) is used to replicate data between distant AWS Regions
- Same-Region replication (SRR) is used to copy objects across Amazon S3 buckets in the same AWS Region
- AWS **Transit Gateway** connects VPCs and on-premises networks through a central hub. This simplifies your network and puts an end to complex peering relationships. It acts as a cloud router – each new connection is only made once. As you expand globally, inter-Region peering connects AWS Transit Gateways using the AWS global network. Your data is automatically encrypted and never travels over the public internet
![transitGateway](../images/transitGateway.jpg)
- **VPC peering connection** is a networking connection between two VPCs that enables you to route traffic between them privately. VPC peering is not transitive, a separate VPC peering connection has to be made between two VPCs that need to talk to each other. With growing VPCs, this gets difficult to manage.
![vpcPeering](../images/vpcPeering.jpg)
- AWS  **Site to Site VPN** creates a secure connection between your data center or branch office and your AWS cloud resources. This connection goes over the public internet. Site to Site VPN cannot be used to interconnect VPCs.
- Cloud Computing Models
![cloudModels](../images/cloudModels.jpg)
- AWS **[Support Plans](https://aws.amazon.com/premiumsupport/plans/)**
![supportPlans](../images/support1.jpg)
![supportPlans](../images/support2.jpg)
- AWS **System Manager** gives you visibility and control of your infrastructure on AWS. Systems Manager provides a unified user interface so you can view operational data from multiple AWS services and allows you to automate operational tasks such as running commands, managing patches, and configuring servers across AWS Cloud as well as on-premises infrastructure.
![systemManager](../images/systemManager.jpg)