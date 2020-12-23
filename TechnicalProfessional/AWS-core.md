# AWS Core Technologies :

## Cloud :

In contast with On-Premises IT, the user will access ressources ( apps/ database/ server / storage ... ) throught the internet. 

## Cloud computing :

It's an on demand delivery of compute power, database, storage,.. via the internet with pay as you go pricing.
    
## Advantage of cloud computing :
    
1. Variable expense : 
**only pay** for what the customer consumes **when they need to**.
2. Benefit from massive economy of scale : 
AWS achieves heigher economy of scale -> **lower pay as you go prices**.
3. guessing capacity : 
**Eliminates guessing on infrastructure capacity** needs, no idle ressouce waiting, ressources in cloud computing can **scale according to the demand**.
4. Speed and agility :
New IT ressources are available within minutes.
5. **Stop spending money** on running and maintaining infrastructure.
6. Deploy globally (multiple regions) in minutes.

> AWS offers a huge range of features and services to help customers achieve their goals.
        
#        
## AWS Global [Infrastructure](https://www.infrastructure.aws/)

-    ### AWS Regions:

        AWS cloud computing ressources are hosted in multiple locations called **AWS regions**. 
        Each region is **completly isolated** -> great fault tolerance and stability -> increased [resiliency](https://en.wikipedia.org/wiki/Resilience_(network)). 
        
        > Ressources **are only viewable withtin the region**, no ressources are replicated automatically across regions.

        How to **choose a region?**:

        1. Compliance : requirements (exmaple country requirment)
        2. Proximity : close to customer (speed and latency)
        3. Feature availability : not all features are availble in all regions.
        4. Pricing : not same pricing for all regions. 

-    ### Availibility zone (AZ):

        Seperated geographic area with multiple isolated locations. All AZ are interconnected with high bandwidth low latency fully [redundent fiber](https://blog.ospinsight.com/the-importance-of-fiber-network-redundancy).
        
        A minimum of 2 AZ is available in each region.

        > Deploying on multiple AZ in the same region **improves availability**.
        > 
        > On Instance runs in One AZ.

- ### Points of Presence (POP):

   Edge locations and regional Edge cache servers are used by **Amazon CloudFront (global content delivery service)** to store cached data, video, apps and APS with low latency transfer speed closer to customers. It accelerate communication and content delivery.
  
- ### Amazon Outpost :
        
  AWS Outposts is a fully managed service that offers the same AWS infrastructure, AWS services, APIs, and tools to virtually any datacenter, co-location space, or on-premises facility for a truly consistent hybrid experience. AWS Outposts is ideal for workloads that require low latency access to on-premises systems, local data processing, data residency, and migration of applications with local system interdependencies.    

## AWS core categories :

AWS has infrustructure services in different catgeories : Compute, Storage, Database, Security, Management, Networking. Thus offering a **high degree of architecture flexebility**. Cutomers can power up Web & Mobile apps, Data processing and Warehousing, Storage and archiving.

#
## [Compute](https://aws.amazon.com/products/compute/) services 

They allow customers to Develop, Deploy, Run & scale workloads.
They are the compute building blocks and comes with a large variaty of hardware configurations. Their software are customizeable at launch trough **AMI**. Can be used with auto scaling and load balancers.

> ![image](../images/compute.jpg)
### AWS compute services

1. **Amazon EC2** : Amazon Elastic Compute Cloud.

    A web service that provides resizeable secure compute capacity in the cloud.

    > compute capacity refers to that functionality that is traditionally provided by on premises and virtual servers.

2. **Amazon EC2 [Auto Scaling](https://aws.amazon.com/ec2/autoscaling/)**.

    Customer can maintain the health and availability of their applications by **setting triggers** to **automatically increase/decrease** the number of instances (horizontal scaling) as well as the hardware of the instance (vertiacal scaling)

    **automatically add/remove EC2 instances** to adapt to demand.
    
    - It can **monitor the health** of running instances. When an instance fails the health check it will get terminated and replaced by a new one. 

    - It also **automatically balance instances across zones**.

    - Ensure **Dynamic** and **Predictive Scaling**

3. **Amazon ELB** : [Elastic Load Balancing](https://aws.amazon.com/elasticloadbalancing/).

    It increases **availability** and **fault tolerance** of apps.

    **Distributes** application traffic across **multiple targets** : EC2 instances, containers, IP adresses and lamda functions. in one or more availability zones.

    It is **scalable** and acts at the **region level**.

    The load balancer sends requests only to **healthy instances** which are configured by the customer.

    They can offload encryption and decryption so that instances only needs to focus on their main work.

    There are three types of load balancers :

    1. Application load balancer.(*For web apps with http and https*)
    2. Network load balancer.(*more resilient on traffic spikes*)
    3. Classic load balancer.(*previous generation load balancer for EC2 classic instances*)

4. **AWS Lambda**.

    Runs code without server management. It is referred as **serverless computing**. Codes are run withtin **milliseconds of an event**

5. **Amazon ECS** : Elastic Container service.

    Highly scalable, high performance container management service that **supports docker containers**. It allows easy running of apps on a **managed cluster of Amazon EC2 instances**.
    Containers can be managed with API calls.

6. **Amazon EKS** : Elastic Kubernetes service ( Container service)

     Fully managed service that you can use to run Kubernetes on AWS. 

7. **AWS Fargate** (serverless) :

     It works with both Amazon ECS and Amazon EKS.

### AWS EC2 Benefits :

1. **Elasticity** : 

    Increase and decrease capacity withtin minutes.
    combined **with EC2 autoscaling**, customers maintain availability and scale down and up automatically -> maximized perfromance and minimized costs.

2. **Complete control** :

    100% control with root access.

3. **Flexible hosting** :

    Choosing instances types, OS and software packages.

4. **Integrated with most AWS services** :

    Provides secure solution for compute, query processing and storage.

5. **Reliability** :

    Instances can be rapidly and predictably commissioned.

6. **Secure**
7. **Inexpensive** :

    Pay a very low rate for the consumed compute capacity.

8. **Easy to get started** :

    Free to get started.
          
### AWS EC2 [Instance types](https://aws.amazon.com/ec2/instance-types/)  :
        
Refers to the hardware capabilities of an instance.

1. **General Purpose** :

    provides balance between compute, memory any network ressouces.

2. **Optimized** :

    Using High perfromance processors ideal for compute bound apps.

3. **Memory Optimized** :
    
    Fast perfromance for large datasets in memory.

4. **Accelerated** :
    
    Using hardware accelerators or co processors for accelerated floating point calc, data pattern processing, gpu processing, ...

5. **Storage Optimization** :   
        
    For high sequential read/write access. 10.000 of IO access/second.

> Each category has different families, example : A,T,M inside the general purpose category.

### Amazon Machine Images (AMI) :

Initial software configuration of an instance.
AMIs must be specified when launching the instance.
AMI are provided by AWS, AWS marketplace, User community, or custom AMIs chich can be created and managed by the customer.

### Scalable architecture :

In the Cloud, **computing power is a programmatic ressource**, allowing **flexible scaling** approach:

1. Launch new instances in advance of Peak Periods.

2. Use Monitoring to programatically scale out.
    
3. Automatically scale down when the need is low.

> The customer only pays for the used ressources.  
# 
## [Storage](https://aws.amazon.com/products/storage/) Services 

A reliable, scalable and secure place for data.

> ![image](../images/storageServices.jpg)

### AWS storage services

1. **Instance Stores**

    Are not persistent. Best for Temporary data when it is not kept for long term.
    
1. **Amazon Elastic Block Store (EBS)** :

    **Persistent storage** like a hard drive. Customers can create partitions on it, format it and boot from it. It Persists **independently** from the **instances**. 
    
    They are automatically **replicated across zones** to prevent data loss.

    Can be attached to **any instance in the zone**.

    Can only be **attached to one EC2 instance** except in the case of using **multi attach OPS ssd** (max 16 instances).
    
    One instance can attach to **multiple EBS volumes**.

    It stores data **in a single AZ**. It **can not be autoscaled**.

    Allow point in time snapshots which are stored in S3. The **snapshot** can be **copied across regions**.

    For **complex read write change functions**.

    > Sizes are between 1 Giga Byte to 16 Terra Byte **allocated by 1 Giga Byte increment**.

2. **Amazone Simple Storage service [(S3)](https://aws.amazon.com/s3/)**:

    Storage for internet wich privides simple web service interface which can be used to store and retrieve data from the internet.

    It's an object storage service. It stores data in objects called **buckets** 

    **Unlimited** number of objects , each with a **max size of 5 Terrabyte**.

    Data can be versioned.

    write once, read many.

    I web enabled and serverless.

    For complete objects or minor changed files.

    It supports **eleven 9s of durability and four 9s of availibility**.

    > ![storage](../images/s3Storage.jpg)

    > **Use cases** : 
    >
    > - backup and storage
    > - application hosting
    > - media hosting
    > - software delivery ( downloadable software )

3. **Amazon S3 Glacier**:

    For data archiving. It allows the easy storage of big data with low cost for decades.

4. **AWS storage Gateway**: 

    Transfer data between on promises sites and aws storage infrastructure (in and out). 

5. **Amazone Elastic File System (EFS)** :

    File storage for EC2 instances. It provides a simple interface for creating and configuring file systems.
    The storage is elastic **(autoscales)**.
    It is ideal for use cases in which a large number of services and resources need to access the same data at the same time.
    Supports Multiple Read/write at the same time.
    Linux Based Filesystem. It is a **regional ressouce**.
    It stores data in **multiple AZ**.

### [Storage classes](https://aws.amazon.com/s3/storage-classes/) :

> ![storage](../images/s3StorageClasses.jpg)

1. **S3 standard** : for frequently accessed data, low latency high throughput.
    
2. **S3 standard infrequent access (IA)** : for data that is accessed less frequently, but rapidly. cost less then S3 standard and is ideal for long term storage, backups and disaster recovery files.
    
3. **S3 One Zone IA** : costs 20% then standard IA. costs 20% less, good for secondary backup copy or easy recreatble data.

4. **S3 Glacier** : For data archiving. It allows the easy storage of big data with low cost for decades.provides three retrieval options ( from minutes to hours).

5. **S3 Glacier Deep Archive** : provides retrieval in 12 hours.

> **S3 intelligent tiering** is offered in order to **automate cost saving** by moving data between **two acces tiers** configured by the customer.

#        
## [Database](https://aws.amazon.com/products/databases/) Services  

### **Advantages Over EC2**

- **Easier to setup an maintain** then running database software on EC2. 

- Backup/recovery/managing patches/updates .. is done automatically within amazone RDS.

- High available database, synchronous multi zone deployment.

- Synchronized replication for high availability oracle.

- No need to manage backups and point in time recoveries.

### **Disadvantage in contrast to EC2**

- **In Ec2** the customer has **more control and flexibility**.

- Operating System access. Use of commercial software not supported by database services.

> ![db](../images/dbServices.jpg)  

### **Database Storage Types:**

1. Amatzon RDS :
    
    Supports Amazone Aurora/Postgres/MariaDB/MySQL/Oracle/MySQL server. Scalable, cost efficient and resizeable capacity.
    
    Has automatic backup, snapshots, automatic host replacement.

2. Amazon DynamoDB : (serverless database)

    noSQL database. fast and predicatble performance in range of millisecond digits.
    It is a Nonrelational database. has simple schemas. can remove any item at any time.
    It allows Automatic Autoscaling. It is high scalable.
    Simple queries on one table.
    It is fully managed and uses a key value pair.
    It scales upto 10 Trillion requests per day.

3. Amazon Aurora:

    It is compatible with MySQL and PostgreSQL relational databases.
    Five times faster than standard MySQL databases and up to three times faster than standard PostgreSQL databases.

    If the workloads require high availability. It replicates six copies of your data across three Availability Zones and continuously backs up your data to Amazon S3.

4. Amazon RedShift:

    It is a **data warehouse** for **Big Data** BI Solutions. Used for **looking backwards queries**.
    Petab Bytes of data. It is 10x Times fatser then traditional databases.

5. Amazon DocumentDB:
     
    It is a **document database** service that supports MongoDB workloads. (MongoDB is a document database program.)

6. Amazon Neptune:
     
    It is a graph database service. To build and run applications that work with highly connected datasets, such as recommendation engines, fraud detection, and knowledge graphs.

7. Amazon Quantum Ledger Database (Amazon QLDB):
    
    It is a ledger database service. 
    It can be used to review a complete history of all the changes that have been made to application data.

8. Amazon Managed Blockchain :

    It is a service that you can use to create and manage blockchain networks with open-source frameworks. 

### **Additional Database services and accelerators**

1. Amazon ElastiCache :

    Deploy in memory cache in the cloud. Improves the performance of web apps from a fast managed in memory cache instead of slower disk based databases.

2. Amazon DynamoDB Accelerator (DAX):
    
    It is an in-memory cache for DynamoDB. It helps improve response times from single-digit milliseconds to microseconds. 

### **Database Migration Service AWS (DMS)**

It enables the **migration** of relational databases, nonrelational databases, and other types of data stores.
It can migarate homogenous ( Compatible source and target) and non hetrogenous databases( source and target are not compatible ).

Hetrogenous migration is a 2 step migration: First the data needs to be converted using the **schema converter** then migrated via DMS

While migrating using DMS , the source is kpt alive.

DMS can be used during :
    - Development and test database migration.
    - Database consolidation : (combining several databases into one database).
    - Coninuous replication.
#     
## [Networking](https://aws.amazon.com/products/networking/) services 

It enables customers to build a virutal private network in the cloud ([VPC](https://en.wikipedia.org/wiki/Virtual_private_cloud)).

It provides security features for group access and network access control lists.

Amazon Route53 is a **DNS service** that routes users to applications by translating human readble names into IP addresses. 
            
> ![db](../images/network.jpg)

### **Amazon Virtual private Network (VPC):**

- **Internet gateway** :
    
    To allow public traffic from the internet to access your VPC, you attach an internet gateway to the VPC.

- **Virtual private gateway** :

    To access private resources in a VPC.It encrypts (or protects) internet traffic from all other requests around it. 
    **It allows traffic** into the VPC only if it is coming **from an approved network**.
    
- AWS **Direct Connect**:

    It is a service that enables the establishment of a dedicated private connection between customers data center and a VPC. 

- Customers have **complete control** over their virtual network : 
    
    1. Select their IP ranges.
    2. Create subnets.
    3. Configure route tables and gateways.
        
- Ressouces can be launched into a specified [subnets](https://en.wikipedia.org/wiki/Subnetwork):
    
    1. **public subnet** : for for ressources connected to internet ( typically front end ).
    2. **private subnet** : ressources that are not connected to internet ( hidden from customers, backend ... ).

### **[Amazon network security](https://aws.amazon.com/answers/networking/vpc-security-capabilities/)**
- **Amazon Network access control Lists (NACL):** (stateless)

    - Controls traffic at a subnet level. Evaluates packets. 
    - By default it enables all inbound and outbound traffic.
    - For custom network ACLs, all inbound and outbound traffic is denied until you add rules to specify which traffic should be allowed.

- **Amazon Network security groups:** (statefull)

    - Controls traffic acts at AWS instance level.
    - 5 security groups can be set per instance.
    - If not set a default security group will be applied. ( blocking all ports and traffics )
    - They allow all outbound traffic.
      
- **VPC flow log** 
    - captures netwokr information and store it in **Amazon CloudWatch** Log. It can be used to check why a traffic is not reaching an instance which might be causes by over restrictive security groups.

- **Host based Firewalls**
    - can be enabled at the operating system. example iptables, windows fierwalls or third party ones.

# 
## **Amazon [security,identity and compliance services](https://aws.amazon.com/products/security/)**

**Benefits** of AWS Security:

- **Keeps Your Data Safe**: The AWS infrastructure puts strong safeguards in place to help protect customers privacy. All data is stored in highly secure AWS data centers.

- **Meet Compliance Requirements**: AWS manages dozens of compliance programs in its infrastructure. This means that segments of your compliance have already been completed.

- **Save Money**: Cut costs by using AWS data centers. Maintain the highest standard of security without having to manage your own facility

- **Scale Quickly**: Security scales with your AWS Cloud usage. No matter the size of your business, the AWS infrastructure is designed to keep customers data safe.

AWS **Shield**

AWS Shield is a service that protects applications against **DDoS attacks**. AWS Shield provides two levels of protection:

- AWS **Shield Standard** automatically protects all AWS customers at **no cost**. It protects your AWS resources from the most common, frequently occurring types of DDoS attacks. 

- AWS **Shield Advances** is a paid service that provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks. 

> ![db](../images/security.jpg)

### **AWS Identity and access management ([IAM](https://aws.amazon.com/iam/))**

Manages access to AWS services and ressources. Throught IAM, user and groups can be created and permission can be managed through **IAM policies**.
It allows :

- **Fine grained access to AWS ressources**. ( limiting users to certain ressources, specific access at a specific time of day , ...)
- Additional security with **Multi factor Authentication** for users (especially root).
- Possibility to **analyze access**.
- **Integration with corporate directories** to allow **[federated access](https://en.wikipedia.org/wiki/Federated_identity)** like Microsoft active directory.

- **IAM Roles** is an identity that you can assume to gain temporary access to permissions.
 
### **AWS [shared responsability model](https://aws.amazon.com/compliance/shared-responsibility-model/)**

> ![db](../images/sharedSecurity.jpg)

- AWS is responsible for the **security of the cloud** : hardware, software networking and facilities. It is also reponsible for the security configurations of it's products.

- Customers are reponsible for the **security in the cloud** : security of customer content and applications that use AWS services.
### **AWS cloud [compliance](https://aws.amazon.com/compliance/)**

- AWS environment are continuasly audited.
- AWS shars information about industry certifications, security and control practices.

### **AWS Organizations**

- it is used to consolidate and manage multiple AWS accounts within a **central location**.
- In AWS Organizations, customers can **centrally control** permissions for the accounts in their organization by using **service control policies (SCPs)**
- **SCPs enable** customers to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access. It can place policies to the **organization root, an individual member account, or an Organizational Unit (OU)(group accounts)**
- It also profits from the **consolidating billing** (one billing)

### **Compliance**

 AWS **Compliance center** can be used to find AWS compliance.

 AWS **Artifact** is a service that provides **on-demand access** to AWS security and compliance reports and select online agreements. AWS Artifact consists of two main sections: **AWS Artifact Agreements** and AWS **Artifact Reports**.

 - In AWS Artifact Agreements, you can review, accept, and manage agreements for an individual account and for all your accounts in AWS Organizations. Different types of agreements are offered to address the needs of customers who are subject to specific regulations

 - AWS Artifact Reports provide compliance reports from third-party auditors. These auditors have tested and verified that AWS is compliant with a variety of global, regional, and industry-specific security standards and regulations. AWS Artifact Reports remains up to date with the latest reports released. You can provide the AWS audit artifacts to your auditors or regulators as evidence of AWS security controls. 
 
### Denial-of-service attacks (DoS)

 Is a deliberate attempt to make a website or application unavailable to users.

### AWS **Key Management Service** (AWS KMS)

 It enables customers to perform **encryption operations** through the use of **cryptographic keys**.

### AWS **WAF**

 It is a web application firewall that **monitors network requests** that come into web applications by using a web **access control list** (ACL) to protect AWS resources. 

### Amazon **Inspector**

 Amazon Inspector helps to improve the security and compliance of applications by running automated security assessments. It checks applications for security vulnerabilities and deviations from security best practices, such as open access to Amazon EC2 instances and installations of vulnerable software versions. 

### Amazon **Guard Duty**

 It is a service that provides **intelligent threat detection** for your AWS infrastructure and resources. It identifies threats by continuously monitoring the network activity and account behavior within AWS environment.


#     
## [Management Interfaces](https://docs.aws.amazon.com/)

**Three way of management** based on **restfull api**

- AWS **management console** :GUI Interface to manage cloud. ( intranet based manual configuration )
- AWS **Command Line Interface** (CLI) interface allows access via commands. ( scriptable can be run automatically)
- AWS **Software development Kits** (SDK) allows acces inside code ( various programming languages )
- AWS **AWS Elastic Beanstalk** ( Managed Tool)
  
    Provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform the following tasks:

    1. Adjust capacity
    2. Load balancing
    3. Automatic scaling
    4. Application health monitoring

- AWS **CloudFormation** ( Managed Tool)

    It can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources.
    It provisions resources in a safe, repeatable manner, enabling Customers to frequently build their infrastructure and applications without having to perform manual actions or write custom scripts. It determines the right operations to perform when managing customers stack and rolls back changes automatically if it detects errors.
#
## Monitoring and analytics

### Amazon **[CloudWatch](https://aws.amazon.com/cloudwatch/)**

It is a web service that enables you to **monitor and manage various metrics** and configure **alarm actions** based on data from those metrics using **(SNS)**.

It can create alarms that automatically perform actions if the value of a metric has gone above or below a predefined threshold.

The **CloudWatch dashboard** feature enables to access all the metrics for your resources from a single location in a GUI interface.

It provides **central access** to metrics and logs, **gives visibility** in applications, infrastructure and services. It reduces **Mean Time To resolution (MTTR)** and improves **Total Cost of Ownership (TCO)**

### Amazon **CloudTrail**

AWS CloudTrail **records API calls** for customers account. The recorded information includes the identity of the API caller, the time of the API call, the source IP address of the API caller, and more.

Events are typically updated in CloudTrail within 15 minutes after an API call.

Within CloudTrail, **CloudTrail Insights** can be enabled. This optional feature allows CloudTrail to automatically detect unusual API activities in AWS accounts. 

It helps **Filter logs** to assist with **operational analysis and troubleshooting**.

### AWS **[Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor)** 

AWS Trusted Advisor is a web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices.

> ![advisor](../images/trustAdvisers.jpg)

Trusted Advisor compares its findings to AWS best practices in five categories: **cost optimization**, **performance**, **security**, **fault tolerance**, and **service limits**. For the checks in each category, Trusted Advisor offers a list of recommended actions and additional resources to learn more about AWS best practices. 
#
## **Pricing and support**

### AWS **Free Tier**

The AWS Free Tier enables you to begin using certain services without having to worry about incurring costs for the specified period.

Three types of offers are available: 

- Always Free
- 12 Months Free
- Trials

## AWS **pricing concept**

- Pay for usage (On Demand): 
    For each service, you pay for exactly the amount of resources that you actually use, without requiring long-term contracts or complex licensing. 
- Pay less when Reserving:
    Some services offer reservation options that provide a significant discount compared to On-Demand Instance pricing.
- Pay less with volume-based discounts when using more:
    Some services offer tiered pricing, so the per-unit cost is incrementally lower with increased usage.

## AWS **Pricing Calculator**

The AWS Pricing Calculator lets explore AWS services and **create an estimate** for the cost of use cases on AWS. AWS estimates can be organized by groups that can be defined. A group can reflect how the company is organized, such as providing estimates by **cost center**.

exmaple : 

- AWS Lambda : It offers **1 Million free request per Month**. 
- Amazon EC2 : can choose a Spot Instance that would provide  up to 90% cost savings while still meeting the availability requirements of your workload.
- Amazon S3 : 
    1. Customers only for only the **storage that they use**.
    2. Customers pay for **Requests and data retrievals**.
    3. There is **no cost to transfer** data between different **Amazon S3 buckets** or from **Amazon S3** to other services **within the same AWS Region**
    4. **Management and replication features are paid features**.

### **Billing Dashboard**

The AWS Billing & Cost Management dashboard is used to **pay AWS bills**, **monitor usage**, and **analyze and control** costs.

### **Consolidated billing**

It's a **free Feature**.

The consolidated billing feature of AWS Organizations enables to receive a **single bill** for **all AWS accounts in an organization**.

The **default maximum number** of accounts allowed for an organization is 4.

One benefit of consolidated billing is the ability to **share bulk discount pricing, Savings Plans, and Reserved Instances across the accounts in an organization**.

### AWS **Budgets**

Customer can create budgets to plan their service usage, service costs, and instance reservations.

It set custom alerts when the usage exceeds 

### AWS **Cost Explorer**

It is a tool that enables customer to visualize, understand, and manage your AWS costs and usage over time.
It allows also to create custom reports.
It can show costs by user defined tags.

### AWS **Support**

- Basic (free for everyone ): Customer service/ Documentation / whitepapers/ limited access to trusted advisers / Personal DashBoard.
- Developer : email customers support, reponse in 24h.
- Business: phone access (4h response if production system is impaire and 1h if production system is down ) , It provides infrastructure event management. It have access to all AWS Trusted Advisor 
- Entreprise : 15 min reponse time.dedicated technical account manager.
They provide guidance, architectural reviews, and ongoing communication with companis as they plan, deploy, and optimize their applications. 

### AWS **Marketplace**

AWS Marketplace is a digital catalog that includes thousands of software listings from independent software vendors. It can be used to find, test, and buy software that runs on AWS. 

#
## Migration and innovation

### AWS **Cloud Adoption Framework**
It guives guidance on who to loop on the framework.
There are Six core perspectives of the Cloud Adoption Framework.

- Business Perspective : focus on business capabilities
- People Perspective: focus on business capabilities
- Governance Perspective: focus on business capabilities
- Plattform Perspective: focus on technical capabilities
- Security Perspective: focus on technical capabilities
- Operation Perspective: focus on technical capabilities

### **Migration for strategies (6R)**

- Rehosting : also known as “lift-and-shift” involves moving applications without changes into the cloud. 
- Replatforming : “lift, tinker, and shift,” involves making a few cloud optimizations to realize a tangible benefit. Optimization is achieved without changing the core architecture of the application.
- Refactoring/re-architecting : Involves reimagining how an application is architected and developed by using cloud-native features
- Repurchasing : involves moving from a traditional license to a software-as-a-service model. 
- Retaining :  consists of keeping applications that are critical for the business in the source environment.
- Retiring : is the process of removing applications that are no longer needed.

### **AWS Snow Family**:

The AWS Snow Family is a collection of physical devices that help to **physically transport** up to exabytes of data into and out of AWS.

AWS Snow Family is composed of :
- AWS Snowcone : AWS Snowcone is a small, rugged, and secure edge computing and data transfer device. It features 2 CPUs, 4 GB of memory, and 8 TB of usable storage.
- AWS Snowball : 
   
    1. Snowball Edge Storage Optimized devices are well suited for large-scale data migrations and recurring transfer workflows, in addition to local computing with higher capacity needs. 80 TB of hard disk drive (HDD) and 1 TB of SATA solid state drive (SSD)  
    2. Snowball Edge Compute Optimized : provides powerful computing resources for use cases such as machine learning, full motion video analysis, analytics, and local computing stacks. 42-TB usable HDD capacity, 7.68 TB of usable NVMe SSD.
- AWS Snowmobile : It  is an exabyte-scale data transfer service used to move large amounts of data to AWS. (100 Peta Byte)
#
## More Services
+ ### Amazon **textract**
  Document based service
+ ### Amazon **sage maker** : 
  For building machine learning.
+ ### Amazon **Augmenated AI**
+ ### Amazon **[Lex](https://aws.amazon.com/lex)** : 
  alexa service
+ ### Amazon **DeepRacer**
+ ### Amazon **ground station** 
+ ### ....
#
## AWS **well-architectued Framework**

Tool fo evaluate the framework.based on following framework pillars:

1. Operational Excellence :
    It is the ability to run and monitor systems to deliver business value and to continually improve supporting processes and procedures. 
2. Security :
    The Security pillar is the ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies. 
3. Reliability:
    - Recover from infrastructure or service disruptions Dynamically 
    - acquire computing resources to meet demand
    - Mitigate disruptions such as misconfigurations or transient network issues   
4. Performance Efficiency:
    Is the ability to use computing resources efficiently to meet system requirements and to maintain that efficiency as demand changes and technologies evolve. 
5. Cost Optimization:
    Cost optimization is the ability to run systems to deliver business value at the lowest price point.
## Conclusion

- AWS offers more then 165 services: from compute, storage, machine learning, analytics, IoT  