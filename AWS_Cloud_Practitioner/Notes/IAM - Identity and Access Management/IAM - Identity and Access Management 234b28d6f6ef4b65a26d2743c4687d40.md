# IAM - Identity and Access Management

Created: Oct 28, 2020 1:14 PM

- Global Service
- Root accout created by default (shouldn't be shared or used)
- Users are people within an organization
- Users can belong to multiple groups
- **Permissions -** Users or Groups can be assigned JSON documents called **policies**
- In AWS, you apply **the least privilege principle: don't give more permissions than a user needs**
- **Add Tags allows you to mark users & give them attributes**
- Multi Factor Authentication - MFA
    - You want to protect your Root Accounts and IAM Users
    - MFA = password **you know** + security device **you own**
    - **Benefit: even if password is stolen or hacked, the account is not compromised because *the hacker needs to physical device to preform a successful login***
    - **MFA devices options in AWS**
        - Virtual MFA device ( google authenticator {phone} or Authy {multi-device} )
        - Universal 2nd Factor Security Key (physical device)
        - Hardware Key Fob MFA Device
        - Hardware Key Fob MFA Device for AWS GovCloud (US)
    - When you log in with MFA activated, once you put your password in. You'll be greeted with a MFA code page. This is where you would go to you Authy app and submit that code into it.

- 3 ways to access AWS:
    - AWS Management Console ( protected by password + MFA)
    - AWS Command Line Interface (CLI): protected by access keys
    - AWS Software Development Kit (SDK) - for code: protected by access keys
        - **don't ever share your access keys.**
- Do not use your **root accout** to create security credentials

```bash
aws configure

# will be asked to fill AWS Access Key ID, Secret Access Key, region name, and output format.

aws iam list-users # Will show all the users in the account
```

## IAM Roles for Services

- Some services will need to preform actions on your behalf, so you'll have to provide permissions to the **AWS Services** with **IAM Roles**
- If you have given permissions for an EC2 instance to access AWS, this would be the typical flow

![IAM%20-%20Identity%20and%20Access%20Management%20234b28d6f6ef4b65a26d2743c4687d40/Untitled.png](IAM%20-%20Identity%20and%20Access%20Management%20234b28d6f6ef4b65a26d2743c4687d40/Untitled.png)

- Very common services that use roles are EC2 instances (virtual servers) and Lambda functions.

## IAM Security Tools

- IAM Credentials Report (account-level)
- IAM Access Advisor (user-level)
    - you can see what permissions were granted and when they were used
    - you can revise policies by using this information

## IAM Guidelines & Best Practices

- **Don't use root account except for AWS account setup**
- One physical user = One AWS user
- Assign users to groups and assign permissions to groups
- Create a strong password policy
- Use and enforce the use of MFA
- Create and use **Roles** for giving permissions to AWS Services
- Use Access Keys for Programmatic Access (CLI/SDK)
- Audit permissions of your account with the **IAM Credentials Report**
- Never share IAM users & Access Keys

## Shared Responsibility Model for IAM

- AWS is responsible for all the infrastructure but you are responsible for how you use it

![IAM%20-%20Identity%20and%20Access%20Management%20234b28d6f6ef4b65a26d2743c4687d40/Untitled%201.png](IAM%20-%20Identity%20and%20Access%20Management%20234b28d6f6ef4b65a26d2743c4687d40/Untitled%201.png)

## IAM Section - Summary

- Users: mapped to a physical user
- Groups: contains users only
- Policies: JSON documents that will outline permission for users & groups
- Roles: permissions for AWS services such as EC2 instance
- Security: enable MFA + password policy
- Access Keys: access AWS using CLI or SDK if you need to program something
- Audit: IAM Credential Reports (**lists all your account's users and the status of their various credentials)** & IAM Access Advisor ( **shows the service permissions granted to a user & when they were last accessed )**