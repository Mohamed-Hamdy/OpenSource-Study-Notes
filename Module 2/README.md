## 📘 MODULE 2 – COMPUTE IN THE CLOUD

------

### <u>Amazon EC2 Overview</u>

- **Amazon EC2 (Elastic Compute Cloud)** provides secure, resizable virtual servers in the AWS cloud.
- **Benefits vs. on-premises:**
  - No upfront hardware cost.
  - Launch virtual servers within minutes.
  - Pay only for what you use (only while running).
  - Scale resources up/down as needed.

------

### <u>How Amazon EC2 Works</u>

![CPE Digital - How Amazon EC2 works](D:\AWS Cloud Practitioner Essentials\AWS-Cloud-Practitioner-Essentials\Images\CPE Digital - How Amazon EC2 works.png)

1. Choose AMI (Amazon Machine Image).
2. Select instance type.
3. Configure instance (networking, storage, etc.).
4. Add storage.
5. Add tags.
6. Configure security group.
7. Launch instance.



------

### <u>Amazon EC2 Instance Types</u>

Different instance types are designed for different use cases:

| **Type**                  | **Use Case**                                                 |
| ------------------------- | ------------------------------------------------------------ |
| **General Purpose**       | Balanced compute, memory, and networking. Ideal for apps, gaming, small DBs. |
| **Compute Optimized**     | High-performance CPUs. Great for web servers, gaming, and batch processing. |
| **Memory Optimized**      | Handles large in-memory datasets. Ideal for real-time data, large databases. |
| **Accelerated Computing** | Uses GPUs/FPGAs for intensive tasks like ML, graphics, simulations. |
| **Storage Optimized**     | High IOPS for workloads like data warehousing, OLTP systems, and big data. |

### <u>Amazon EC2 Pricing Options</u>

| **Pricing Model**      | **Best Use Case**                                            | **Key Benefits**                                             |
| ---------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **On-Demand**          | Short-term, unpredictable workloads.                         | No upfront cost, pay-per-use, flexible.                      |
| **Reserved Instances** | Steady-state usage with long-term commitment.                | Up to 75% savings vs On-Demand. Options: Standard & Convertible. |
| **Savings Plans**      | Consistent usage with flexibility in instance types/regions. | Up to 72% savings, no upfront instance specs required.       |
| **Spot Instances**     | Flexible, interruptible tasks (e.g., batch jobs, non-critical processing). | Up to 90% savings. Runs on unused EC2 capacity.              |
| **Dedicated Hosts**    | Regulatory/license-bound workloads (e.g., BYOL, compliance-heavy environments). | Full control of physical server, but most expensive option.  |

#### Quick Pricing Notes

- **Reserved Instances** require a 1- or 3-year commitment.
- **Convertible Reserved Instances** allow changes in instance type, OS, and AZ.
- **Savings Plans** are flexible, charged based on hourly commitment (not instance count).
- **Spot Instances** can be interrupted, making them ideal for background or non-critical jobs.
- **Dedicated Hosts** offer complete server isolation and support for legacy licensing.

### <u>Scaling Amazon EC2</u>

#### **Scalability Overview**

- Scalability means starting with the resources you need and growing or shrinking them based on demand.
- You only pay for what you use.
- To handle changing demand automatically, you use **Amazon EC2 Auto Scaling**.

#### **Amazon EC2 Auto Scaling**
<p align="center">
  <img src="https://github.com/Mohamed-Hamdy/AWS-Cloud-Practitioner-Essentials-Course-Notes/blob/main/Images/CPE%20Digital%20-%20Amazon%20EC2%20Auto%20Scaling.png?raw=true" width="400" alt="CPE Digital - Amazon EC2 Auto Scaling" />
</p>


- Automatically adds or removes EC2 instances based on application demand.
- Ensures high availability and optimal cost-efficiency.
- Two scaling strategies:
  - **Dynamic Scaling**: Responds to real-time demand changes.
  - **Predictive Scaling**: Forecasts future demand and adjusts capacity proactively.
- You can combine both for faster and more accurate scaling.

#### **Auto Scaling Group Example**

- You define three key settings:
  - **Minimum capacity**: e.g., 1 instance (always running).
  - **Desired capacity**: e.g., 2 instances (target level to maintain).
  - **Maximum capacity**: e.g., 4 instances (upper limit during high demand).
- If desired capacity is not set, it defaults to the minimum.
- EC2 Auto Scaling ensures a cost-effective, high-availability application infrastructure.
- You are billed only for the running EC2 instances—improving efficiency while keeping costs under control.

### <u>**Elastic Load Balancing (ELB)**</u>

- **Elastic Load Balancing (ELB)** automatically distributes incoming application traffic across multiple targets (like EC2 instances).
  - Acts as a **single point of contact** for incoming traffic, improving application availability and fault tolerance.
- **Works with EC2 Auto Scaling** to adjust the number of instances handling traffic based on demand.
- Ensures **no single EC2 instance is overloaded** by spreading requests evenly.

#### Real-World Analogy:

- Think of **Amazon EC2 instances** as registers in a coffee shop.
- During busy hours, more registers (instances) open to serve customers.
- A staff member (the **load balancer**) directs customers to the shortest line, ensuring efficient service.

#### Low-Demand Period:

> If only a few customers are present, a few EC2 instances (registers) handle the traffic.

<p align="center">
  <img src="https://github.com/Mohamed-Hamdy/AWS-Cloud-Practitioner-Essentials-Course-Notes/blob/main/Images/CPE%20Digital%20-%20Low%20demand.png?raw=true" alt="Low Demand" width="350" />
</p>


------

#### 🖼️ High-Demand Period:

> As customer demand increases, more EC2 instances (registers) are launched to manage the load efficiently, and ELB distributes traffic evenly.

<p align="center">
  <img src="https://github.com/Mohamed-Hamdy/AWS-Cloud-Practitioner-Essentials-Course-Notes/blob/main/Images/CPE%20Digital%20-%20High%20demand.png?raw=true" width="350" alt="High Demand">
</p>
### <u>Messaging and Queuing in AWS</u>

**Monolithic vs. Microservices Architecture:**

- **Monolithic applications:** Components are tightly coupled; if one component fails, the entire application can fail.
- **Microservices:** Components are loosely coupled; if one fails, others continue to function, improving availability.

AWS supports microservices communication with two key services:

------

### <u>**Amazon Simple Notification Service (SNS)**</u>

- SNS is a **publish/subscribe messaging service**.
- Publishers send messages to **topics**, and subscribers receive messages from those topics.
- Subscribers can be web servers, email addresses, AWS Lambda functions, etc.
- Example: A coffee shop newsletter where customers subscribe to topics like coupons, coffee trivia, or new products.
- Customers can subscribe to multiple or individual topics to receive only relevant updates.

------

### <u>Amazon Simple Queue Service (SQS)</u>

- SQS is a **message queuing service** that decouples application components.
- Messages are sent to a queue, stored until processed, and then deleted.
- This allows components to work independently without waiting on each other.
- Example: Coffee shop ordering system:
  - Cashier takes orders and puts them in a queue.
  - Barista retrieves orders from the queue when ready.
  - Enables smooth operation even if barista is busy or on break.

### <u>Additional Compute Services</u>

### **Serverless Computing**

- **Serverless** means you run code *without managing servers*. AWS handles server provisioning and scaling.
- Focus is on *code*, not infrastructure.
- **Scales automatically** based on demand.
- Example service: **AWS Lambda**
  - Run code in response to events (e.g., file uploads, API calls).
  - Pay only for **compute time used**.
  - No need to manage infrastructure.

------

### **AWS Lambda Process**
<p align="center">
  <img src="https://github.com/Mohamed-Hamdy/AWS-Cloud-Practitioner-Essentials-Course-Notes/blob/main/Images/aws-lambda-sudo.png?raw=true" width="500" alt="aws-lambda-sudo">
</p>
1. Upload your code.
2. Configure a trigger (like an S3 upload or API Gateway call).
3. Lambda executes code only when triggered.
4. Billing is based on execution time only.

------

### **Containers**

- **Containers** package app code and dependencies together.
- Ensure consistent environments across development and deployment.
- Useful for scalable, secure, and reliable workflows.

------

### **Scaling with Containers**

- A single host can run multiple containers.
- At scale (100s of hosts, 1000s of containers), you need orchestration to manage them efficiently.

------

### **Container Orchestration Services**

- **Amazon ECS (Elastic Container Service)**
  - AWS-managed Docker container orchestration.
  - High-performance, scalable.
  - Supports both open-source and enterprise Docker.
- **Amazon EKS (Elastic Kubernetes Service)**
  - AWS-managed **Kubernetes** (open-source container orchestration platform).
  - Lets you run Kubernetes apps at scale on AWS.
  - Easy updates and community support.
- **AWS Fargate**
  - **Serverless compute engine for containers**.
  - Works with ECS and EKS.
  - No server provisioning needed; just define and run your containers.
  - Pay for what you use.

# Module 2 Summary



In Module 2, you learned about the following concepts:

- Amazon EC2 instance types and pricing options
- Amazon EC2 Auto Scaling
- Elastic Load Balancing
- AWS services for messaging, containers, and serverless computing

## **Additional resources**

To learn more about the concepts that were explored in Module 2, review these resources.

- [Compute on AWS](https://aws.amazon.com/products/compute)
- [AWS Compute Blog](https://aws.amazon.com/blogs/compute/)
- [AWS Compute Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/compute-services.html)
- [Hands-On Tutorials: Compute](https://aws.amazon.com/getting-started/hands-on/?awsf.getting-started-category=category%23compute&awsf.getting-started-content-type=content-type%23hands-on)
- [Category Deep Dive: Serverless](https://aws.amazon.com/getting-started/deep-dive-serverless/)
- [AWS Customer Stories: Serverless](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc|product%23api-gateway|product%23cloudfront|product%23route53|product%23directconnect|product%23elb&awsf.customer-references-category=category%23serverless)
- [Amazon EC2 Reserved Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-reserved-instances.html)
- [How Savings Plans apply to usage](https://docs.aws.amazon.com/savingsplans/latest/userguide/sp-applying.html)

## **Module 2 Quiz questions with their correct answers**:

------

#### **Q1: You want to use an Amazon EC2 instance for a batch processing workload. What would be the best Amazon EC2 instance type to use?**

 Answer:
 ➡️ Compute optimized

------

#### **Q2: What are the contract length options for Amazon EC2 Reserved Instances? (Select TWO.)**

 Answers:
 ➡️ 1 year
 ➡️ 3 years

------

#### **Q3: You have a workload that will run for a total of 6 months and can withstand interruptions. What would be the most cost-efficient Amazon EC2 purchasing option?**

  Answer:
 ➡️ Spot Instance

------

#### **Q4: Which process is an example of Elastic Load Balancing?**

Answer:
 ➡️ Ensuring that no single Amazon EC2 instance has to carry the full workload on its own

------

#### **Q5: You want to deploy and manage containerized applications. Which service should you use?**

Answer:
 ➡️ Amazon Elastic Kubernetes Service (Amazon EKS)
