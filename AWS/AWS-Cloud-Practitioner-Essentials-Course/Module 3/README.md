## **Module 3: Global Infrastructure and Reliability**



### <u>**AWS Global Infrastructure Overview**</u>

#### 🔹 **Regions**

- A **Region** is a **geographic location** with multiple, isolated **Availability Zones (AZs)**.
- When choosing a Region, consider:
  1. **Compliance**: Choose a Region that meets **data governance and legal** requirements (e.g., UK data must stay in the UK).
  2. **Proximity to customers**: Lower latency by hosting services close to users (e.g., use Singapore Region for Singapore customers).
  3. **Available services**: Not all services are available in every Region (e.g., Amazon Braket only in specific Regions).
  4. **Pricing**: Costs vary between Regions due to factors like **local taxes** (e.g., São Paulo may be 50% more expensive than Oregon).

------

### <u>**Availability Zones (AZs)**</u>

<p align="center">
  <img src="https://raw.githubusercontent.com/Mohamed-Hamdy/AWS-Cloud-Practitioner-Essentials-Course-Notes/refs/heads/main/Images/availability_zones.png" width="500" alt="availability_zones" />
</p>

- An **AZ** is a **single data center or group of data centers** within a Region.
- AZs are located **tens of miles apart** to ensure **low latency** and **high availability**.
- **Best practice**: Run applications in **multiple AZs** to ensure fault tolerance.
  - Example: If **us-west-1a** fails, the application can still run in **us-west-1b**.

### **<u>Edge Locations</u>**

<p align="center">
  <img src="https://github.com/Mohamed-Hamdy/AWS-Cloud-Practitioner-Essentials-Course-Notes/blob/main/Images/CloudFront.png?raw=true" width="500" alt="CloudFront" />
</p>

- An **Edge Location** is a site that **Amazon CloudFront** uses to **cache copies of content closer to customers**.
- Purpose: Improve **content delivery speed** and reduce **latency**.
- Example: If an EC2 instance is in South America, content might be **cached in South Asia** so users in **East Asia** access it faster.
- Edge locations are part of **AWS's global content delivery network (CDN)**.

### **How to Provision AWS Resources**

------

#### 🔹 **Ways to Interact with AWS Services**

1. **AWS Management Console**
   - **Web-based UI** for managing AWS services.
   - Features:
     - Easy navigation, search, and wizards.
     - Mobile app: monitor resources, alarms, and billing.
     - Multiple users can stay logged in on the app.
2. **AWS Command Line Interface (CLI)**
   - **Single tool** for managing AWS services via **command line**.
   - Available on **Windows, macOS, and Linux**.
   - Automate tasks using **scripts** (e.g., launch EC2, manage Auto Scaling groups).
3. **Software Development Kits (SDKs)**
   - Provide **language-specific APIs** for AWS services.
   - Integrate AWS directly into your **apps**.
   - SDKs available for: **Java, .NET, Python, C++, and more**.
   - Includes sample code and documentation.

------

### <u>**AWS Resource Provisioning Services**</u>

1. **AWS Elastic Beanstalk**
   - **Simplifies app deployment**: just upload code and settings.
   - Handles:
     - Capacity adjustments
     - Load balancing
     - Auto scaling
     - Health monitoring
2. **AWS CloudFormation**
   - **Infrastructure as Code (IaC)** tool.
   - Automates and **safely provisions** resources using code templates.
   - Key features:
     - **Repeatable**, version-controlled infrastructure.
     - **Automatic rollback** on error detection.
     - Eliminates the need for manual steps via the console.

## <u>**Module 3 Summary:**</u>

------

### **1. AWS Regions and Availability Zones**

- **Regions**: Separate geographic areas where AWS resources are hosted (e.g., US-East-1, EU-West-1).
- **Availability Zones (AZs)**: Isolated locations within a region, consisting of one or more data centers.
  - AZs are designed for **fault isolation** and **low-latency performance**.
  - Best practice: deploy across **multiple AZs** for **high availability**.

------

### **2. Edge Locations & Amazon CloudFront**

- **Edge Locations**: Sites used by Amazon CloudFront to cache content closer to users.
- Improves **latency** and **delivery speed**.
- Supports global **content distribution**.

------

### **3. Tools to Interact with AWS**

- **AWS Management Console**: Web-based GUI for managing AWS services.
- **AWS CLI (Command Line Interface)**: Automates AWS tasks through command-line commands.
- **AWS SDKs (Software Development Kits)**: APIs for integrating AWS services into apps (supports languages like Java, Python, .NET, etc.).

------

### **4. AWS Elastic Beanstalk**

- Platform-as-a-Service (PaaS) for **deploying applications quickly**.
- Handles provisioning, scaling, and monitoring automatically.
- You only provide your **code and config settings**.

------

### **5. AWS CloudFormation**

- Treats infrastructure as code (**IaC**).
- Provisions resources using **template files**.
- Enables safe, **repeatable deployments** with **rollback on failure**.

------

### **Additional Learning Resources**

- [AWS Global Infrastructure Map](https://infrastructure.aws/)
- [AWS Regions & AZs](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)
- [AWS Networking Blog](https://aws.amazon.com/blogs/networking-and-content-delivery/)
- [AWS Tools to Build](https://aws.amazon.com/getting-started/tools-sdks/)
- [AWS Customer Stories](https://aws.amazon.com/solutions/case-studies/)

------

### <u>**Module 3 Quiz:**</u>

### **1. Which statement is TRUE for the AWS global infrastructure?**

✅ **Correct Answer:**
 **A Region consists of three or more Availability Zones.**

**Explanation:**
 An AWS Region is a separate geographic area with multiple, isolated Availability Zones (AZs). Most Regions contain **three or more AZs** to ensure high availability.

------

### **2. Which factors should be considered when selecting a Region? (Select TWO.)**

✅ **Correct Answers:**

- **Compliance with data governance and legal requirements**
- **Proximity to your customers**

**Explanation:**
 These two factors are critical:

- Compliance ensures your data meets legal regulations.
- Proximity helps reduce latency and improve user experience.

Other options like AWS CLI access or assigning permissions are available globally and not Region-specific.

------

### **3. Which statement best describes Amazon CloudFront?**

✅ **Correct Answer:**
 **A global content delivery service**

**Explanation:**
 Amazon CloudFront is a **Content Delivery Network (CDN)** that caches and delivers content globally from **edge locations**, improving speed and performance.

------

### **4. Which site does Amazon CloudFront use to cache copies of content for faster delivery to users at any location?**

✅ **Correct Answer:**
 **Edge location**

**Explanation:**
 CloudFront caches content at **edge locations**, which are strategically located globally to serve content with **low latency** to users.

------

### **5. Which action can you perform with AWS Outposts?**

✅ **Correct Answer:**
 **Extend AWS infrastructure and services to different locations including your on-premises data center.**

**Explanation:**
 **AWS Outposts** brings AWS services, infrastructure, and operating models to **on-premises environments**, allowing a **hybrid cloud approach**.
