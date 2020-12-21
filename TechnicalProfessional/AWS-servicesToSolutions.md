# AWS Services to Solutions :

## Migration Strategies :

- **Rehost** : Lift and Shift
  
  Recreate the On premises Network only hosted in AWS:
    - servers are migrated to EC2 instances
    - network configuration are migrated to VPC, subnet, groups, internet and VPN gateways.
    - customer benefits from the **pay as you go pricing**, he can also **elevate it's capacity** when needed.
    - the migration can be **automated** via **AWS VM Import/Export**.
    - Once hosted on the cloud, it is **easier to optimize and reachitecture** 

- **Replattform** : Lift tinker and shift
 
    Same as Rehost but making cloud optimization. example :
    
    - moving the database to a managed one like (RDS).
    - apply elasticity to instances.
    - it can use best practices.

- **Refactor** : Modernize

    Apply AWS Cloud to modernize the architecture. For example :

    - Apply Amazone Aurora instead of RDS.
    - Change Monolitic app to microservices to be able to use container and AWS lambda.
    
- **Retire** :
    - shutting non usefull app.
    - reduction of cost/management/security.

- **Retain** : Revisit
 Only migrate what make sense.
- **Repurchase** :
  hosting [SaaS](https://en.wikipedia.org/wiki/Software_as_a_service) for zero maintenance.

## Cloud Architecture Best practices :

### Design for failure an nothing fails :

- multiple instances
- multiple AZ
- seperate a server to multiple servers with single functionalities

### Built Security in every layer :

- 