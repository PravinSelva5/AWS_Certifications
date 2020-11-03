# EC2 - Instance Storage Section

Created: Nov 2, 2020 4:45 PM

## EBS Volume

- Elastic Block Store Volume is a **network drive** you can attach to your instances while they run
- It allows you to maintain data even after you terminate.
- **They can only be mounted to on instance at a time.**
- They are bound to a **specific availability zone**
    - **to move a volume across, you first need to snapshot it**
- You need to provision capacity

## EBS Snapshots

- Make a backup of your EBS volume at a point in time. **It's recommended to detach volume to do a snapshot.**

## AMI Overview

- AMI = Amazon Machine Image
    - you add your own software configurateion, OS, monitoring, etc.
    - Faster boot/config time
- AMI are built for a **specific region**
- You can launch EC2 instances from:
    - **A Public AMI:** AWS provided
    - **Your own AMI:** you make and maintain them yourself
    - **An AWS Marketplace AMI:** an AMI someone else made ( and potentially sells)

## EC2 Instance Store

- **If you need a high-performance hardware disk, use EC2 Instance Store.**
    - Better I/O performance
    - EC2 Instance Store lose their storage if they're stopped ( aka ephemeral)
        - Good use case:
            - buffer, cache, scratch data, temporary content
        - **Can't be used for long-term storage, EBS is better**
        - Risk of data loss if **hardware fails. Therefore Backups and Replication is the user's responsibility**

## Elastic File System (EFS)

- Managed **NFS, Network File System** that can be mounted on 100s of EC2
- Works with Linux EC2 instances in multi-AZ.
- It's highly available, scalable, expensive ( 3x gp2), pay per use, no capacity planning

![EC2%20-%20Instance%20Storage%20Section%20f2cc69703c32465ba5b9c5400e7dc29b/Untitled.png](EC2%20-%20Instance%20Storage%20Section%20f2cc69703c32465ba5b9c5400e7dc29b/Untitled.png)

## EBS vs EFS

- You use a mount target so everyone can see the same files through the EFS.

![EC2%20-%20Instance%20Storage%20Section%20f2cc69703c32465ba5b9c5400e7dc29b/Untitled%201.png](EC2%20-%20Instance%20Storage%20Section%20f2cc69703c32465ba5b9c5400e7dc29b/Untitled%201.png)

## Shared Responsibility Model for EC2 Storage

![EC2%20-%20Instance%20Storage%20Section%20f2cc69703c32465ba5b9c5400e7dc29b/Untitled%202.png](EC2%20-%20Instance%20Storage%20Section%20f2cc69703c32465ba5b9c5400e7dc29b/Untitled%202.png)

## EC2 Instance Storage - summary

- EBS volumes:
    - network drives  attached to **one EC2 instance at a time**
    - Mapped to an Availability Zone
    - Can use EBS Snapshots for backups / transferring EBS volumes across AZ
- AMI
    - create ready-to-use EC2 instances with our customizations
- EC2 Instance Store:
    - High performance hardware disk attached to our EC2 instance
    - Lost if our instance is stopped/terminated
- EFS
    - network file system, can be attached to 100s of instances in a region.