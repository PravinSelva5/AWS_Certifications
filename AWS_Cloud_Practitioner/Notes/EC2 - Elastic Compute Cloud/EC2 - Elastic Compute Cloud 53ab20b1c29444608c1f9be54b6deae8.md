# EC2 - Elastic Compute Cloud

Created: Oct 28, 2020 1:14 PM

- EC2 = Elastic Compute Cloud = Infrastructure as a Service
- It mainly consists of:
    - Renting virtual machines (EC2)
    - Storing data on virtual drives (EBS)
    - Distributing load across machines (ELB)
    - Scaling the services using an auto-scaling group (ASG)
- **AMI - Amazon Machine Image** contains the software configuration such as OS, application server, and applications **required to launch your instance**

## Security Groups & Classic Ports

- Security Groups control how traffic is **allowed** into or out of our EC2 instances.
- Security groups rules can **reference by IP or by security group**

![EC2%20-%20Elastic%20Compute%20Cloud%2053ab20b1c29444608c1f9be54b6deae8/Untitled.png](EC2%20-%20Elastic%20Compute%20Cloud%2053ab20b1c29444608c1f9be54b6deae8/Untitled.png)

- **Classic Ports to know**
    - 22 = SSH (Secure Shell) - log into a Linux instance
    - 21 = FTP (File Transport Protocol) - upload files into a file share
    - 22 = SFTP (Secure File Transport Protocol) - upload files using SSH
    - 80 = HTTP - access unsecured websites
    - 443 = HTTPS - access secured websites
    - 3389 = RDP ( Remote Desktop Protocol) - log into a Windows instance
- Source
    - HTTP - 0.0.0.0/0 -  **Everywhere in IPv4 is allowed**
    - HTTP - ::/0 - **Everywhere in IPv6 is allowed**

## SSH Summary Table

![EC2%20-%20Elastic%20Compute%20Cloud%2053ab20b1c29444608c1f9be54b6deae8/Untitled%201.png](EC2%20-%20Elastic%20Compute%20Cloud%2053ab20b1c29444608c1f9be54b6deae8/Untitled%201.png)

## SSH using Linux or Mac

- SSH allows you to control a remote machine, all using the command line.
- **If you get a permission error when trying to connect with your AMI server, `chmod 0400` , command will set permissions so that:**
    - (U)ser / owner can read, can't write and can't execute. (G)roup can't read, can't write and can't execute. (O)thers can't read, can't write and can't execute.
    - And then execute `ssh -i keyName.pem ec2-user@ipaddress`

## SSH TroubleShooting

- **There's a connection timeout**
    - Security group issue. Any timeout is related to security groups or a firewall. Make sure EC2 is like this:

    ![EC2%20-%20Elastic%20Compute%20Cloud%2053ab20b1c29444608c1f9be54b6deae8/Untitled%202.png](EC2%20-%20Elastic%20Compute%20Cloud%2053ab20b1c29444608c1f9be54b6deae8/Untitled%202.png)

- **If there still is a connection issue:**
    - A personal or corporate firewall is blocking the connection
- **If SSH doesn't work with windows, then you need to use Putty.**
- **If there's a connection refused**
    - instance is reachable but no SSH utility is running on the instance.
    - **Restart the instance**
    - If it doesn't work, **terminate the instance,** and create a new one. Make sure you're using **Amazon Linux 2.**
- **Permission Denied (publickey,gssapi-keyex,gssapi-with-mic)**
    - Two possibilities:

        ```
        1. You are using the wrong security key or not using a security key. 
           Please look at your EC2 instance configuration to make sure you have assigned the correct key to it.

        2. You are using the wrong user. 
        	 Make sure you have started an Amazon Linux 2 EC2 instance, and make sure you're using the user ec2-user. 
           This is something you specify when doing ec2-user@<public-ip> (ex: ec2-user@35.180.242.162) in your SSH command or your Putty configuration
        ```

- **Nothings working?!?!?!?!?!?!**
    - Use **EC2 Instance Connect**
- **I was able to connect yesterday, but today I can't**
    - You probably stopped your EC2 instance and then restarted it. The IP would have changed. Make sure the public IP you're using is the same as the instance
- **If nothing works, it's okay, try using the GUI.**

## EC2 Instance Roles Demo

- NEVER RUN `aws configure` on an EC2 instance

## EC2 Instance Launch Types

- EC2 Instances Purchasing Options
    - On-Demand Instances
        - short-workload, predictable pricing
        - Linux - **billing per second, after the first minute**
        - All other OS' are **billed per hour**
    - Reserved
        - 75% discount vs On-demand
        - Reservation Period: 1 year | 3 years
        - Purchasing Options: no upfront | partial upfront | All upfront (more discount)
        - Reserve a specific instance type
        - Recommended for steady-stae usuage applications (think database)
        - **Convertible Reserved Instance**
            - up to 54% discount
            - can change the EC2 instance type
        - **Scheduled Reserved Instances**
            - launch within time window you reserve
            - when you require a fraction of day / week / month
            - still commitment of 1 to 3 years
    - Spot Instances
        - 90% discount vs on-demand
        - **you can lose them at any time if your MAX PRICE is less than the current SPOT PRICE**
        - Useful for workloads that are resilent to failure
            - Batch Jobs
            - Data analysis
            - Image processing
            - Any **distributed** workloads
            - Workloads with a flexible start and end time
    - Dedicated Hosts
        - entire physical server is dedicated to your use. Dedicated Hosts can help you address  **compliance requirements & reduce costs by allowing you to use your existing server-bound software licenses.**
        - 3 year reservation period & expensive
        - useful for companies with strong regulatory & compilance needs
        - **There are dedicated instances for individual users**

        ![EC2%20-%20Elastic%20Compute%20Cloud%2053ab20b1c29444608c1f9be54b6deae8/Untitled%203.png](EC2%20-%20Elastic%20Compute%20Cloud%2053ab20b1c29444608c1f9be54b6deae8/Untitled%203.png)

        ## Shared Responsibility Model for EC2

        ![EC2%20-%20Elastic%20Compute%20Cloud%2053ab20b1c29444608c1f9be54b6deae8/Untitled%204.png](EC2%20-%20Elastic%20Compute%20Cloud%2053ab20b1c29444608c1f9be54b6deae8/Untitled%204.png)

        ## EC2 Section - Summary

        - **EC2 Instance**: AMI (OS) + Instance Size (CPU + RAM) + Storage + security groups + EC2 User Data
        - **Security Groups:** Firewall attached to the EC2 instance
        - **EC2 User Data:** Script launched at the first start of an instance
        - **SSH:** start a terminal into our EC2 Instances (port 22)
        - **EC2 Instance Role:** link to IAM roles
        - **Purchasing Options:**
            - On-Demand
            - Spot
            - Reserved (Standard + Convertible + Scheduled)
            - Dedicated Host
            - Dedicated Instance