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
- IAM **access advisor** (User level) : it shows the service permissions granted to a specific user and last access time.  
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
## [Elastic Cloud Compute (EC2)] (../TechnicalProfessional/AWS-core.md#compute-services-ec2)

It is an IaaS.

### [EC2 Instance](../TechnicalProfessional/AWS-core.md#aws-compute-services)
### [EC2 Instance Benefits](../TechnicalProfessional/AWS-core.md#aws-ec2-benefits-)
### [EC2 Instance Types](../TechnicalProfessional/AWS-core.md#aws-ec2-instance-types--)
### EC2 Security groups

They are **active firewalls** on EC2 instances
Control the traffic into and outo EC2 instances.
They have rules by ip or by security groups.
They can be attached to multiple instances.

### EC2 **user data**

Script launched at the first start of instance

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

+ **Dedicated Instances**

    like dedicated Hosts, but no access to the hardware. hardware will no be shared.

+ **AWS Cost Explorer**

    It can analyze your Amazon EC2 usage over the past 7, 30, or 60 days. AWS Cost Explorer also provides customized recommendations for Savings Plans.

## [EC2 Storage](../TechnicalProfessional/AWS-core.md#storage-services-)

### Amazon Machine Images (AMI) 

Are a custimization of EC2 instances.

### Storage Gateway

Brige between on premise data and cloud.
### EBS Storage

EBS storage is a **network drive** , One EBS volume can be attached **to a single instance**.
Are **locked to one AZ**. EBS volume are **persistant**. only same AZ instances cann attach to EBS.
to transfer EBS volume data across regions, we can use **snapshot** to restore it in another region or AZ.
EBS snapshots are stored in amazone S3.
### Instance Storage

**Hardware** disk storage. Better IO performance. They **loose their** storage when detached. They are good for buffer/ cache / temporary content.

### EFS storage

Can be mounted to 100s of EC2. shared EFS. works across **multiple AZ**. expensive. it is scalable.

## Elastic Load Balancer & Auto scaling group

## [Elastic Load Balancer](../TechnicalProfessional/AWS-core.md#aws-compute-services)
It is a Managed Load balancer across multiple AZ. It supports health checks.

- Application LB : HTTP/HTTPs layer 7
- Network LB : ultra high perfromance , TCP layer 4
- Classic LB : layer 4 and layer 7.

## [Auto Scaling Group] (ASG)(../TechnicalProfessional/AWS-core.md#scalable-architecture-)

Create or removes instances depending on demands or instance health across AZ. it can be used with elastic load balancer.
they are defined by minimun size, desired capacity, and a maximum size.

## [Amazone Simple Storage service](../TechnicalProfessional/AWS-core.md#amazone-simple-storage-service-s3)

- **Infinitly** scalable storage. 
- Can be used for **disaster recovery**, **archive**, **hybrid** cloud storage, **media hosting**, **big data**, **software delivery** and **static websites**.
- S3 stores **objects** in **buckets**. Buckets must be **uniqly named globally**. Buckets are created at the **region level**.
- Bucket **key** is the **full path**.
- Maximum object size is **5 Gig**. (**use multi part upload** for bigger then 5 Gigs).
- By default public Bucket are blocked.
- S3 can host static files

### S3 Security

- **User based** : through IAM Policies.With I am Policies there( without cross account ) is no need for Bucket policies.
- **Ressource Based** :
    - Bucket policies : bucket rules from s3 console to allow/deny access and AWS cross account access
    - Object Access Control List : finer control
    - Bucket Access Control List
- **Encryption**

has to be activated.

### S3 Versioning

Used to version files. It is enabled at bucket level.

### S3 Access Logs

Logs **request** to buckets in **another S3 Bucket**.

### S3 Replication

copying is asynchronus.

- CRR : cross region replication : compliance/low latency access/replication acrosse accounts. Used to **globally** optimize **dynamic data**.
- SRR : same region replication : logs / live repliction between production and test accounts.

### S3 Classes

all have 11 9's of durability : how often you will loose a file

availability : how available is the service.

- S3 Standard : 99,99% availability , frequently accessed data (big data, mobile application).
- S3 IA : 99,9% infrequent and rapid access. **lower cost but retrieval fee** ( disaster recovery).
- S3 Intelligent tiering : 99,9% availability, **most cost saving**.
- S3 IA One Zone : 99,5% availability (secondary backup copy).
- Glacier : frozen data **low cost** (GB/Month), there are fees for **retrieval**.
- Glacier Deep archive **cheapest**.

there are **transition rules** that can be used to **transit objects** between storage classes using **lifecycle configurations**.

### S3 Data transportation

Physical data transportation. **cost effictive**
use [snowball](../TechnicalProfessional/AWS-core.md#aWS-Snow-Family)

## Database & Analytics

### RDS

- **Managed database** using SQL.
- **Automated** provisioning , OS patching.
- Continuous backup and restore options.
- Monitoring dash board.
- scale the read perfromance with read replicas.
- Multi AZ for disaster recovery.
- Storage is backed by EBS.
- Vertical/Horizontal scalable.
- OLTP : online transaction processing

### Aurora

Propriatory, cloud optimized, supports only Postgres (3x perfromance) and MySql(5x performance).
- Aurora storage automatically scales in 10GB increments up to 64TB
- Aurora **costs 20%** more than RDS.
- Not included in free tier.
- OLTP : online transaction processing

### ElastiCache

- **In memory database** with high perfromance low latency.
- **reduce loads** off databases. 

### DynamoDB

- Fully Managed High availability DB with **replication across 3 AZ**.
- **noSQL** key/Value database.
- **Serverless** database.
- **millions** of requests/sec.
- low **latency retrieval**

### RedShift

- **Warehouse** and use **analytics** on it.
- Column based and not row based.
- Based on **PostgresSQL**.
- OLAP ( Online Analytical processing)
- Integrated with BI such as **AWS QuickSight** and **Tableau**

### Elastic Map Reduce (EMR)

- creates **Hadoop cluster** (BigData) to analyse and process Big data.
- used for data processing machine learning web indexing, big data.
- provisions EC2 instances and configure them.

### Athena

- Full **Serverless** database with SQL capabilities.
- Queries data in **S3**
- Pay per Query

### Data Migration Service (DMS)

- Used for database migration into AWS.
- The source database remains **available during migration**.

### AWS Glue

It's a managed **E**xtract, **T**ransform and **L**oad service (ETL).
Used to prepare and transform data to analytics.
It's full **serverless**.
Glue Data Catalog is a central repository to store the cataloge of datasets. It is used to **provide metadata** to athena, Redshift and EMR.

## Other Compute services

### [Amazon Orchestration Tools](../TechnicalProfessional/AWS-core.md#aws-compute-services)

### Elastic container service (ECS)

It launches docker containers on AWS. The customer need to provision and maintain EC2 instances.

### Amazon EKS : Elastic Kubernetes service

### FarGate :

Serverless, Same as ECS but **no need to provision** the infrastructure.

### Elastic Container Registry (ECR)

Private Docker Container in AWS. Stores Docker Images that can be run by Fargate.

### AWS Lamda

**On demand** , **autoscalable**, **serverless** virtual functions **limited by time for shorter time of execution**.
Pay per request. It is event driven. Integarted with **programming languages**.
**Docker** can not be used with **lamda**.
It **has a free tier** with 1 Millions calls. after the free tier, customer **pay by calls , duration and RAM**. 
It is used for workloads from **0 to 15 Minutes**.

### AWS Batch

**Serverless with no time limit**, used for Efficiently running **100000s** of computing jobs on AWS.

### LightSail

**Low and predictable** pricing. FUlly managed. Can setup monitoring and notifications.
Mostly for website, simple applications. For Users with **No cloud expierience**.

## Deployment & Management Infrastructure

### CloudFormation

Cloudformation **template** is used to build **Infrastructure as Code**. Can be used to replicate infrastructure.
Can be **timely managed** to destroy the services at certain time.It's usage **is free**.

### BeanStalk

It is a Managed **Plattform as a service**. It is a **developer centric view**.
It's usage **is free**.
### CodeDeploy

It doesn't need to use CloudFormation or BeanStalk. It is a **hybrid service**. Servers and Instances **must be provisioned**.

### System Manager Service (SSM)

Manage the fleet of EC2 instances and on-premises. It can be used to **patch automate the instances**, **run commands across services**, **Store parmater configuration**.
An **SSM** agent has to be installed on instances.
### OpsWorks

Managed **Chef and puppet** service.
## Global Infrastructure

Deployment in **different regions or edge locations**. It improves **latency**, adds a **disaster recovery plan**.
### Route 53

**Route users** to the closest deplyment with the lowest latency. Good for disaster recovery strategy.
It's **not a free service**. 
It's a **managed DNS** service.
> - map name to address -> A record
> - map name to long adress -> AAAA record.
> - map name to a name -> CName
> - map name to AWS ressource -> Alias.

It has following routing policies :

- **Simple** Routing policy (1 to 1) with **no health** checks
- **Weighted** Routing Policiy with **health check**
- **Latency** Routing Policiy with **health check**
- **Failover** Routing Policy with **health check**

### CloudFront

It's a Content delivery network **(CDN)**. It **replicates content**  in to edge locations. It improves the read perfomance by caching to edge locations. 
It has **Ddos protection**. It caches in **S3 Bucket** or **Https server**. Not best suited for **dynamic content**.

### S3 Transfer Acceleration

Increase transfer speed of files in and out of S3.

### AWS Global Accelerator

**Redirects** to the proper application region throught the AWS internal network.
## Cloud Integration

**Decouple** applications with SQS or SNS
### Simple Queue Service SQS

Serverless ( Managed ) low letency **message queuing**. It uses a **pull based system**.
It's a **free service**. Message are **retained by default 4 Days** and to a **maximum of 14 Days**.
### Simple Notification Service SNS

It's a **publisher/subscriber** service.
SNS **publisher** will send notifications. All **subscriber** will recieve the notifications.
Subscribers can be : HTTP(S) end points, email, SMS Messages, Mobile Apps, **SQS queues** , **Lambda Functions**.

![sns](../images/sns.jpg)

## Cloud Monitoring

### CloudWatch

It Provides **metrics for every service** in AWS.example : Billing Metric, CPU Utilization in EC2, Ststus check, Network check, EFS Volumes, S3 Buckets, Service Limits ...
+ ### CloudWatch alarm

  Are used to trigger notifications for metrics and can setup alarm actions. example : Auto scaling / EC2 actions / SNS Notifications
+ ### CloudWatch logs

  collects logs from services and provides realtime monitoring of logs.

+ ### CloudWatch Events = Event Bridge

  It can be used to **schedule jobs (CRON)**, or **react to events** example IAM login.
### CloudTrail

Is a **governance/compliant** and **aws account audit** service.
get a history of events API call of :
- console,
- CLI,
- SDK,
- AWS services

### AWS X-RAY

Debugging in production of **distributed services**. It's a **visual analysis** of the applications. It is also used for **troubleshooting**.

### Service Health DashBoard

Shows **Historical information for services in all region** (services Health). It **monitors** AWS Infrastrutcture.
### Personal Health DashBoard

Provides **alert and remediation** guidance for AWS infrastructure. It provides **personalized views of perfromance and availability**.

## VPC & Networking

VPC is Private network to deploy ressources. It is tied to a **specific region**. within a VPC are subnets which allows the **partitioning of network** inside it.
There are **public** (accessible to internet) subnet and **private** one in AZ.
**Intenet Gateway** are used to allow traffic to **public subnets**.
**NAT Gateway** are used to allow traffic to **private** subnets that will allow them to **connect to internet while remaining private**.

### Security Group & Network access Conrol List 

NACL is at the **subnet level** before it reaches the instance. (statless)
Security group is a firewall that controls traffic to and from EC2 Instances. it operates at the **instance level** (statefull)

### VPC Flow log

It captures information about network traffic. It is used to **monitor and troubleshoot** connectivity issues.

### VPC Peering

Connect two vpc using aws network.Both will look as if they are **in the same network**.

### VPC Endpoints

Allows to connect using private network for better security. better latency.
- VPC Endpoint **Gateway** : for S3 and DynamoDB
- VPC EndPoint **Interface** : for the rest of services.

### Direct Connect & Site to Site VPN

Used for hybrid connection:

Site to Site VPN : **Encrypted connection** and goes over the public internet. ( **Customer and Virtual Private Gateway** are needed to connect)
DirectConnect : **Physical private connection** between on-premises and AWS. ( take at least a month to be established).

### Transit Gateway

To allow peering between thousand of VPCs also with on-premise infrastructure.

## Security & Compliance
### DDos Protection

    + AWS Shield Standard : free. Protection against commun DDos attacks.
    + AWS Shield Advanced : Premium DDos Protection. Protection against more sophisticated DDos attacks.
    + AWS WAF : Filter request based on rules. Protects Web Applications from common exploits using (Web access control list)
    + CloudFront & Route 53
### Penetration Testing

Attack own infrastructure for testing. No **need to inform AWS** about the test.

### Encryption

- Key Management Service KMS, by default CloudTrail, S3 Glacier and Storage Gateway. 
- CloudHSM : Customers manage their own keys using hardware Security.

### Secrets Manager

**Stores Secrets**. It allows Forcing the **rotation** of secrets. it can **manage RDS credentials**.
### Artifcat

On demand access to **compliance and documentation**. Good for **internal audit** and **compliance documents**.

### GuardDuty

It is a **threat detection service** that **continously monitors** **malicious activities** and **unauthorized behaviors**.
It uses **Machine learning algorithm** to protect **AWS account**.
**Can emit events to cloudwatch**. cloud watch can then trigger functions.

### Inspector

**Automated Security** and **vurnabilities assesment** on **EC2 Instances only**.

### Config

**Auditing and recording** config changes and AWS ressources. Can recieve SNS events. It is a paid service.

### Macie

Fully managed data security and privacy service. Used to find sensitive data.

## Machine Learning

### [Rekognition](https://aws.amazon.com/rekognition/)

Finds **people/text/scenes** in images and videos
### Transcribe

Convert Speech to text quickly and accurately.
### Polly

Convert Text to Speech

### Translate

It translates languages.

### Lex

Same tech as in alexa. It uses Natural language understandings to recognize the meaning. Can be used to build chat bots.

### Comprehend

It is for Natural language Processing.

### SageMaker

Fully Managed service for **developer to build machine learning models**.


## Accound Management & Billing

### AWS Organization 

It's a global service. 
The consolidated billing feature of AWS Organizations enables to receive a **single bill** for **all AWS accounts in an organization**.
Pooling from reserved instances will be shared.
It provides an **api to automate account creation**.
It can also **restrict account privileges** using **service control policies**.

### AWS total Cost of ownership (TCO)

It evaluates the cost saving by moving on-premises to AWS.

### AWS Pricing Calculator ( Simple Monthly Calculator **deprecated** )

Caluclates the cost of the architecture solution.

### AWS Billing DashBoard

Shows the costs for the Month.

### Cost allocation tags ###

Allows to track costs by category. ( ressource groups)

### Cost and Usage Reports

Generates reports in details for cost and usage.

### Cost explorer

**Visual tool** to **analyse costs** using **custom reports**, and can **forcast** Bills.

### Billing Alarm

global billing alarm

### Budget

Creates Budgets and send alarms when a threshold has been exceeded.

### AWS **[Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor)**

AWS Trusted Advisor is a web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices.

> ![advisor](../images/trustAdvisers.jpg)

Trusted Advisor compares its findings to AWS best practices in five categories: **cost optimization**, **performance**, **security**, **fault tolerance**, and **service limits**. For the checks in each category, Trusted Advisor offers a list of recommended actions and additional resources to learn more about AWS best practices. 
**Alarms Can be set to CloudWatch Events**

### AWS Support Plans

- Free: 24hx7 access to customer service
- Developer: emails Cloud Support Associates. 24 hours reponse General/ 12h system impairs
- Business: 24x7 email, phone and chat access , production system impaires <4h, Production system down <1h
- Enterprise: dedicated TAM + concierge supoort team for billing, business critical down < 15 min

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
- [Udemy Practice exams](https://www.udemy.com/course/practice-exams-aws-certified-cloud-practitioner)

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