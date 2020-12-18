# AWS Technical Professional

## Intro :

- AWS : Amazon web service
- POC : Proof of concept
- APN : AWS Partner Network


## AWS Core Technologies :

+    ### Cloud :

        In contast with On-Premises IT, the user will access ressources ( apps/ database/ server / storage ... ) throught the internet. 

+    ### Cloud computing :

        It's an on demand delivery of compute power, database, storage,.. via the internet with pay as you go pricing.
    
+    ### Advantage of cloud computing :
    
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
        
        
+   ### AWS Global Infrastructure 
    [infrastructure](https://www.infrastructure.aws/)

    -    AWS Regions:

            AWS cloud computing ressources are hosted in multiple locations called **AWS regions**. 
            Each region is **completly isolated** -> great fault tolerance and stability -> increased [resiliency](https://en.wikipedia.org/wiki/Resilience_(network)). 
            
            > Ressources **are only viewable withtin the region**, no ressources are replicated automatically across regions.

    -    Availibility zone (AZ):
    
            Seperated geographic area with multiple isolated locations. All AZ are interconnected with high bandwidth low latency fully [redundent fiber](https://blog.ospinsight.com/the-importance-of-fiber-network-redundancy).
            
            A minimum of 2 AZ is available in each region.

            > Deploying on multiple AZ in the same region **improves availability**.

    -    Points of Presence (POP):
    
            Edge locations and regional Edge cache servers are used by Amazon CloudFront to deliver data, video, apps and APS with low latency transfer speed.

## AWS core categories :

AWS has infrustructure services in different catgeories : Compute, Storage, Database, Security, Management, Networking. Thus offering a **high degree of architecture flexebility**. Cutomers can power up Web & Mobile apps, Data processing and Warehousing, Storage and archiving.

+    ### Compute services EC2 
        [compute types](https://aws.amazon.com/products/compute/) 
    
        They allow customers to Develop, Deploy, Run & scale workloads.
        They are the compute building blocks and comes with a large variaty of hardware configurations. Their software are customizeable at launch trough **AMI**. Can be used with auto scaling and load balancers.

        +    #### AWS compute services

                1. **Amazon EC2** : Amazon Elastic Compute Cloud.
                
                    A web service that provides resizeable secure compute capacity in the cloud.
    
                    > compute capacity refers to that functionality that is traditionally provided by on premises and virtual servers.

                2. Amazon EC2 [Auto Scaling](https://aws.amazon.com/ec2/autoscaling/).
                
                    Customer can maintain the health and availability of their applications by **setting triggers** to **automatically increase/decrease** the number of instances

                    **automatically add/remove EC2 instances** to adapt to demand.
                    
                    - It can **monitor the health** of running instances. When an instance fails the health check it will get terminated and replaced by a new one. 

                    - It also **automatically balance instances across zones**.

                    - Ensure **Dynamic** and **Predictive Scaling**
                
                3. **Amazon ELB** : [Elastic Load Balancing](https://aws.amazon.com/elasticloadbalancing/).
                
                    It increases **availability** and **fault tolerance** of apps.
                
                    **Distributes** application traffic across **multiple targets** : EC2 instances, containers, IP adresses and lamda functions. in one or more availability zones.

                    The load balancer sends requests only to **healthy instances** which are configured by the customer.

                    They can offload encryption and decryption so that instances only needs to focus on their main work.

                    There are three types of load balancers :

                    1. Application load balancer.(*For web apps with http and https*)
                    2. Network load balancer.(*more resilient on traffic spikes*)
                    3. Classic load balancer.(*previous generation load balancer for EC2 classic instances*)
                
                4. AWS Lambda
                
                    Runs code without server management. It is referred as **serverless computing**. Codes are run withtin **milliseconds of an event**
                
                5. **Amazon ECS** : Elastic Container service
                
                    Highly scalable, high performance container management service that **supports docker containers**. It allows easy running of apps on a **managed cluster of Amazon EC2 instances**.

        +    #### AWS EC2 Benefits :

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
                    
        +    #### AWS EC2 [Instance types](https://aws.amazon.com/ec2/instance-types/)  :
                
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

        +   #### Amazon Machine Images (AMI) :

            Initial software configuration of an instance.
            AMIs must be specified when launching the instance.
            AMI are provided by AWS, AWS marketplace, User community, or custom AMIs chich can be created and managed by the customer.

        +   ### Scalable architecture :

            In the Cloud, **computing power is a programmatic ressource**, allowing **flexible scaling** approach:

            1. Launch new instances in advance of Peak Periods.
            
            2. Use Monitoring to programatically scale out.
             
            3. Automatically scale down when the need is low.
            
            > The customer only pays for the used ressources.  
              