## Module 7: Monitoring and Analytics

### <u>**Amazon CloudWatch**</u>

**Amazon CloudWatch** is a monitoring and observability service that collects and tracks metrics from AWS resources. It automatically generates performance graphs over time and enables proactive management of resources.

#### Key Features:

- **Metrics Monitoring**: Collects performance data (e.g., CPU usage, request counts) from AWS services.
- **CloudWatch Alarms**: Automatically triggers actions (like stopping EC2 instances) when metrics cross defined thresholds; useful for cost and performance optimization.
- **Dashboards**: Customizable visual panels to view and analyze multiple metrics (e.g., EC2, S3, RDS) in one place, tailored to different applications or teams.

**Use Case**: Automating EC2 instance shutdown if CPU usage is consistently low to avoid unnecessary costs.

------

### <u>**AWS CloudTrail**</u>

**AWS CloudTrail** is a service that records and logs all **API calls and user activity** across your AWS account. It provides detailed insights into **who did what, when, where, and how** within your environment.

#### Key Features:

- **API Call Logging**: Tracks API requests including the caller identity, IP address, time, and actions performed.
- **Event History**: Lets you view and filter historical API activity to support security auditing, troubleshooting, and compliance.
- **Use Case**: If an unknown IAM user appears, CloudTrail helps determine who created the user, when, and how (e.g., console, CLI).
- **CloudTrail Insights**: Automatically detects **unusual activity** (e.g., a spike in EC2 launches) and highlights potential security concerns.

------

### <u>**AWS Trusted Advisor**</u>

**AWS Trusted Advisor** is a web service that analyzes your AWS environment and provides real-time recommendations to help you follow AWS best practices.

#### Key Features:

- Evaluates your setup across five categories:
  - Cost Optimization
  - Performance
  - Security
  - Fault Tolerance
  - Service Limits
- Dashboard indicators:
  - Green Check – No issues found
  - Orange Triangle – Recommended for investigation
  - Red Circle – Recommended actions required

#### Use Cases:

- Helps during new deployments and while improving existing applications.
- Offers actionable insights and links to relevant AWS documentation and best practices.

------

### **Module 7 Summary**

In **Module 7**, you explored key AWS services that support monitoring, auditing, and optimization of your cloud resources:

#### **1. Amazon CloudWatch**

A monitoring service that collects metrics, logs, and events for AWS resources and applications. It allows you to:

- Visualize performance data in real-time dashboards
- Set alarms to trigger actions based on defined thresholds
- Optimize resource usage through data-driven insights

#### **2. AWS CloudTrail**

A service that records API calls made in your AWS account. It helps with:

- Tracking user activity and changes across your infrastructure
- Auditing for compliance and troubleshooting
- Detecting unusual behavior using CloudTrail Insights

#### **3. AWS Trusted Advisor**

An optimization tool that offers real-time best practice recommendations in five key areas:

- Cost Optimization
- Performance
- Security
- Fault Tolerance
- Service Limits

------

### **Additional Learning Resources**

To deepen your understanding of these concepts, explore the following:

- [Management and Governance on AWS(opens in a new tab)](https://aws.amazon.com/products/management-tools)
- [Monitoring and Observability(opens in a new tab)](https://aws.amazon.com/products/management-tools/use-cases/monitoring-and-observability/)
- [Configuration, Compliance, and Auditing(opens in a new tab)](https://aws.amazon.com/products/management-tools/use-cases/configuration-compliance-and-auditing/)
- [AWS Management & Governance Blog(opens in a new tab)](https://aws.amazon.com/blogs/mt/)
- [Whitepaper: AWS Governance at Scale](https://docs.aws.amazon.com/whitepapers/latest/aws-governance-at-scale/introduction.html)

------

### **1. Which actions can you perform using Amazon CloudWatch? (Select TWO.)**

✅ Monitor your resources’ utilization and performance
✅ Access metrics from a single dashboard

------

### **2. Which service enables you to review the security of your Amazon S3 buckets by checking for open access permissions?**

✅ AWS Trusted Advisor

------

### **3. Which categories are included in the AWS Trusted Advisor dashboard? (Select TWO.)**

✅ Performance
✅ Fault tolerance