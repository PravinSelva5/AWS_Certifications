# VPC & Networking

Created: Nov 7, 2020 5:29 PM

## VPC - Virtual Private Cloud, Subnet, Internet Gateway & NAT Gateways

- VPC - private network to deploy your resources
- **Subnets - allow you to partition your netowrk inside your VPC**
- Public Subnet - subnet is accessible from the internet
- Private Subnet - not accessible from the internet
- **Route Tables** are used to define access to the internet & between subnets

![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled.png)

- **Internet Gateways** helps our VPC instances connect with the internet
- **Public Subnets** have a route to the internet gateway
- **NAT Gateways** ( AWS-managed) & **NAT Instances** (self-managed) allow your instances in your **Private Subnets** to access the internet while remaining private

![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%201.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%201.png)

- **CIDR** refers to the blocks of IP addresses available

## Security Groups & Network Access Control List (NACL)

- **NACL**
    - firewall which controls traffic from and to subnet
    - can ALLOW and DENY rules
    - are attached at teh subnet level and rules only include IP addresses

    ![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%202.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%202.png)

- **Security Groups**
    - A firewall that controls traffic to and from **an ENI / an EC2 Instance**
    - Can only have ALLOW rules
    - Rules include IP addresses and other security groups

    ![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%203.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%203.png)

![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%204.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%204.png)

## VPC Flow Logs & VPC Peering

- IP traffic going into your interfaces can be logged:
    - VPC flow logs
    - Subnet flow logs
    - Elastic Network Interface flow logs
- Helps to monitor & troubleshoot connectivity issues
    - Subnets to internet
    - Subnets to subnets
    - Internet to subnets
- Connect two VPC, privately using AWS' network is called **VPC Peering**
    - It'll make them behave as if they were in the same network
    - Must not have  **overlapping**
    - VPC Peering connection **is not transitive ( *must be established for each VPC that need to communicate with on another* )**

## VPC Endpoints - Interface & Gateway (S3 & DynamoDB)

- Endpoints allow you to connect to AWS Services **using a private network** instead of the public www network
- better security and low latency with endpoints
- **VPC Endpoint Gateway is ONLY to connect to S3 and Dynamo DB**
- **VPC Endpoint Interface is used to CONNECT to the rest**

![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%205.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%205.png)

![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%206.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%206.png)

## Direct Connect & Site-to-Site VPN

![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%207.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%207.png)

- Because site-to-site goes over the public internet, you may have bandwidth and security issues even though the connection is **automatically encrypted**
- **Direct Connect (DX)**
    - establish a physical connection between on-premises and AWS
    - The connection is private, secure and fast
    - **Goes over a private network**

    ![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%208.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%208.png)

    - It takes a month to establish but is **faster, more secure, and more reliable**
    - **ON THE EXAM**
        - Ask yourself two questions when deciding which one to use
            - Does it need to be private or not?
            - Does it need to be established fast or not?
    - Site-to-Site VPN
        - **On-premises side: MUST USE A CUSTOMER GATEWAY (CGW)**
        - **AWS side**: **MUST USE A VIRTUAL PRIVATE GATEWAY (VGW)**

        ![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%209.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%209.png)

## Transit Gateway

- This service allows you to have transitive peering between thousands of VPC and on-premises, hub-and-spoke (star) connection
- One single Gateway to provide this functionality
- **Works with Direct Connect Gateway, VPN connections**

![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%2010.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%2010.png)

## Summary

![VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%2011.png](VPC%20&%20Networking%20000e99d239b94bacbde0f8d707f2ffff/Untitled%2011.png)

## Questions & Summary

1. NAT Gateways allow your instances in your private subnets to access the Internet while remaining private, and are managed by AWS.
2. A public subnet is accessible from the Internet while a private subnet is not accessible from the Internet.
3. A network access control list (NACL) is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets. They have both ALLOW and DENY rules.
4. Transit Gateway connects thousands of VPC and on-premises networks together in a single gateway.
5. VPC Peering connection is a networking connection between two VPCs using AWS' network.
6. A virtual private cloud (VPC) is a virtual network dedicated to your AWS account. It is logically isolated from other virtual networks in the AWS Cloud. You can launch your AWS resources, such as Amazon EC2 instances, into your VPC.
7. AWS Direct Connect is a cloud service solution that makes it easy to establish a dedicated private network connection from your premises to AWS.
8. An internet gateway is a horizontally scaled, redundant, and highly available VPC component that allows communication between your VPC and the internet.