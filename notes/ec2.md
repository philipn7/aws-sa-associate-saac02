# Elastic Compute Cloud (EC2)

## Architecture and Resilience
- ![](images/Pasted%20image%2020211115202303.png)
- REMEMBER: EC2 is AZ resilient:
- ![](images/Pasted%20image%2020211115202855.png)
- ![](images/Pasted%20image%2020211115203049.png)
- In general, pick EC2 as the default and others only for specific requirements.

## Instance Types
- For exam questions revolving choosing the best type for a situation.
- ![](images/Pasted%20image%2020211115203601.png)
- ![](images/Pasted%20image%2020211115203734.png)
- Naming: (focus on Instance Family)
![](images/Pasted%20image%2020211115204017.png)
- ![](images/Pasted%20image%2020211115204121.png)

## Storage
- Ephemeral vs Persistent storage (EC2 store vs EBC)
- ![](images/Pasted%20image%2020211115205851.png)
- ![](images/Pasted%20image%2020211115210134.png)
- Need to know IO Size, IOPS, Throughput values of storage types to answer exam questions

## EBS (Elastic Block Store)
- Block Storage - raw disk allocations. Instances see block device and create file system on this device (ext2/4, ntfs)
- **Storage is provisioned on ONE AZ (AZ Resilient)** EBS in one AZ is different than in another AZ.
- EBS can be detached/attached, not lifecycle linked to one instance. Persistent

## EBS Volume Types
- General Purpose SSD - GP2
- IO Credit Bucket as currency to use IPOPS
 ![](images/Pasted%20image%2020211115211942.png)
- GP3 is a newer price model. Not currently default, but is cheaper for almost all cases.
- Provisioned IOPS SSD (io1/2) - can adjust IOPS independantly of size. Consistant low latency and up to 4x IOPS per volume of GP2/3
- **MEMORIZE: Don't need to remember exact numbers, but need to know the ranges and comparison**
![](images/Pasted%20image%2020211115212701.png)
- HDD-Based
![](images/Pasted%20image%2020211115212948.png)

## Instance Store Volume
- **Must attach at launch time. Can't add later. You can with EBS though.**
- An instance store provides **temporary** block-level storage for your instance. This storage is located on disks that are physically attached to the host computer (**Local on EC2 Host**).
- **Lost on instance move, resize, or hardware failure**
- Benefit is higher IOPS vs EBS
![](images/Pasted%20image%2020211115213643.png)

## Choosing between Instance Store vs EBS
- **Need to remember all these:**
- ![](images/Pasted%20image%2020211115214050.png)
- ![](images/Pasted%20image%2020211115214505.png)
