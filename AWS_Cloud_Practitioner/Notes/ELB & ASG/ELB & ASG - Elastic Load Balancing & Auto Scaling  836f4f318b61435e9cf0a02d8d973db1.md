# ELB & ASG - Elastic Load Balancing & Auto Scaling Groups

Created: Nov 3, 2020 11:50 AM

- There are two types of scalability:
    - Vertical Scalability
        - increase the size of the instance ( scale up/down)
        - very common for distributed systems, such as a database
        - there is usually a limit depending on the hardware
    - Horizontal Scalability ( = elasticity)
        - increasing the number of instances/systems
        - you need **distributed systems**
        - very common for web applications/modern applications
        - You can use Auto Scaling Group or Load Balancer to accomplish this
- High availability means you are running your application/system in at least 2 Availability Zones

## Scalability vs Elasticity (vs Agility)

- **Scalability:** ability to accomodate a larger load by making the hardware stronger (scale up), or by adding nodes ( scale out)
- **Elasticity:** once a system is scalable, elasticity means that there will be some "auto-scaling" so that the system can scale based on the load. This is "cloud-friendly": **pay-per-use, match demand, optimize costs.**
- **Agility: (*not related to scalability - distractor)*** new IT resources are only a click away, which means that you reduce the time to make those resources available to your developers from weeks to just minutes.

## Elastic Load Balancing

- Load balancers are servers that forward internet traffic to multiple servers downstream
- Why use a load balancer?
    - Spread load across multiple downstream instances
    - Expose a single point of access(DNS) to your application
    - Seamlessly handle failures of downstream instances
    - Do regular health checks to your instances
    - Provide SSL termination (HTTPS) for your websites
    - High availability across zones
- AWS provides 3 types of load balances:
    - Application Load Balancer (HTTP/HTTPS only) - Layer 7
    - Network Load Balancer (ultra-high performance, allows for TCP) - Layer 4
    - Classic Load Balancer (slowly retiring) - Layer 4 & 7

![ELB%20&%20ASG%20-%20Elastic%20Load%20Balancing%20&%20Auto%20Scaling%20%20836f4f318b61435e9cf0a02d8d973db1/Untitled.png](ELB%20&%20ASG%20-%20Elastic%20Load%20Balancing%20&%20Auto%20Scaling%20%20836f4f318b61435e9cf0a02d8d973db1/Untitled.png)

## What's an Auto Scaling Group?

- The goal of an Auto Scaling Group is to :
    - **Scale out (** add EC2 instances ) to match an **increased load.**
    - **Scale in (** remove EC2 instances ) to match a decreased load.
    - Ensure we have a minimum and a maximum number of machines running
    - Automatically register new instances to a load balancer
    - **Replace unhealthy instances**
- Cost Savings: **only run at an optimal capacity**

![ELB%20&%20ASG%20-%20Elastic%20Load%20Balancing%20&%20Auto%20Scaling%20%20836f4f318b61435e9cf0a02d8d973db1/Untitled%201.png](ELB%20&%20ASG%20-%20Elastic%20Load%20Balancing%20&%20Auto%20Scaling%20%20836f4f318b61435e9cf0a02d8d973db1/Untitled%201.png)

## Auto Scaling Group in AWS with Load Balancer

![ELB%20&%20ASG%20-%20Elastic%20Load%20Balancing%20&%20Auto%20Scaling%20%20836f4f318b61435e9cf0a02d8d973db1/Untitled%202.png](ELB%20&%20ASG%20-%20Elastic%20Load%20Balancing%20&%20Auto%20Scaling%20%20836f4f318b61435e9cf0a02d8d973db1/Untitled%202.png)

- Set up EC2 launch templates before setting up Auto Scaling Groups
- When you **create a Auto Scaling Group, make sure you choose all the Subnets available so that the group is highly available.**
- Choose ELB for Health Checks, so that instances are **replaced when unhealthy.**
- If you delete an instance, Auto Scaling will automatically recreate the instance
- You need to delete the auto scaling group if you want to delete the EC2 instances.
- You can go to Load Balancers tab to terminate it as well

## Questions

- A Network Load Balancer can handle millions of requests per second with low-latency. It operates at Layer 4, and is best-suited for load-balancing TCP, UDP, and TLS traffic with ultra high-performance.
- Auto Scaling Groups can add or remove instances, **but from the same type**. The cannot change the EC2 Instances Types on the fly.
- Load Balancers **cannot help with back-end autoscaling.** You should us **Auto Scaling Groups.**