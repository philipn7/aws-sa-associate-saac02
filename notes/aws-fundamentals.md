# AWS Fundamentals
## Public vs Private Services
AWS public and private services are separated from eachother. By default, private cannot connect to public services. S3 is an example of an AWS Public service. EC2 is private. 
![](images/Pasted%20image%2020211013145425.png)

## AWS Global Infrastructure
- AWS Regions have Full Compute, Storage, DB, AI, Analytics...
- AWS Edge locations are in relatively remote locations and are local distribution points without all the services.
For example, major services run on AWS regions while data is stored closer to users at edge locations.
- Availability zone: backup zones within a region itself. Region code ends with a, b, c...

## Virtual Private Cloud (VPC)
- Virtual network inside AWS. Regionally resilient. Private and isolated.
- Max 1 VPC per region! but many custom VPCs.
- How is it regionally resilient? The VPC CIDR is split inside the region into subnets, one for each Availability Zone.


