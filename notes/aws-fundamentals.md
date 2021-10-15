# AWS Fundamentals
## Public vs Private Services
AWS public and private services are separated from each other. By default, private cannot connect to public services. S3 is an example of an AWS Public service. EC2 is private. 
![](images/Pasted%20image%2020211013145425.png)

## AWS Global Infrastructure
- AWS Regions have Full Compute, Storage, DB, AI, Analytics...
- AWS Edge locations are in relatively remote locations and are local distribution points without all the services.
For example, major services run on AWS regions while data is stored closer to users at edge locations.
- **Availability zone**: backup zones within a region itself. Region code ends with a, b, c...

## Virtual Private Cloud (VPC)
- Virtual network inside AWS. Regionally resilient. Private and isolated.
- **Max 1 VPC per region!** but many custom VPCs.
- How is it regionally resilient? The VPC CIDR is split inside the region into subnets, one for each Availability Zone.

## Elastic Compute Cloud EC2
- IAAS, Private, **AZ Resilient**, on demand billing, local storage or Elastic Block Store (EBS)
- **You still need to pay for storage even if EC2 is 'Stopped'**
- Amazon Machine Image (AMI): similar to an OS image you use for virtual machines. AMI is used to create the EC2 instance.

## Simple Storage Service (S3)
- Global Storage Platform - regional based and resilient, Public
- Objects can be thought of as files. Buckets as containers for objects.
![](images/Pasted%20image%2020211013163933.png)
- **Exam questions highlighted in orange**
![](images/Pasted%20image%2020211013164533.png)
![](images/Pasted%20image%2020211013164751.png)

## Cloud Formation
- Infrastructure as code (IaC) - allows automation of infrastructure through templates (YAML / JSON)
- **exam trick question**
![](images/Pasted%20image%2020211013174249.png)

## CloudWatch
- Collects and manages operational data. Metrics, Logs, Events. We used this service to set a billing alarm.
- namespace
- dimensions - extra distinguishing info for datapoints.o

## High-Availability, Fault-tolerance, Disaster recovery

## Domain Name System (DNS)
![](images/Pasted%20image%2020211015110333.png)
![](images/Pasted%20image%2020211015111249.png)
![](images/Pasted%20image%2020211015111120.png)

## Route53
- Register domains, Host Zones, managed nameservers
- 