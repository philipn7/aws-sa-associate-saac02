# Virtual Private Cloud
## Subnets
![](images/Pasted%20image%2020211105185855.png)
Not required for the exam to calculate CIDR. Helpful to know these ranges.

## Custom VPCs - DNS
Two critical options for DNS in VPC:
- 'enableDnsHostnames' - Gives instances DNS Names. Indicates whether public IP addresses in a VPC are given public DNS hostnames.
- 'enableDnsSupport' - enables DNS resolution in VPC. If enabled, instances in VPC can use the DNS IP address.
If question is about issues. These are the two options to look at.
- Min /28 (16 IPs)  Max /16 (65,536 IPs)
- ![](images/Pasted%20image%2020211113191043.png)

## VPC Subnets
- A subnet is only on 1 AZ. An AZ can have zero or more subnets in it. **A subnet is created in an AZ and can't be created in another.**
- CIDR that a SUBNET uses can not overlap with any other subnets in that VPC. **Non overlapping subnets.**

## Router, Gateway, Bastion
- **EXAM:** Route tables are attached to zero or more subnets. A subnet MUST have a route table (Main VPC table or custom table.). Local routes are always there and match the IP range of the subnet. Higher prefix values are more specific and take higher priority (local always has higher priority though)
- Internet Gateway is **Regionally** resilient. Meaning, don't need a gateway per AZ. One gateway is enough for all AZ.
- For IPv4, **public IP is NOT configured in the OS**. It's part of the Internet Gateway. So the instance will only see local. Just like a home network.
- Bastion/Jumpbox are entry points for highly secure Private VPC.

##  Stateful vs Stateless