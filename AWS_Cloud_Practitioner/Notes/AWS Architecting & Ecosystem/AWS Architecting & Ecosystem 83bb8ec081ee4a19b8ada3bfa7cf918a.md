# AWS Architecting & Ecosystem

Created: Nov 8, 2020 8:53 PM

## AWS WhitePapers Well-Architected Framework

- Stop guessing your capacity needs (Auto Scaling)
- Test  systems at production scale
- Automate to make architectural experimentation easier
- Allow for evolutionary architectures
    - Design based on changing requirements
- Drive architectures using data
- Improve through game days
    - Simulate applications for flash sale days

```
AWS CLOUD BEST PRACTICES - DESIGN PRINCIPLES

- Scalability: vertical & horizontal
- Disposable Resources: servers should be disposable & easily configured
- Automation: Serverless, Infrastructure as a Service, Auto Scaling
- Loose Coupling: 
				- **Monolith** are applications that do more and more over time, become bigger
				- Break it down into smaller, loosely coupled components
				- A change or a failure in one component **should not cascade to other components**
- Services, not Servers:
				- Don't use just EC2
				- think about which managed services, databases, you should use.
```

> There are 5 Pillars to a **well architected framework: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization.                      *They are not something to balance, or trade-offs, they're a synergy.***

## 1st pillar: Operational Excellence

- Perfom operations as code - Infrastructure s code
- Annote documentation ( made after every build)
- Make freqPerformance Efficiency design principles include: democratize advanced technologies, go global in minutes, use serverless architecture, experiment more often, mechanical sympathy.uent, small, reversible changes
- Refine operations procedures frequently
- **Anticipate failure**
- **Learn from all operational failures**

### Operational Excellence with AWS Services

![AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled.png](AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled.png)

## 2nd pillar: Security

- ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies

```
DESIGN PRINCIPLES

- Implement a strong identity foundation
- Enable traceability
- Apply security at all layers
- Automate security best practices
- Protect data in transit and at rest
- Keep people away from data
- Prepare for security events
```

![AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled%201.png](AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled%201.png)

## 3rd pillar: Reliability

- Ability of a system to recover from **infrastructure or service disruptions**, **dynamically acquire computing resources to meet demand**, and **mitigate disruptions** such as misconfigurations or transient network issues

```
------------------
DESIGN PRINCIPLES
------------------
- Test recovery procedures
- Automatically recover from failure
- Scale horizontally to increase system availability
- Stop guessing capacity
- Manage change in automation
```

![AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled%202.png](AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled%202.png)

## 4th Pillar: Performance Efficiency

- Includes the ability to use computing resources efficiently to meet system requirements, and to maintain that efficiency as demand changes and technologies evolve

```
DESIGN PRINCIPLES

- Democratize advanced technologies
- Go global in minutes
- Use serverless architectures
- Experiment more often
- Mechanical sympathy
```

![AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled%203.png](AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled%203.png)

## 5th Pillar: Cost Optimization

- Includes the ability to run systems to deliver business value at the lowest price point

```
DESIGN PRINCIPLES

- Adopt a consumption mode ( Pay for only what you use )
- Measure overall efficiency ( use CloudWatch)
- Stop spending money on data center operations
- Analyze and attribute expenditure ( use tags )
- Use managed and application level services to **reduce cost of ownership** 
		- As managed services operate at cloud scale, they can offer a lower cost
			per transaction or service
```

![AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled%204.png](AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled%204.png)

## AWS Ecosystem

- Free Resources
    - AWS Blogs
    - AWS Forums
    - AWS Whitepapers & Guides
    - AWS Quick Starts
    - AWS Solutions
- AWS Support

![AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled%205.png](AWS%20Architecting%20&%20Ecosystem%2083bb8ec081ee4a19b8ada3bfa7cf918a/Untitled%205.png)

## Questions & Answers

1. Auto Scaling in EC2 allows you to have the right number of instances to handle the application load. Auto Scaling in DynamoDB automatically adjusts read and write throughput capacity, in response to dynamically changing request volumes, with zero downtime. These are both examples of horizontal scaling.
2. Performance Efficiency design principles include: democratize advanced technologies, go global in minutes, use serverless architecture, experiment more often, mechanical sympathy.
3. This is a distractor. This type of AWS Partner Network does not exist. It is made up with words related to the AWS Partner Network.
4. Testing recovery procedures, stopping guessing capacity, and managing changes in automation are design principles of Reliability. Performance Efficiency design principles include: democratize advanced technologies, go global in minutes, use serverless architecture, experiment more often, mechanical sympathy.
5. CloudFormation is a key service to Operational Excellence as it prepares, operates, and evolves, but also performs operations as code.
6. Better fault tolerance is NOT a vertical scaling limit, This is an advantage of horizontal scaling.
7. AWS Cost Explorer and AWS Trusted Advisor are Cost Optimization services examples. It also includes AWS Budgets, Cost and Usage Reports, etc.
8. The Security pillar includes the ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies.