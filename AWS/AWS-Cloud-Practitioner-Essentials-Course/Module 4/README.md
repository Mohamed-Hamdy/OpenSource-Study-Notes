## **Module 4: Networking**

### <u>Connectivity to AWS</u>

### **Amazon VPC (Virtual Private Cloud)**

- A **private, isolated section of the AWS Cloud** where you define your own virtual network.
- You can organize resources like EC2 instances into **subnets** for better structure and access control.

------

### **Internet Gateway**

- Acts as a **doorway to the internet** for your VPC.
- Needed to allow **public internet access** to your VPC resources (e.g., websites).
- Without it, **external users cannot access** VPC resources.

------

### **Virtual Private Gateway + VPN**

- Used when you want to **access VPC resources privately** (not through public internet).
- Establishes a **VPN connection** between your VPC and a **private network** (e.g., corporate data center).
- **Encrypts traffic**, adding a layer of protection, but still travels over the public internet.

------

### **AWS Direct Connect**

- A **dedicated, private connection** from your data center to AWS (bypasses public internet).
- Offers **lower latency**, **higher bandwidth**, and **more security** compared to VPN.
- Ideal for enterprises needing consistent, high-throughput connectivity.

### <u>**Subnets and Network Access Control Lists**</u>

### Subnets in a VPC

- A subnet is a section of a Virtual Private Cloud (VPC) used to group AWS resources based on security or operational needs.
- Public subnets contain resources that need internet access (e.g., web servers).
- Private subnets contain resources that should only be accessible internally (e.g., databases).
- Subnets within a VPC can communicate with each other.

------

### Network Traffic Flow

- Data requests (packets) enter a VPC through an internet gateway.
- Before entering or exiting a subnet, packets are filtered by Network Access Control Lists (ACLs).
- Once inside a subnet, packets are further filtered by security groups associated with specific resources like EC2 instances.

------

### Network ACLs (Access Control Lists)

- Network ACLs act as firewalls at the subnet level.
- They are **stateless**, meaning they check each packet independently without remembering previous traffic.
- The default network ACL allows all inbound and outbound traffic.
- Custom ACLs deny all traffic by default until specific allow rules are added.
- Every ACL includes an explicit deny rule as a fallback.

------

### Security Groups

- Security groups act as firewalls at the EC2 instance level.
- They are **stateful**, meaning they remember previous traffic and automatically allow return traffic.
- By default, security groups deny all inbound traffic and allow all outbound traffic.
- You can customize rules to allow specific traffic in and out of an instance.

------

### Comparison: Network ACL vs. Security Group

| Feature          | Network ACL            | Security Group                 |
| ---------------- | ---------------------- | ------------------------------ |
| Scope            | Subnet level           | Instance level                 |
| Stateful?        | No (stateless)         | Yes (stateful)                 |
| Default behavior | Allow all (by default) | Deny inbound, allow outbound   |
| Rule application | Checks both directions | Tracks return traffic          |
| Best use case    | Broad subnet control   | Fine-grained instance security |



------

### Key VPC Components Recap

- **Private Subnet**: Used to isolate sensitive data like databases.
- **Public Subnet**: Hosts resources like websites that need public internet access.
- **Virtual Private Gateway**: Enables VPN connection between AWS and a private network.
- **AWS Direct Connect**: Provides a private, high-speed connection from a data center to AWS.



### <u>**Global Networking in AWS**</u>

#### Domain Name System (DNS)

- **Purpose**: Translates domain names (like `anycompany.com`) into IP addresses (like `192.0.2.0`), enabling browsers to locate servers.
- **Analogy**: Functions like the phone book of the internet.
- **How it works**:
  1. A user enters a domain name in the browser.
  2. The customer DNS resolver sends a query to the company’s DNS server.
  3. The DNS server responds with the correct IP address.

#### Amazon Route 53

- A scalable and highly available DNS web service.
- Key capabilities:
  - Routes users to AWS-hosted resources (e.g., EC2 instances, Load Balancers).
  - Can also route traffic to infrastructure outside AWS.
  - Supports domain name registration and DNS record management.
  - Enables centralized domain and DNS configuration.

------

### Example: Route 53 and CloudFront Working Together

1. A customer visits AnyCompany’s website.
2. Route 53 resolves the domain name to its IP address.
3. The request is routed through the nearest Amazon CloudFront edge location.
4. CloudFront forwards the request to an Application Load Balancer, which directs it to an EC2 instance.

### <u></u>

### <u>**Module 4 Summary: AWS Networking Essentials**</u>

In this module, you learned how to:

- **Structure and Connect to a VPC**
  - Create isolated sections of the AWS Cloud using Amazon Virtual Private Cloud (VPC).
  - Connect your VPC to the internet using **Internet Gateways**, or to private networks using **Virtual Private Gateways** and **AWS Direct Connect**.
- **Secure VPC Resources**
  - Use **Network Access Control Lists (ACLs)** to control traffic at the subnet level (stateless filtering).
  - Use **Security Groups** to control traffic at the instance level (stateful filtering).
- **Deliver Content Efficiently**
  - Use **Amazon Route 53** for DNS resolution and routing users to AWS and non-AWS resources.
  - Use **Amazon CloudFront** to deliver content quickly from edge locations around the world.

------

### Additional Learning Resources:

- [Networking and Content Delivery on AWS](https://aws.amazon.com/products/networking)
- [AWS Networking & Content Delivery Blog](https://aws.amazon.com/blogs/networking-and-content-delivery/)
- [Amazon Virtual Private Cloud](https://aws.amazon.com/vpc)
- [What is Amazon VPC?](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
- [How Amazon VPC works](https://docs.aws.amazon.com/vpc/latest/userguide/how-it-works.html)