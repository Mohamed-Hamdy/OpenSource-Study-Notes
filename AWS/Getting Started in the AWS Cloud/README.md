# Getting Started in the AWS Cloud

### **Introduction to Cloud Computing**

- Cloud computing allows you to treat infrastructure like **software**, not hardware.
- It is the **on-demand delivery** of IT resources and applications over the **internet**.

------

### **Advantages of Cloud Computing**

 ✅ **No large upfront investments**
 ✅ **No hardware management**
 ✅ **Provision exactly what you need, when you need it**
 ✅ **Scale as needed and only pay for what you use**

------

### **Three Key Benefits**

1.  **Programmable resources** – Easily automate and manage your infrastructure.
2.  **Dynamic abilities** – Scale resources up or down on demand.
3.  **Pay as you go** – Pay only for what you consume.

------

### **Traditional On-Premises vs. Cloud**

**On-Premises:**

- Buy, set up, and maintain physical servers.
- Risk of **over- or under-provisioning**.
- Long provisioning time and higher upfront costs.

**Cloud Services (e.g., AWS):**

- Infrastructure is **managed by the cloud provider**.
- Resources are **virtualized** and accessed via the **internet**.
- Offers **elasticity**, scaling with your business needs.

------

### **How AWS Works**

- AWS owns and maintains the hardware.
- You interact with AWS via:
  -  **AWS Management Console**
  -  **AWS CLI**
  -  **AWS SDKs**
- You can **customize** storage, applications, and network configuration.

------

### **Core AWS Services**

Focus areas include:

 🖥️ **Compute** – e.g., Amazon EC2
 📦 **Storage** – e.g., Amazon S3, EBS
 📊 **Databases** – e.g., DynamoDB
 🌐 **Networking** – e.g., Amazon Route 53, VPC
 🔐 **Security** – Identity and compliance tools

------

### **Broad AWS Service Categories**

- **Machine Learning**
- **IoT**
- **Media Services**
- **Analytics**
- **Blockchain**
- **Application Integration**
- **Mobile & Game Tech**
- **Customer Engagement**
- **Migration & Security Tools**
   …and more.

------

### ✅ Quiz Review

**Q: Which statement best describes traditional on-premises environments?**
 ➡️ *You are responsible for purchasing hardware to match your capacity needs.*

**Q: What are the three key benefits of cloud computing?**
 ✅ Programmable resources
 ✅ Dynamic abilities
 ✅ Pay as you go

------

## **Understanding the AWS Global Infrastructure**

### What Is the AWS Global Infrastructure?**

The AWS Global Infrastructure is composed of several **geographically distributed components** that help run your applications reliably, securely, and at scale. These components include:

- **Regions** (geographic areas)
- **Availability Zones** (multiple isolated locations within a region)
- **Data Centers** (physical buildings housing servers)

------

###  **Six Key Advantages of the AWS Cloud Infrastructure**

1. **Trade upfront costs for variable costs**
   - No need to invest in hardware or facilities upfront.
   - You only pay for what you use.
2. **Increase speed and agility**
   - Quickly deploy resources and scale faster.
   - More time to focus on building your app.
3. **Move to a global presence**
   - Deploy apps in multiple locations worldwide without physically being there.
4. **Stop spending money running and maintaining data centers**
   - AWS manages the infrastructure, freeing your team to focus on innovation.
5. **Stop guessing capacity**
   - Scale up or down as needed without overprovisioning or underprovisioning.
6. **Benefit from massive economies of scale**
   - AWS leverages huge customer demand to reduce prices for everyone.

------

### **Quiz Question & Correct Answer**

**Question:**
 Which statement best describes an AWS data center?

**Correct Answer:**

> **An AWS data center is where your hardware is located. It typically houses thousands of servers.**

# Core Services Overview: Compute

## Amazon EC2 (Elastic Compute Cloud)

Amazon EC2 provides scalable virtual servers (instances) in the cloud.

**Key Benefits:**

- Full control over compute resources
- Resizable capacity
- Fast provisioning
- Multiple instance types tailored to different workloads

**EC2 Instance Types and Use Cases:**

- General purpose: Balanced resources (e.g., t3, m5)
- Compute optimized: CPU-heavy workloads (e.g., c4, c5)
- Memory optimized: High RAM use cases like in-memory databases (e.g., r5, x1)
- Storage optimized: I/O-intensive apps (e.g., i3, d2)
- Accelerated computing: GPU-heavy tasks like ML (e.g., p3, g4)
- HPC optimized: Large-scale simulations, deep learning (e.g., Hpc6a)

------

## Amazon EC2 Auto Scaling

Auto Scaling adjusts the number of EC2 instances to match demand.

**Key Benefits:**

- Automatically replaces unhealthy instances
- Dynamically scales based on real-time metrics
- Avoids over- or under-provisioning
- Offers manual, scheduled, dynamic, and predictive scaling options

------

## Serverless Computing with AWS Lambda

Serverless computing allows you to run code without managing servers.

**Key Benefits:**

- No servers to provision or manage
- Automatically scales with usage
- No charges for idle resources
- Built-in availability and fault tolerance

**AWS Lambda Features:**

- Supports multiple programming languages
- Runs code in response to events or on a schedule
- Billed per millisecond of execution
- Stateless and highly available

------

## Containers (Amazon ECS and Amazon EKS)

Used for deploying and managing containerized applications.

- Amazon ECS: AWS-managed container orchestration
- Amazon EKS: Managed Kubernetes service

**Key Benefits:**

- Centralized control and monitoring of containers
- Scales and maintains container fleets
- Simplifies infrastructure management

------

## Quiz Answer Summary

**Benefits of Serverless (Select 3):**

- No physical servers to provision or manage
- Resources scale based on usage
- Built-in availability

**AWS Lambda Advantages (Select 3):**

- Per-millisecond pricing
- Runs code in response to events
- Can run code on a schedule

**Amazon EC2 Auto Scaling Benefits (Select 3):**

- Automatically replaces unhealthy instances
- Matches capacity to real-time demand
- Scales horizontally to avoid over/under provisioning

## Core Storage Services in AWS

In this lesson, you explore **four core AWS storage services**, focusing mainly on **Amazon S3** and its various storage classes.

------

## Amazon S3 (Simple Storage Service)

**Amazon S3** is a fully managed, serverless, low-cost **object-level storage** service.

### Key Features:

- Scalable and highly durable object storage
- Unlimited data storage across different formats
- 99.999999999% durability
- Supports event-driven architecture (can trigger functions on file uploads)

------

## Amazon S3 Storage Classes

Amazon S3 offers multiple **storage classes**, optimized for different **cost, performance, and access patterns**:

### Frequently Accessed Data:

- **S3 Standard**: Best for general-purpose use, low latency, high throughput

### Optimized for Cost Savings:

- **S3 Intelligent-Tiering**: Automatically moves data between access tiers based on usage
- **S3 Standard-IA (Infrequent Access)**: Lower cost for infrequently accessed data, with retrieval fees
- **S3 One Zone-IA**: Same as Standard-IA but stored in a single Availability Zone (lower cost, lower redundancy)

### Archival & Long-Term Storage:

- **S3 Glacier Instant Retrieval**: Low-cost storage for data that requires immediate access
- **S3 Glacier Flexible Retrieval**: Archive data with minutes to hours retrieval time
- **S3 Glacier Deep Archive**: Lowest-cost storage for data accessed once or twice a year

### On-Premises Option:

- **S3 Outposts**: Brings Amazon S3 on-premises for hybrid cloud storage needs

------

## Amazon S3 Benefits

- **High Durability**: Designed for 11 nines (99.999999999%) of durability
- **Event-Driven Support**: Trigger AWS Lambda or other services on file upload or changes
- **Flexible Storage Options**: Choose the right storage class based on performance, access frequency, and cost

------

- ## Amazon S3 Use Cases

  Amazon S3 is a versatile service with a wide range of use cases. Here are key examples:

  1. **Content storage and distribution**
     - Store and deliver static assets like images, videos, and documents.
  2. **Backup and archiving**
     - Cost-efficient and durable storage for backup and compliance archives.
  3. **Build a data lake**
     - Centralize structured and unstructured data at scale for analytics.
  4. **Backup and restore critical data**
     - Enable disaster recovery with versioning and object replication.
  5. **Archive data**
     - Store infrequently accessed data using Glacier or Deep Archive tiers.
  6. **Run cloud-native apps**
     - Use S3 to store application logs, configuration files, and temporary app data.

  ------

  ## Other Core AWS Storage Services

  ### **Amazon EBS (Elastic Block Store)**

  **Description**:
   Durable, block-level storage volumes for use with Amazon EC2.

  **Key Benefits**:

  - Persistent even after EC2 is stopped or terminated (unless deleted).
  - Choice of SSD or HDD-based volumes.
  - Scalable capacity.
  - Pay only for what you provision.
  - Supports **encrypted snapshots** and **automated backups**.

  ### **Amazon EFS (Elastic File System)**

  **Description**:
   Fully managed **serverless** file system that can be mounted by multiple EC2 instances.

  **Key Features**:

  - Scalable and elastic
  - Supports **NFS** and **SMB** protocols
  - Ideal for shared file storage
  - Integrated with AWS compute services
  - Offers **four storage classes** for different performance needs

  ### **Amazon FSx**

  **Description**:
   Launch, run, and scale high-performance file systems with native support for:

  - **NetApp ONTAP**
  - **Windows File Server**
  - **OpenZFS**
  - **Lustre**

  **Highlights**:

  - Fully managed and cost-effective
  - Suitable for workloads needing advanced features like snapshots, deduplication, and caching
  - Handles patching, provisioning, and backups

  ------

  ## Quiz Answer Summary

  **Q1: Amazon EBS Benefits (Select 2):**

  -  Pay only for what you provision
  -  Snapshots are encrypted and support recovery

  **Q2: Amazon S3 Use Cases (Select 3):**

  -  Building a data lake
  -  Content storage and distribution
  -  Archiving data

  **Q3: Amazon EFS Use Cases (Select 2):**

  -  Build high-performing, cost-optimized file systems with built-in elasticity
  -  Use when you need a serverless shared file system

## Ways to Run Databases on AWS

You can run your database workloads in two main ways:

1. **Amazon EC2** – Full control, but manual setup and maintenance.
2. **Managed Database Services** – AWS handles provisioning, backups, scaling, patching, etc.

------

## Benefits of AWS Managed Databases

- Simplified configuration and setup
- Automated backups and failover
- High availability and security
- Performance at scale
- Purpose-built engines for different use cases

------

## AWS Database Types & Services

| **Database Type** | **Use Cases**                                     | **AWS Service(s)**                            |
| ----------------- | ------------------------------------------------- | --------------------------------------------- |
| **Relational**    | ERP, CRM, e-commerce                              | Amazon Aurora, Amazon RDS, Amazon Redshift    |
| **Key-Value**     | Web apps, gaming, e-commerce                      | Amazon DynamoDB                               |
| **In-memory**     | Caching, sessions, gaming leaderboards            | Amazon ElastiCache, Amazon MemoryDB for Redis |
| **Document**      | User profiles, content management                 | Amazon DocumentDB                             |
| **Wide Column**   | Fleet management, industrial apps                 | Amazon Keyspaces                              |
| **Graph**         | Fraud detection, social media, recommendations    | Amazon Neptune                                |
| **Time Series**   | IoT, DevOps, industrial telemetry                 | Amazon Timestream                             |
| **Ledger**        | Registrations, supply chain, banking transactions | Amazon QLDB                                   |



------

## AWS Database Services Highlights

### **Amazon Aurora**

- Compatible with MySQL and PostgreSQL
- Serverless, multi-region replication
- High availability and performance
- Built for the cloud

### **Amazon RDS**

- Supports 7 popular engines (Aurora, MySQL, PostgreSQL, MariaDB, Oracle, SQL Server)
- Multi-AZ deployment for high availability
- Simplifies setup and management of relational databases

### **Amazon Redshift**

- Cloud-based **data warehouse**
- Columnar storage for OLAP workloads
- High performance analytical querying

### **Amazon DynamoDB**

- Fully managed, **serverless** NoSQL database
- Single-digit millisecond performance
- Auto-scaling for high throughput
- Ideal for dynamic schemas

### **Amazon ElastiCache / MemoryDB**

- In-memory data storage
- Ultra-fast latency
- Redis or Memcached support

### **Amazon DocumentDB**

- Document-oriented database with MongoDB compatibility
- Optimized for JSON workloads

### **Amazon Keyspaces**

- Managed wide-column database
- Apache Cassandra compatibility

### **Amazon Neptune**

- Graph database
- Best for connected data (e.g., social graphs, fraud detection)

### **Amazon Timestream**

- Optimized for time series data
- Serverless and scalable
- Great for IoT and DevOps metrics

### **Amazon QLDB**

- Fully managed **ledger database**
- Immutable, transparent, and cryptographically verifiable logs

------

## Quiz Answer Summary

**Q1: Amazon RDS Attributes (Select 3):**

-  Can be launched in Multi-AZ for high availability
-  Compatible with multiple engines including Amazon Aurora
-  Setup and scaling with just a few clicks

**Q2: Why Choose Amazon Neptune?**

-  Simplifies the setup and running of graph databases

**Q3: Amazon DynamoDB Key Features (Select 2):**

-  Single-digit millisecond performance at any scale
-  Fully managed, serverless, nonrelational database

## Core AWS Networking Services

AWS provides essential networking services to help your resources communicate within the cloud and with users across the internet.

------

### Amazon Virtual Private Cloud (Amazon VPC)

- **What it is**: A logically isolated virtual network within AWS.
- **Purpose**: Launch AWS resources (like EC2 instances) in a secure, customizable network.
- **Benefits**:
  - Full control over IP addressing, subnets, route tables, and network gateways.
  - Traffic control in and out of the network.
  - Logical separation of environments (e.g., dev, test, prod).
  - Can connect to on-premises networks or other VPCs via VPN or VPC peering.

------

### Amazon Route 53 (DNS)

- **What it is**: A highly available and scalable Domain Name System (DNS) web service.
- **Main functions**:
  1. **Domain Registration** – Buy and manage domains.
  2. **DNS Routing** – Translate human-readable domain names into IP addresses.
  3. **Health Checks** – Monitor the health of resources.
- **Routing policies** include:
  - Simple
  - Weighted
  - Latency-based
  - Failover
  - Geolocation, etc.
- **Use Case**: Direct user traffic to AWS-hosted or on-prem apps.

------

### Elastic Load Balancing (ELB)

- **What it is**: Distributes incoming application traffic automatically across multiple targets (like EC2 instances).
- **Main types**:
  - Application Load Balancer (HTTP/HTTPS)
  - Network Load Balancer (TCP/UDP)
  - Gateway Load Balancer (third-party virtual appliances)
- **Benefits**:
  - Improves availability and fault tolerance.
  - Supports scaling by balancing traffic across multiple AZs.
  - Acts as a **single point of contact** for end users.

------

## Quiz Answer Summary

**Q1: What is a benefit of Amazon Route 53?**

- You can purchase and manage domain names and configure DNS settings.

**Incorrect options:**

- DNS **does** translate domain names into IP addresses.
- Route 53 has **multiple** routing options.
- Route 53 **is** a scalable DNS service.

------

**Q2: What is an advantage of Elastic Load Balancing (ELB)?**

- ELB automatically distributes incoming application traffic across virtual appliances in one or more Availability Zones.

**Incorrect options:**

- ELB does **not** send traffic to only one EC2 instance.
- ELB is **not** a DNS service (that’s Route 53).
- It handles **more than two** targets, depending on configuration.



## Core AWS Security Services Overview

### Shared Responsibility Model

AWS and the customer share responsibility for securing workloads. The division of responsibility depends on the **services used**.

#### **AWS is responsible for: “Security \*of\* the Cloud”**

- Physical infrastructure (data centers, hardware, networking)
- Foundation services (compute, storage, database, networking)
- Global infrastructure (Regions, Availability Zones, edge locations)
- Environmental and physical controls

#### **Customer is responsible for: “Security \*in\* the Cloud”**

- Data and file system security
- Identity and Access Management (IAM)
- Application configuration
- Network/firewall configuration
- Encryption (client-side, server-side, traffic protection)

------

## AWS Security Tooling & Services

### 1. **IAM – Identity and Access Management**

- Controls access to AWS services and resources
- Allows user/role-based permission policies

### 2. **AWS KMS – Key Management Service**

- Create, manage, and rotate encryption keys
- Control access to cryptographic keys

### 3. **AWS Shield**

- Protects against DDoS attacks
- Comes in **Standard** (default) and **Advanced** (premium) versions

### 4. **AWS Artifact**

- Provides compliance documentation
- Used to download reports and agreements

### 5. **AWS Trusted Advisor**

- Provides real-time recommendations across:
  - Cost Optimization
  - Performance
  - Security
  - Fault Tolerance
  - Service Limits

------

## Quiz Answer Summary

**Q1: AWS responsibilities in the Shared Responsibility Model**
 ✅ Global infrastructure
 ✅ Foundation services (storage, compute, etc.)

------

**Q2: Customer responsibilities in the Shared Responsibility Model**
 ✅ Identity and access management
 ✅ Applications and firewall configuration

------

**Q3: AWS Security Systems**
 ✅ AWS Key Management Service (KMS)
 ✅ AWS Identity and Access Management (IAM)
 ✅ AWS Shield

------

## Core AWS Pricing Concepts

AWS offers flexible, usage-based pricing designed to help you **optimize costs** as your needs change.

### Main Pricing Principles

1. **Pay for what you use**
    You are billed for the resources you actually consume.
2. **Pay less when you reserve**
    Save significantly with **Reserved Instances** or **Savings Plans** by committing to usage for 1 or 3 years.
3. **Pay less with volume-based discounts**
    As your usage increases, AWS automatically applies tiered discounts.
4. **Pay even less as AWS grows**
    AWS reduces prices as it gains operational efficiencies and scale.

------

## Amazon EC2 Purchasing Options

### On-Demand Instances

- Pay by the second for compute capacity.
- No long-term commitment.
- Best for short-term, unpredictable workloads.

### Reserved Instances / Savings Plans

- Commit to usage for 1 or 3 years.
- Standard Reserved Instances: up to 72% discount.
- Convertible Reserved Instances: allow instance family and OS changes.

### Spot Instances

- Use unused EC2 capacity for up to 90% off regular pricing.
- Ideal for stateless, flexible, or fault-tolerant workloads.

------

## AWS Free Tier

AWS Free Tier offers free access to AWS services under different models:

### Always Free

- Available to all users, all the time.
- Examples: AWS Lambda (1M requests/month), DynamoDB (25 GB)

### 12 Months Free

- Valid for 12 months after initial signup.
- Examples: EC2 t2.micro (750 hours/month), S3 (5 GB)

### Free Trials

- Temporary full-access trials of premium services.
- Duration varies by service.

------

## Cloud Financial Management with AWS

Tools and services to help you:

- Monitor and optimize AWS costs
- Set budgets and forecasts
- Analyze usage patterns
- Control spending using reports and alerts

------

## Quiz Answer Summary

**Q1: Amazon EC2 purchasing options**

 ✅ Spot Instances can provide up to **90% discount**
 ✅ Reserved Instances include **Standard and Convertible** options

------

**Q2: AWS Free Tier types**

 ✅ Always free
 ✅ 12 months free
 ✅ Free trials

------

**Q3: AWS Pricing Benefits**

✅ Pay even less as AWS grows
 