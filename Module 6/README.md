## Module 6: Security

### AWS Shared Responsibility Model

The **AWS Shared Responsibility Model** outlines how security and compliance responsibilities are shared between AWS and the customer.

#### AWS Responsibilities – *Security of the Cloud*

AWS is responsible for protecting the infrastructure that runs AWS services. This includes:

- Physical security of data centers
- Hardware and software infrastructure
- Network and virtualization layers
- Maintaining the host operating system and global infrastructure (Regions, Availability Zones, edge locations)

AWS ensures this security through rigorous controls and third-party audits.

#### Customer Responsibilities – *Security in the Cloud*

The customer is responsible for securing the resources they create and manage in AWS. This includes:

- Managing access controls and permissions (e.g., S3 object access)
- Configuring and patching operating systems on EC2 instances
- Managing user accounts and network settings (like security groups)
- Deciding how data is stored, encrypted, and accessed

**Analogy:**
 AWS acts as a homebuilder, ensuring a solid, secure house. The customer is like the homeowner, responsible for locking doors and securing personal belongings inside.

------

### **User Permissions and Access**

**AWS Identity and Access Management (IAM)** helps you securely manage access to AWS services and resources.

#### **1. AWS Root User**

- Created when you first open your AWS account.
- Has **full access** to all AWS services.
- **Best Practice:** Use the root user **only for tasks that require it** (e.g., changing support plans). Create an IAM user for daily tasks.

------

#### **2. IAM Users**

- Represent people or applications interacting with AWS.
- Created with **no permissions** by default.
- **Best Practice:** Create **individual IAM users** for each person, even if they need the same permissions.

------

#### **3. IAM Policies**

- JSON documents that **allow or deny permissions**.
- Used to assign specific access levels to users, groups, or roles.
- **Best Practice:** Apply the **principle of least privilege** – grant only the permissions needed.

------

#### **4. IAM Groups**

- Collections of IAM users.
- Assign permissions to groups instead of individual users.
- **Best Practice:** Use groups to manage permissions for users with similar roles efficiently.

------

#### **5. IAM Roles**

- Used for **temporary access**.
- Can be assumed by IAM users, AWS services, or applications.
- When a user assumes a role, they **drop previous permissions** and **gain the role's permissions**.
- **Best Practice:** Use IAM roles for **task-based or time-limited access**, such as rotating responsibilities.

------

#### **6. Multi-Factor Authentication (MFA)**

- Adds an **extra layer of security** beyond a username and password.
- Requires a second form of verification (e.g., a smartphone code or hardware device).
- **Best Practice:** Enable MFA for **both the root user and all IAM users**.

------

### **AWS Organizations**

**AWS Organizations** allows you to **consolidate and manage multiple AWS accounts** from a central location.

------

#### **Key Features:**

- **Root**: The parent container created automatically when an organization is set up. All accounts fall under this root.
- **Service Control Policies (SCPs)**:
   Used to centrally **control permissions** across accounts.
  - SCPs define what **services, actions, or resources** users and roles in an account can or cannot access.
  - SCPs apply to **accounts or organizational units (OUs)** — **not** directly to individual IAM users, groups, or roles.
- **Consolidated Billing**:
   Enables a single bill for all accounts in your organization. Covered in more detail in another module.

------

#### **Organizational Units (OUs):**

- OUs are **logical groupings** of AWS accounts within an organization.
- You can apply SCPs to an OU; **all accounts in that OU inherit the policy**.
- Useful for organizing based on **business functions**, **security needs**, or **regulatory compliance**.

------

#### **Example Scenario:**

1. A company has separate AWS accounts for **Finance, IT, HR, and Legal**.
2. Finance and IT accounts are placed **directly under the root** because they have unique needs.
3. HR and Legal accounts are placed **together in an OU** because they share similar service access needs.
4. A **single SCP** applied to that OU automatically controls access for both departments.

------

#### **Important Notes:**

- IAM users, groups, and roles are still used within each account to manage access.
- SCPs **do not grant permissions**; they only **restrict** what permissions can be granted within the account.
- Best used to **enforce security boundaries** and ensure accounts cannot exceed certain permissions.

------

### **AWS Compliance**

**Compliance** ensures that your company adheres to specific industry standards, often verified through audits or inspections.

------

### **AWS Artifact**

**AWS Artifact** is a **centralized service** that provides:

- **On-demand access** to AWS **security and compliance reports**
- Tools to **review and manage agreements** with AWS

It has two main sections:

#### 1. **AWS Artifact Agreements**

- Lets you **review, accept, and manage agreements** with AWS
- Applicable to **individual accounts** and **entire organizations** (via AWS Organizations)
- Especially useful for industries subject to regulations like **HIPAA**

#### 2. **AWS Artifact Reports**

- Provides **third-party audit reports** verifying AWS compliance with:
  - Global
  - Regional
  - Industry-specific standards
- Common reports include:
  - **ISO certifications**
  - **PCI reports**
  - **SOC (Service Organization Control) reports**
- These reports can be used as evidence in **audits and regulatory reviews**

------

### **Customer Compliance Center**

A dedicated AWS resource hub for learning about compliance:

- **Compliance stories** from AWS customers in regulated industries
- **Whitepapers and documentation** on:
  - AWS risk and compliance overview
  - Common compliance questions
  - Security auditing checklist
- **Auditor learning path** for those in legal, compliance, or auditing roles

------

### **Denial-of-Service (DoS) Attacks**

#### **DoS Attack Overview**

A **Denial-of-Service (DoS) attack** is an intentional effort to make a website or application **unavailable to legitimate users** by overwhelming it with traffic.

- A **single attacker** sends excessive requests.
- The application becomes too busy to respond to real users.

#### **Distributed Denial-of-Service (DDoS) Attacks**

In a **DDoS attack**, the flood of traffic comes from **multiple sources**:

- This makes it much harder to block all attackers.
- Often involves a **botnet** — a network of compromised devices controlled by an attacker.

------

### **AWS Shield — Protection Against DDoS**

#### **1. AWS Shield Standard**

- **Free** and **automatically enabled** for all AWS customers.
- Protects against **common, frequently occurring DDoS attacks**.
- Uses real-time traffic analysis to detect and mitigate malicious traffic.

#### **2. AWS Shield Advanced**

- **Paid service** with more advanced features:
  - **Sophisticated DDoS attack detection and mitigation**
  - **Detailed diagnostics** and visibility
  - **Integration** with:
    - Amazon CloudFront
    - Amazon Route 53
    - Elastic Load Balancing
    - AWS WAF (for custom rule creation)

------

### **Coffee Shop Analogy (To Simplify)**

- A prankster calls a coffee shop repeatedly to block the line — **like a DoS attack**.
- The prankster gets multiple friends to do the same — **like a DDoS attack**.
- The shop struggles to take real customer orders due to this flood of fake calls — **services become unavailable**.

------

## **Additional AWS Security Services **

### **1. AWS Key Management Service (KMS)**

AWS KMS helps **encrypt and decrypt** data using **cryptographic keys**.

- Supports encryption at rest and in transit
- Create, manage, and control cryptographic keys
- IAM-based access control to keys
- Keys never leave AWS KMS; you remain in full control
- Option to disable keys temporarily

**Use Case**: Secure your application data both while stored and during transmission.

------

### **2. AWS Web Application Firewall (WAF)**

AWS WAF filters and monitors HTTP(S) requests to protect applications.

- Works with Amazon CloudFront and Application Load Balancer
- Uses web ACLs (Access Control Lists)
- Block or allow traffic based on:
  - IP addresses
  - Query strings
  - Headers, etc.

**Use Case**: Block malicious traffic like IPs performing SQL injection or cross-site scripting while allowing legitimate users through.

------

### **3. Amazon Inspector**

Amazon Inspector runs **automated security assessments** on AWS resources.

- Identifies vulnerabilities and deviations from best practices
- Focus on EC2 instances, containers, and Lambda
- Findings include severity ranking and recommended fixes
- Based on the shared responsibility model: AWS provides insights, customers must take action

**Use Case**: Secure new or existing applications without manual security testing.

------

### **4. Amazon GuardDuty**

Amazon GuardDuty provides **intelligent threat detection**.

- No need for extra security software
- Analyzes logs like VPC Flow Logs, DNS logs, and CloudTrail
- Detects unusual account behavior and potential credential misuse
- Can integrate with AWS Lambda for automatic responses

**Use Case**: Continuously monitor and detect threats in your AWS environment.

------

## **Module 6 Summary**

In this module, you explored essential security concepts and services within AWS. Below are the key topics covered:

------

### **1. Shared Responsibility Model**

- AWS and the customer share responsibility for security and compliance.
  - **AWS is responsible** for securing the cloud infrastructure.
  - **Customers are responsible** for securing their applications, data, and access configurations **in** the cloud.

------

### **2. AWS Identity and Access Management (IAM)**

- IAM allows you to manage access to AWS services and resources securely.
- Core features include:
  - Users, groups, roles, and policies
  - Fine-grained permission control
  - Multi-factor authentication (MFA)

------

### **3. AWS Organizations**

- Consolidates and centrally manages multiple AWS accounts.
- Enables:
  - Centralized billing
  - Organizational Units (OUs) for grouping accounts
  - Service Control Policies (SCPs) for managing permissions across accounts

------

### **4. Compliance Resources**

- AWS offers tools and documentation to help customers meet compliance requirements:
  - **AWS Artifact** for reports and agreements
  - **Customer Compliance Center** with whitepapers, checklists, and real-world compliance stories

------

### **5. Application Security and Encryption Services**

Key AWS security tools include:

- **AWS Key Management Service (KMS)** – Manage and use cryptographic keys for data encryption.
- **AWS WAF** – Protect web applications by filtering incoming traffic.
- **Amazon Inspector** – Run automated security assessments.
- **Amazon GuardDuty** – Detect threats by monitoring network and account activity.
- **AWS Shield** – Protect against DDoS attacks (Standard and Advanced levels).

------

### **Additional Resources to Explore**

- [Security, Identity, and Compliance on AWS(opens in a new tab)](https://aws.amazon.com/products/security)
- [Whitepaper: Introduction to AWS Security(opens in a new tab)](https://docs.aws.amazon.com/whitepapers/latest/introduction-aws-security/welcome.html)[(opens in a new tab)](https://docs.aws.amazon.com/whitepapers/latest/aws-security-best-practices/know-the-aws-shared-responsibility-model.html)
- [Whitepaper: Amazon Web Services - Overview of Security Processes(opens in a new tab)](https://docs.aws.amazon.com/whitepapers/latest/aws-overview-security-processes/aws-overview-security-processes.pdf)
- [AWS Security Blog(opens in a new tab)](https://aws.amazon.com/blogs/security/)
- [AWS Compliance(opens in a new tab)](https://aws.amazon.com/compliance)
- [AWS Customer Stories: Security, Identity, and Compliance(opens in a new tab)](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc|product%23api-gateway|product%23cloudfront|product%23route53|product%23directconnect|product%23elb&awsf.customer-references-category=category%23security-identity-compliance)
- [Security best practices in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)

### **1. Which statement best describes an IAM policy?**

✅ **A document that grants or denies permissions to AWS services and resources**

------

### **2. An employee requires temporary access to create several Amazon S3 buckets. Which option would be the best choice for this task?**

✅ **IAM role**

------

### **3. Which statement best describes the principle of least privilege?**

✅ **Granting only the permissions that are needed to perform specific tasks**

------

### **4. Which service helps protect your applications against distributed denial-of-service (DDoS) attacks?**

✅ **AWS Shield**

------

### **5. Which task can AWS Key Management Service (AWS KMS) perform?**

✅ **Create cryptographic keys**