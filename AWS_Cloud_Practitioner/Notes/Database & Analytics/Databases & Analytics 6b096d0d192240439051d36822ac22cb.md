# Databases & Analytics

Created: Nov 5, 2020 11:00 AM

## Database Introduction

- Relational Databases
    - Looks like Excel spreadsheets, with links between them
    - Can use SQL to preform queries/lookups
- NoSQL
    - non-relational databases
    - **NoSQL databases are purpose built for specific data models and have flexible schemas for building modern applications**
    - **Benefits:**
        - Flexibility: easy to evolve data model
        - Scalability: designed to scale-out by using distributed clusters
        - High-performance: optimized for a specifc data model
        - Highly functional: types optimized for the data model
    - Example:
        - **JSON (JavaScript Object Notation)** is a common form of data that fits into a NoSQL model
            - Data can be nested, fields can **change over time, support for new types such as arrays.**

## Databses & Shared Responsibility on AWS

![Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled.png](Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled.png)

## RDS & Aurora Overview

- RDS - Relational Database Service
    - SQL as query language
    - It allows you to create databases in the cloud that are managed by AWS:
        - **Postgres**
        - **MySQL**
        - **MariaDB**
        - **Oracle**
        - **Microsoft SQL Server**
        - **Aurora ( AWS Proprietary database)**

## RDS vs DB on EC2

- RDS is a **managed service:**
    - **Automated provisioning, OS patching**
    - **Continuous backups and restore to specific timestamp ( Point in Time Restore) !**
    - **Monitoring dashboards**
    - **Read replicas for improved read performance**
    - **Multi AZ setup of Disaster Recovery**
    - **Maintenance windows for upgrades**
    - **Scaling capability (vertical and horizontal)**
    - **Storage backed by EBS ( either gp2 or io 1)**
- Only problem is you won't be able to SSH into your instances

![Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled%201.png](Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled%201.png)

## Amazon Aurora

- Supports **PostgreSQL** and **MySQL**
- Cloud optimized, so there's a **5x** improvement over MySQL on RDS and over **3x** performance of Postgres on RDS
- Aurora Storage grows automatically in increments of **10GB, up to 64TB**
- **Aurora costs more than RDS, 20%, but is more efficient**
- Aurora isn't in the free tier but RDS is.
- *You can take snapshots of the current database and create a new one from that snapshot*

## Amazon ElastiCache

- used to get a managed Redis or Memcached
- Chaces are **in-memory databases** with high performance, low latency
- Helps reduce load off databases for read intensive workloads

![Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled%202.png](Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled%202.png)

### DynamoDB

- Fully managed highly available with replication across 3 availability zones
- **NoSQL database - not a relational database**
- Scales to massive workloads, distributed "**serverless"** database
- Millions of requests per seconds, trillions of rows, 100s of TB of storage
- **Fast and consistent in performance**
- ***Single-digit millisecond latency - low latency retrieval***
- Integrated with IAM for security, authorization, and adminstration
- **Low cost and auto scaling capabilities**
- **Type of Data?**
    - it is a key/value database

    ![Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled%203.png](Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled%203.png)

    ### RedShift

    - Redshift is based on PostgreSQL, but it's not used for OLTP
    - **It's OLAP, Online Analytical Processing (analytics and data warehousing)**
    - Really good for analyzing data, **10x better performance than other data warehouses**, scale to PBs of data
    - **Columnar** storage of data (instead of row based)
    - **Massively Parallel Query Execution (MPP), highly available**
    - Pay as you go based on the instances provisioned
    - Has a SQL interface for performing queries
    - Integrated with BI tool such as AWS Quicksight or Tableau

    ## Amazon EMR

    - EMR stands for "**Elastic MapReduce"**
    - It helps creating **Hadoop clusters (Big Data)** to analyze and process vast amount of data
    - Clusters can be made of **hundreds of EC2 instances**
    - Supports **Apache Spark, HBase, Presto, Flink...**
    - EMR takes care of all the provisioning and configuration
    - Autoscaling available integrated with Spot instances
    - **Use cases: data processing, machine learning, web indexing, big data.**

    ## Athena

    - Fully serverless database with SQL capabilites
    - Used to query data in S3
    - Pay per query
    - Output results back to S3
    - Secured through IAM
    - **Use case: one-time SQL queries, serverless queries on S3, log analytics**

    ## DMS

    - Database Migration Service

        ![Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled%204.png](Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled%204.png)

    ## Glue

    - Managed **extract, transform, and load (ETL)** service
    - Useful to prepare and transform data for analytics (**fully serverless service)**

    ![Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled%205.png](Databases%20&%20Analytics%206b096d0d192240439051d36822ac22cb/Untitled%205.png)

    - Glue Data Catalog: **catalog of datasets** is also available

    ## Summary

    - **Relational Databases** - OLTP ( Online Transaction Processing) - RDS & Aurora (SQL)
    - **In-memory Database**: ElastiCache
    - **Key/Value Database**: DynamoDB (serverless)
    - **Warehouse** - OLAP: Redshift (SQL)
    - **Hadoop Cluster**: EMR
    - **Athena**: query data on Amazon S3 (serverless & SQL)
    - **Glue**: Managed ETL (Extract Transform Load) and Data Catalog Service
    - **Database Migration**: DMS

    ## Questions

    1. Amazon ElastiCache is a web service that makes it easy to deploy and run Memcached or Redis protocol-compliant server nodes in the cloud. ElastiCache caches are in-memory databases with high performance, low latency. They help reduce load off databases for read intensive workloads
    2. Amazon Redshift is a fully managed, petabyte-scale data warehouse service in the cloud.
    3. Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL. Athena is serverless, so there is no infrastructure to manage, and you pay only for the queries that you run.
    4. AWS Glue is a fully managed extract, transform, and load (ETL) service that makes it easy for customers to prepare and load their data for analytics.
    5. Amazon Aurora is a MySQL and PostgreSQL-compatible relational database built for the cloud, that combines the performance and availability of traditional enterprise databases with the simplicity and cost-effectiveness of open source databases. It is a proprietary technology from AWS
    6. AWS Database Migration Service helps you migrate databases to AWS quickly and securely. The source database remains fully operational during the migration, minimizing downtime to applications that rely on the database.
    7. Amazon EMR is a web service that enables businesses, researchers, data analysts, and developers to easily and cost-effectively process vast amounts of data. EMR helps creating Hadoop clusters (Big Data) to analyze and process vast amount of data
    8. The AWS Glue Data Catalog is a central repository to store structural and operational metadata for all your data assets. For a given data set, you can store its table definition, physical location, add business relevant attributes, as well as track how this data has changed over time
    9. Amazon Relational Database Service (Amazon RDS) is a SQL managed service that makes it easy to set up, operate, and scale a relational database in the cloud. It is suited for OLTP workloads
    10. DynamoDB is a fast and flexible non-relational database service for any scale. It can scale with no downtime, it can process millions of requests per second, and is fast and consistent in performance.