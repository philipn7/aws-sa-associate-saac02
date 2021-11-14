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
- ![](images/Pasted%20image%2020211113204753.png)
- Every connection has a request/response and depending on perspective, can be inbound/outbound. StateLESS firewalls needs config for all 4 combinations of this...
- ![](images/Pasted%20image%2020211113204942.png)

## NACL
- Stateless rules. Processed in order by LOWEST rule number. There is an implicit DENY * rule if nothing else matches.
- ![](images/Pasted%20image%2020211113205921.png)

## Security Groups (SG)
- STATEFUL. Can't use SG to block IPs. ***NO EXPLICIT DENY*** SG can only ALLOW traffic.
- Use SG in conjunction with NACL.
- ![](images/Pasted%20image%2020211113210123.png)
- Cant attach SG to instance, it looks like you can, but actually attaching to primary network interface of that instance. ***Security Groups are attached to network interfaces of instances.***
- Logical References: Can reference for example, a security group as a source in a SG rule.

## Network Address Translation (NAT)
- Remap SRC or DST IPs.
- 'IP masquerading': hiding CIDR blocks behind one IP. Mapping many local IPs to one Public IP. Gives OUTGOING internet access.
- ![](images/Pasted%20image%2020211113211309.png)
- ![](images/Pasted%20image%2020211113211436.png)
- There are **two charging elements for NAT: hourly rate + GB rate**.
- NAT is AZ Resilient only. You need one NAT in each AZ unlike Internet Gateway.
- **Cannot use NAT GATEWAY for Bastion host because you can't connect to it's operating system **(comes up all the time on exams.)
- Whereas, NAT INSTANCES are basically EC2 instances and you can filter using NACL or SG
- ***GATEWAYS dont support SG, only NACL*** (comes up all the time)
- **NAT gateways DONT work with IPv6** (help rule out exam answers)

