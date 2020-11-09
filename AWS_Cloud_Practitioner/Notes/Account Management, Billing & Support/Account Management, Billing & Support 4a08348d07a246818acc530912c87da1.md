# Account Management, Billing & Support

Created: Nov 8, 2020 1:11 PM

## Organizations

- Global service
- allows to manage **multiple** **AWS accounts**
- the main account is the **master account**
- **Consolidated Billing** across all acounts - single payment method
- Pricing benefits from **aggregated usage**
- **Pooling of Reserved EC2 instances** for optimal savings
- API is available to **automate AWS account creation**
- **Restrict account privileges using Service Control Policies (SCP)**

![Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled.png](Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled.png)

![Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%201.png](Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%201.png)

## Pricing Models of the Cloud

- AWS 4 pricing models:
    - **Pay as you go**
    - **Save when you reserve**
    - **Pay less by using more**
    - **Pay less as AWS grows**

![Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%202.png](Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%202.png)

![Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%203.png](Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%203.png)

## Billing & Costing Tools

- **Estimating costs in the cloud**
    - TCO Calculator
    - Simple Monthly Calculator / Pricing Calculator
- **Tracking costs in the cloud**
    - Billing Dashboard
    - Cost Allocation Tags
    - Cost and Usage Reports
    - Cost Explorer
- **Monitoring against costs plans**
    - Billing Alarms
    - Budgets

## Estimating Costs in the Cloud - TCO Calculator (Deprecated)& Pricing Calculator

- Helps reduce costs by **reducing the need to invest in large capital expenditures & providing as pay as you go model**
- Compare cost of your applications in an **on-premises** or traditional hosting environment **to AWS: *Server, Storage, Network, IT Labor***

![Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%204.png](Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%204.png)

- Simple Monthly Calculator deprecated in June 30 2020 and **replaced with AWS Pricing Calculator**

## Tracking Costs in the Cloud

- Use **AWS Billing Dashboard** - **High level tool**
- **Cost Allocation tags** can be used to track your AWS costs on a detailed level. Tags are used for organizing resources.
    - AWS generated tags
    - User-defined tags
- Cost and Usage reports can be printed to **dive deeper into your AWS costs and usage.**
- **Cost Explorer,** is used to visualize, understand, and manage your AWS costs and usage over time. **You can forecast usage up to 3 months based on previous usage**

## Monitoring Costs in the Cloud

- Three types of budgets can be created:
    - Usage
    - Cost
    - Reservation
- Up to 5 SNS notifications per budget

## AWS Trusted Advisor

- It'll analyze your AWS accounts and provides recommendation:

![Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%205.png](Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%205.png)

- Core checks & recommendations are available for **all customers**
- Full Trsuted Advisor is avialble for **Business & Enterprise** support plans:
    - Ability to set Cloud Watch alarms when reaching limits
    - **Programmatic Access with AWS Support API**

## Support Plans for AWS

- **Basic Support**
    - free
    - 24x7 access to customer service
    - **AWS Trusted Advisor - access to the 7 core Trusted Advisor checks & guidance**
    - **AWS Personal Health Dashboard available**
- **Developer**
    - All Basic Support Plan
    - Business hours email access to Cloud Support Associates
    - Unlimited Cases/ 1 primary contact
    - Depending on the **case severity:**
        - General guidance: < 24 business hours
        - System impaired: < 12 business hours
- **Business**
    - Full set of checks with **Trusted Advisor**
    - **24x7 phone, email, and chat access** to Cloud Support Engineers
    - Unlimited cases/ unlimited contacts
    - Access to Infrastructure Event Management **for additional fee**
    - Depending on the **case severity:**
        - General guidance: < 24 business hours
        - System impaired: < 12 business hours
        - **Production system impaired: < 4 hours**
        - **Production system down: < 1 hour**
- **Enterprise**
    - inteded for **mission critical workloads**
    - All of Business Support Plan +
    - Access to a **Technical Account Manager (TAM)**
    - **Concierge Support Team**
    - **Infrastructure Event Management, Well Architected & Operations Reviews**
    - Depending on the **case severity:**
        - General guidance: < 24 business hours
        - System impaired: < 12 business hours
        - Production system impaired: < 4 hours
        - Production system down: < 1 hour
        - **Business-critical system down: < 15 minutes**

## Account Best Practices

![Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%206.png](Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%206.png)

## Billing Summary

![Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%207.png](Account%20Management,%20Billing%20&%20Support%204a08348d07a246818acc530912c87da1/Untitled%207.png)

## Questions & Answers

1. These services are free to use. Be careful, the resources created in Elastic Beanstalk (as well as in CloudFormation and Auto Scaling Groups) are not free
2. CloudFront pricing is different across different geographic regions.
3. When the upfront payment is higher, the discount is bigger.
4. Inbound data transfer in the S3 region is free.
5. AWS Trusted Advisor is an online tool that provides you real time guidance to help you provision your resources following AWS best practices, including performance, security, and fault tolerance, but also cost optimization and service limits.
6. AWS Organizations **does** **not** offer faster access to the AWS Support.
7. The added data storage by EBS Snapshots are added cost in GB per month to EBS pricing. Other EBS pricing factors are: Volume type, Provisioned storage volume, IOPS, etc.
8. Business Support Plan is the most cost-effective option that offers 24x7 phone, email, and chat support.
9. With Linux EC2 instances, you pay per second of compute capacity. There is also a minimum of 60s of use.
10. Reservations are available for EC2 Reserved Instances, DynamoDB Reserved Capacity, ElastiCache Reserved Nodes, RDS Reserved Instance, Redshift Reserved Nodes. Reservations allow you to minimize risks, predictably manage budgets and comply with long-term requirements.
11. The AWS Simple Monthly Calculator is an easy-to-use online tool that enables you to estimate their architecture solution monthly cost of AWS services for your use case based on your expected usage. It is being replaced by AWS Pricing Calculator.
12. The Enterprise Support Plan comes with a business-critical system down response under 15 minutes and offers access to a Technical Account Manager, as well as a Concierge Support Team. It is the only plan to have these features.
13. The TCO calculators allow you to estimate the cost savings when using AWS and provide a detailed set of reports that can be used in executive presentations.
14. Reserved Instances are good and more cost-effective (up to 69% discount compared to On-demand pricing, depending on the upfront) for long workloads. You can reserve instances for 1 or 3 years in RDS.
15. You can assign metadata to your AWS resources in the form of tags. Tags can help you manage, identify, organize, search for, and filter resources.
16. Cost Explorer can be used to forecast usage up to 3 months based on the previous usage. It can also be used to choose an optimal Savings Plan. Cost Explorer has an easy-to-use interface that lets you visualize, understand, and manage your AWS costs and usage over time.
17. AWS Budgets gives you the ability to set custom budgets that alert you when your costs or usage exceed (or are forecasted to exceed) your budgeted amount. **Difference with CloudWatch Billing Alarms: CloudWatch Billing Alarms only send alerts when your costs and usage are exceeding your budget, not when it is forecasted to exceed your budget, while AWS Budgets does both.**