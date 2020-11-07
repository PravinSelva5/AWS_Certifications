# Leveraging the AWS Global Infrastructure

Created: Nov 6, 2020 1:24 PM

## Why Global Applications?

- A global application is an application that is deployed in multiple geographies, such as **Regions** and/or **Edge Locations**
- **Decreased Latency**
    - time it takes for a network packet to reach a server
- **Disaster Recovery (DR)**
    - You can fail over to another region and have your application still working
- **Attack Protection**
    - distributed global infrastructure is harder to attack

## Route 53

- Managed DNS
- DNS is a collection of rules and records which help clients understand how to reach a server through URLs

![Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled.png](Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled.png)

![Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%201.png](Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%201.png)

- Routing Policies
    - **Simple Routing Policy**
        - No health checks

        ![Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%202.png](Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%202.png)

    - **Weighted Routing Policy**
        - traffic is distributed through many EC2 instances

        ![Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%203.png](Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%203.png)

    - **Latency Routing Policy**
        - looks at where the user is located and route the user's request to the closest server
    - **FailOver Routing Policy**
        - Helps with Disaster Recovery situations where there is a Failover EC2 instance

        ![Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%204.png](Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%204.png)

- Route 53 costs $12 a year for the domain & 0.50 per month for the hosted zone

## CloudFront

- Content Delivery Network (CDN)
- improves read perfomance, content is cached at the edge
- improvers users experience
- 216 point of presence globally
- DDoS protection,integration with Shiled & AWS Web Application Firewall
- CloudFront at a High Level

![Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%205.png](Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%205.png)

## S3 Transfer Acceleration

![Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%206.png](Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%206.png)

## AWS Global Accelerator

- Improve global application **availability** and **performance** using the AWS global network
- **2 Anycast IP** are created for your application and traffic is sent through **Edge Locations**

![Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%207.png](Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%207.png)

![Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%208.png](Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%208.png)

## Leveraging the AWS Global Infrastructure

![Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%209.png](Leveraging%20the%20AWS%20Global%20Infrastructure%20780e6143d154467494767a469d0f958f/Untitled%209.png)

## Questions & Answers

1. Weighted Routing Policy is used to route traffic to multiple resources in proportions that you specify.
2. Amazon S3 Transfer Acceleration enables fast, easy, and secure transfers of files over long distances between your client and an S3 bucket. Transfer Acceleration takes advantage of Amazon CloudFront’s globally distributed edge locations. As the data arrives at an edge location, data is routed to Amazon S3 over an optimized network path.
3. CloudFront uses Edge Location to cache content, and therefore bring more of your content closer to your viewers to improve read performance.
4. A global application is not specifically used to scale elastically on demand. You can use Auto Scaling Groups for example if you want to elastically scale based on demand.
5. Route 53 features are (non exhaustive list): Domain Registration, DNS, Health Checks, Routing Policy
6. You can use AWS WAF web access control lists (web ACLs) to help minimize the effects of a distributed denial of service (DDoS) attack. For additional protection against DDoS attacks, AWS also provides AWS Shield Standard and AWS Shield Advanced.