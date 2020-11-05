# Other Compute Services: ECS, Lambda, Batch, Lightsail

Created: Nov 5, 2020 4:06 PM

## What is Docker?

- software development platform to deploy apps
- Apps are packaged in **containers that can run on any OS**
- Apps run the same, regardless of where they're run
    - Any machine
    - No compatibility issues
    - Predictable behaviour
    - Less work
    - Easier to maintain and deploy
    - Works with any language, any OS, any technology
- **Scale containers up and down very quickly (seconds)**

![Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled.png](Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled.png)

- Docker images are stored in Docker repository

## Docker vs Virtual Machines?

- Docker is "sort of" a **virtualization technology,** but not exactly
- Resources are shared with the host ⇒ many containers on one server

![Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%201.png](Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%201.png)

## ECS, Fargate & ECR

- **ECS** = Elastic Container Service
    - lauch Docker containers on AWS
    - **You must provision & maintain the infrastructure ( the EC2 instances)**
- AWS takes care of starting/stopping containers
- Has integration with the **Application Load Balancer**
- "I want to run Docker containers on AWS" —> **Think of ECS**
- **Fargate**
    - Launch Docker containers on AWS
    - **You don't have to provision the infrastructure (no EC2 instances to manage, simpler!)**
    - **Serverless offering**
    - AWS just runs containers for you based on the CPU / RAM you need

![Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%202.png](Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%202.png)

## ECR

- Elastic Container Registry, **is used to store your Docker images.**
- Private Docker Registry on AWS.

![Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%203.png](Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%203.png)

## Serverless

- Developers don't have to manage servers anymore
- AWS Lambda pioneered severless but now also includes anything that's managed: "databases, messaging, storage, etc."
- Examples:
    - Amazon S3
    - DynamoDB
    - Fargate
    - Lambda

## Lambda

- Virtual **functions -** no servers to manage!
- Limited by time - **short executions**
- Run **on-demand**
- Scaling is automated

![Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%204.png](Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%204.png)

- Benefits:
    - Easy Pricing
        - Pay per request & compute time
    - Integrated with the whole AWS suite of services
    - **Event-Driven:** functions get invoked by AWS when needed
    - Integrated with many programming languages & **easy monitoring** with AWS Cloud Watch
    - **Easy to get more resources** per functions ( up to 3GB of RAM)
    - Increasing RAM imporves CPU & networking
- **Docker is not for AWS Lambda, it's for ECS/Fargate**

![Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%205.png](Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%205.png)

- Use Lambda's for short workloads (Timeout period)

## AWS Batch

- Fully managed **batch processing** at any scale
- A **"batch"** job is a job with a start and an end
- Batch will dynamically launch **EC2 Instances or Spot Instances**
- AWS Batch provisions the right amount of compute/memory
- **Batch jobs are defined as Docker images and run on ECS**
    - cost optimzations and focusing less on the infrastructure

    ![Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%206.png](Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%206.png)

## Batch vs Lambda

![Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%207.png](Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%207.png)

## Lightsail

- Virtual servers, storage, databases, and networking
- **Simpler alternative to using EC2, RDS, ELB, EBS, Route 53 ...**
- Use cases:
    - Simple web applications
    - Websites
    - Dev/Test environment
- Has high availability, no autoscaling, limited AWS integrations

## Other Compute - Summary

![Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%208.png](Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%208.png)

![Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%209.png](Other%20Compute%20Services%20ECS,%20Lambda,%20Batch,%20Lightsa%20cccf56a71fe4406eb806ff1b0fdf2a4e/Untitled%209.png)

## Questions & Answers

1. In AWS Lambda, you are charged per request and compute time, that's it.
2. Fargate allows you to launch Docker containers on AWS, and you don't need to provision and maintain the infrastructure (=no EC2 instances to manage). It is serverless
3. Amazon Lightsail is designed to be the easiest way to launch and manage a virtual private server with AWS. Lightsail plans include everything you need to jumpstart your project – a virtual machine, SSD- based storage, data transfer, DNS management, and a static IP address – for a low, predictable price. It can be used to create a simple web application, a website or a dev/test environment.
4. Docker is a software development platform that allows you to run applications the same way, regardless of where they are run. It can scale containers up and down within seconds.
5. "Event-driven" in Lambda means that functions are invoked when needed. They are triggered.
6. ECS allows you to launch Docker containers on AWS, but you must provision and maintain the infrastructure (i.e. EC2 instances).
7. Serverless does not mean that there are no servers, you just do not manage, provision and see them, but they do exist.
8. AWS Lambda doesn't have a "definition of a minimum and a maximum of EC2 Instances running". **This is a feature of Auto Scaling Groups, not AWS Lambda.**
9. AWS Batch enables developers, scientists, and engineers to easily and efficiently run hundreds of thousands of batch computing jobs on AWS. AWS Batch dynamically provisions the optimal quantity and type of compute resources (e.g., CPU or memory-optimized instances) based on the volume and specific resource requirements of the batch jobs submitted.
10. Elastic Container Registry (ECR) is a service where you store your Docker image so they can be run by ECS or Fargate.