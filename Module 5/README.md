## Module 5: Storage and Databases

### Instance Store

- Provides **temporary block-level storage** physically attached to the **host machine** of the EC2 instance.
- **Data is lost** when the instance is stopped or terminated.
- Best for **temporary data** that doesn’t need to persist, such as cache or buffers.

### Amazon Elastic Block Store (EBS)

- Provides **persistent block-level storage** that **remains intact** even if the EC2 instance is stopped or terminated.
- Volumes are **separate from the EC2 host** and can be **backed up** using **EBS snapshots**.
- **Snapshots** are **incremental**: only changed data is saved after the first full snapshot.

------

### Key Differences

| Feature        | Instance Store                        | Amazon EBS                                 |
| -------------- | ------------------------------------- | ------------------------------------------ |
| Persistence    | Temporary (deleted on stop/terminate) | Persistent (retained after stop/terminate) |
| Attachment     | Physically tied to host machine       | Separate from host                         |
| Best Use       | Temporary data                        | Long-term data                             |
| Backup Support | No                                    | Yes (Snapshots)                            |

------

### Amazon S3 (Simple Storage Service)

**Object Storage**

- Stores data as **objects** within **buckets**.
- Each object includes:
  - **Data** (e.g., image, video, file),
  - **Metadata** (info about the data),
  - **Key** (unique identifier).
- When an object is modified, **the entire object is updated** (not just a part like in block storage).

**Key Features**

- Supports storing **any file type** (up to 5 TB per object).
- **Unlimited storage capacity**.
- Common use cases: backups, media hosting, data archiving.
- Offers **access control** (e.g., public/private permissions).
- **Versioning** available to track object changes.

------

### S3 Storage Classes (Cost & Access Optimization)

| Storage Class                 | Use Case                                                     |
| ----------------------------- | ------------------------------------------------------------ |
| S3 Standard                   | Frequent access, high durability and availability.           |
| S3 Standard-IA                | Infrequent access, but must be quickly retrievable.          |
| S3 One Zone-IA                | Same as IA, but stored in a single Availability Zone.        |
| S3 Intelligent-Tiering        | Automatically moves data between tiers based on usage patterns. |
| S3 Glacier Instant Retrieval  | Archive with instant access for rarely accessed data.        |
| S3 Glacier Flexible Retrieval | Archive with flexible access times (minutes to hours).       |
| S3 Glacier Deep Archive       | Cheapest, for long-term archiving, retrieval in hours.       |
| S3 Outposts                   | On-premise object storage using AWS services.                |

### Amazon Elastic File System (Amazon EFS)

**What is it?**

- A **scalable, serverless file storage** service for use with AWS services and on-premises resources.
- Supports **simultaneous access** by multiple clients (like EC2, servers, containers).
- Ideal for use cases that require **shared access to the same data**.

**Key Features**

- Grows and shrinks automatically as you add/remove files.
- Scales **on demand** up to **petabytes** without disruption.
- Provides **low latency and high throughput**.

------

### Comparison: Amazon EBS vs Amazon EFS

| Feature            | Amazon EBS                                        | Amazon EFS                                                 |
| ------------------ | ------------------------------------------------- | ---------------------------------------------------------- |
| Scope              | Single Availability Zone                          | Multi-AZ (Regional)                                        |
| Storage Type       | Block storage                                     | File storage                                               |
| Access             | Attached to one EC2 instance                      | Can be accessed by **multiple EC2 instances** concurrently |
| Use Cases          | High-performance apps needing low-latency storage | Shared storage for apps, web servers, CMSs                 |
| Scalability        | Manually configured volume sizes                  | **Automatically scales** with usage                        |
| On-Premises Access | Not directly                                      | Accessible via **AWS Direct Connect**                      |



------

### Amazon Relational Database Service (Amazon RDS)

**What is it?**
 Amazon RDS is a **managed service** that makes it easier to set up, operate, and scale **relational databases** in the cloud. It automates tasks like:

- Hardware provisioning
- Database setup
- Patching
- Backups

------

### Key Features:

- Supports **SQL-based relational databases**
- Handles **administrative tasks** so you can focus on application development
- Offers **encryption at rest and in transit**
- Can integrate with other AWS services (e.g., AWS Lambda)
- Provides **high availability** and **failover** options

------

### Supported Database Engines:

- **Amazon Aurora** (compatible with MySQL and PostgreSQL)
- **PostgreSQL**
- **MySQL**
- **MariaDB**
- **Oracle Database**
- **Microsoft SQL Server**

------

### Amazon Aurora (Highlight):

- Enterprise-grade database engine
- **5x faster than standard MySQL**, **3x faster than PostgreSQL**
- Stores **six copies** of data across **three Availability Zones**
- Automatically backed up to **Amazon S3**
- Ideal for high-throughput, highly available applications

------

### Amazon DynamoDB 

**What is it?**
 Amazon DynamoDB is a **fully managed**, **serverless**, **nonrelational (NoSQL)** database service that uses **key-value pairs** and **document data structures** to store and retrieve data.

------

### Key Features:

- **Serverless**: No server provisioning, maintenance, or patching required.
- **Automatic Scaling**: Automatically adjusts capacity based on usage while maintaining consistent performance.
- **Flexible Schema**: Different items in the same table can have different attributes.
- **High Performance**: Provides **single-digit millisecond response times** at any scale.
- **Highly Available and Durable**: Built-in replication across multiple Availability Zones.

------

### Use Cases:

- Applications that require **massive scale** (millions of requests/second)
- **Real-time analytics**
- **Gaming backends**, **IoT data storage**, **mobile apps**
- Where **schema flexibility** and **speed** are more critical than complex querying

------

### Example (Key-Value Pair):

| Key  | Value                                                        |
| ---- | ------------------------------------------------------------ |
| 1    | Name: John Doe Address: 123 Any Street Favorite drink: Medium latte |
| 2    | Name: Mary Major Address: 100 Main Street Birthday: July 5, 1994 |

------

### Amazon Redshift

**What is it?**
 Amazon Redshift is a **fully managed data warehouse** service designed for **analyzing large volumes of data** (big data). It enables you to collect, store, and analyze data from multiple sources to uncover meaningful patterns, trends, and relationships.

### Key Features:

- **Big Data Analytics**: Handles petabyte-scale data for complex queries and business intelligence (BI).
- **Columnar Storage**: Stores data by columns instead of rows for faster query performance.
- **Massively Parallel Processing (MPP)**: Distributes workloads across multiple nodes to speed up data processing.
- **Integrates with BI Tools**: Easily connects with tools like Amazon QuickSight, Tableau, and Looker.
- **Cost-Effective**: Pay only for what you use, with options for on-demand or reserved instances.

### Use Cases:

- Data warehousing
- Business intelligence reporting
- Large-scale data aggregation from different sources
- Predictive analytics and trend analysis

------

### AWS Database Migration Service (AWS DMS) 

**What is it?**
 AWS DMS is a fully managed service that helps you **migrate databases and data stores** from one location to another—whether between on-premises systems and AWS, between AWS services, or across database engines.

### Key Features:

- **Supports Heterogeneous Migrations**: Migrate between different database engines (e.g., MySQL to PostgreSQL).
- **Minimal Downtime**: The source database remains fully operational during the migration.
- **Supports Relational and Nonrelational Databases**: Works with a wide range of data sources like MySQL, PostgreSQL, Oracle, MongoDB, Amazon Aurora, and more.
- **Managed and Scalable**: AWS handles provisioning, failover, and monitoring.

### Common Use Cases:

- **Production to Test Migration**: Clone production data for developers without disrupting live applications.
- **Database Consolidation**: Merge multiple databases into one for centralized management.
- **Continuous Replication**: Set up real-time data replication for analytics or backup purposes.

------

### **Additional AWS Database Services**

#### 1. **Amazon DocumentDB**

- **Type**: Document Database
- **Use Case**: Supports **MongoDB workloads**.
- **Ideal For**: Applications that use **JSON-like document structures**.

#### 2. **Amazon Neptune**

- **Type**: Graph Database
- **Use Case**: Works with **highly connected datasets**.
- **Ideal For**:
  - **Recommendation engines**
  - **Fraud detection**
  - **Knowledge graphs**

#### 3. **Amazon QLDB (Quantum Ledger Database)**

- **Type**: Ledger Database
- **Use Case**: Tracks a **complete, immutable history** of all changes to your application data.
- **Ideal For**:
  - **Audit trails**
  - **Financial applications**
  - **Supply chain tracking**

#### 4. **Amazon Managed Blockchain**

- **Type**: Blockchain Service
- **Use Case**: Create and manage **blockchain networks** using **open-source frameworks**.
- **Ideal For**:
  - **Distributed ledger systems**
  - **Multi-party transactions**
  - **Decentralized applications**

#### 5. **Amazon ElastiCache**

- **Type**: In-memory Caching Service
- **Use Case**: Adds **caching layers** to speed up **database read times**.
- **Supports**:
  - **Redis**
  - **Memcached**
- **Ideal For**:
  - **Real-time analytics**
  - **Session stores**
  - **Leaderboards**

#### 6. **Amazon DynamoDB Accelerator (DAX)**

- **Type**: In-memory Cache for DynamoDB
- **Use Case**: Speeds up **read operations** from milliseconds to **microseconds**.
- **Ideal For**:
  - **Read-heavy DynamoDB workloads**
  - **Applications needing microsecond latency**

------

### Module 5 Summary: AWS Storage and Databases

In this module, you explored key AWS storage and database services:

- **Amazon EC2 Instance Store and Amazon EBS**: Temporary and persistent block storage options for EC2 instances.
- **Amazon S3**: Scalable object storage service for storing and retrieving any amount of data.
- **Amazon EFS**: Fully managed elastic file system that provides shared file storage for use with AWS Cloud services.
- **Relational Databases and Amazon RDS**: Managed relational database service supporting multiple database engines.
- **Nonrelational Databases and DynamoDB**: Fully managed NoSQL database service offering fast and predictable performance.
- **Amazon Redshift**: Data warehouse service optimized for analytics and complex queries.
- **AWS Database Migration Service (DMS)**: Service for migrating databases securely and efficiently.
- **Additional Database Services and Accelerators**: Various other AWS tools and services that enhance database performance and scalability.

### Additional Resources

- [Cloud Storage on AWS](https://aws.amazon.com/products/storage/)
- [AWS Storage Blog](https://aws.amazon.com/blogs/storage/)
- [Hands-On Tutorials: Storage](https://aws.amazon.com/getting-started/hands-on/storage/)
- [AWS Customer Stories: Storage](https://aws.amazon.com/solutions/case-studies/?search=storage)
- [AWS Database Migration Service (DMS)](https://aws.amazon.com/dms/)
- [Databases on AWS](https://aws.amazon.com/products/databases/)
- [Category Deep Dive: Databases](https://aws.amazon.com/blogs/database/category/database/)
- [AWS Database Blog](https://aws.amazon.com/blogs/database/)
- [AWS Customer Stories: Databases](https://aws.amazon.com/solutions/case-studies/?search=database)

------

### Module 5 Quiz

1. **Which Amazon S3 storage classes are optimized for archival data? (Select TWO.)**

- Amazon S3 Glacier Flexible Retrieval
- Amazon S3 Glacier Deep Archive

1. **Which statement or statements are TRUE about Amazon EBS volumes and Amazon EFS file systems?**

- EBS volumes store data within a single Availability Zone. Amazon EFS file systems store data across multiple Availability Zones.

1. **You want to store data in an object storage service. Which AWS service is best for this type of storage?**

- Amazon Simple Storage Service (Amazon S3)

1. **Which statement best describes Amazon DynamoDB?**

- A serverless key-value database service

1. **Which service is used to query and analyze data across a data warehouse?**

- Amazon Redshift