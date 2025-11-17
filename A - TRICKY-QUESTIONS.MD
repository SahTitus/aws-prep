# **Question:**  
A company wants to migrate a **critical application** to AWS. The application has a **short runtime** and is invoked by **changes in data** or by **shifts in system state**. The company needs a compute solution that **maximizes operational efficiency** and **minimizes cost** of running the application. Which AWS solution should the company use to meet these requirements?.  

**Options:**  
A. Amazon EC2 On-Demand Instances  
B. **AWS Lambda**  
C. Amazon EC2 Reserved Instances  
D. Amazon EC2 Spot Instances  

**Answer:** B. **AWS Lambda**

## Explanation: Why Lambda is the Best Choice
- **Event-driven architecture** – Designed to be invoked by **data changes** or **system state shifts**  
- **Short runtime optimization** – Ideal for applications with **brief execution times**  
- **Maximum operational efficiency** – **No server management**, **automatic scaling**, and **built-in high availability**  
- **Cost optimization** – **Pay only for actual compute time** (billed per millisecond); no charges when code isn't running  
- **Zero idle costs** – Unlike EC2 instances that run continuously, Lambda **eliminates costs during idle periods**


# Question 165
Service that monitors application health automatically:

A. Amazon API Gateway  
B. AWS Elastic Beanstalk  
C. AWS Lambda  
D. AWS Config  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: B. AWS Elastic Beanstalk** ✅  

**Explanation:**  
- **Elastic Beanstalk** manages **deployment, monitoring, and health checks** automatically.

</details>


# Question 113
Which service is natively supported by Snowball Edge?

A. SMS  
B. Aurora  
C. Trusted Advisor  
D. EC2  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: D. Amazon EC2** ✅  

**Explanation:**  
Snowball Edge can run **EC2 instances on the device**.

</details>

# AWS Snowball Edge

**AWS Snowball Edge** natively supports **Amazon EC2**, allowing you to run **compute instances** directly on the device using **EC2-compatible endpoints**.

## Services Natively Supported by Snowball Edge

- **Amazon EC2** – Run **compute instances** with various **vCPU** and **memory options**  
- **Amazon S3** – **Storage** and **data transfer** via **S3-compatible endpoints**  
- **Amazon EBS** – **Block-level storage volumes** for EC2 instances  
- **AWS Lambda** – **Serverless functions** via **AWS IoT Greengrass**  
- **Amazon EKS Anywhere** – **Kubernetes clusters** on Snowball Edge devices  
- **AWS IAM** – **Access control** and **security**


The question asks about **hosted or integrated software solutions from independent providers**.

* **A. AWS TAMs (Technical Account Managers)** – Provide guidance and support, not software solutions. ❌
* **B. APN Consulting Partners** – Provide **advisory, migration, and implementation services**, not hosted software. ❌
* **C. AWS Concierge Support** – Helps with billing and account guidance, not software solutions. ❌
* **D. APN Technology Partners** ✅ – These are **independent software vendors (ISVs)** who provide **hosted or integrated software solutions** on AWS.

✅ **Answer: D. APN Technology Partners**





# Question 134
Tasks requiring root user (Select two):

A. Create EC2 key pair  
B. Remove IAM admin  
C. Change Support plan  
D. Create CloudFront key pair  
E. Give IAM user admin access  

<details>
<summary>Answer & Explanation</summary>

**Correct answers: C, D**  

**Explanation:**  
Only root can **change support plan** and **create CloudFront key pairs**.

</details>


# Question 187

Service for storing data in AWS Cloud:

A. Amazon EFS  
B. Amazon Redshift  
C. Amazon RDS  
D. Amazon VPC  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: A. Amazon EFS** ✅  

**Explanation:**  
- **EFS** provides **scalable file storage in the AWS Cloud**.  
- (Alternatively, S3 could also store data, but EFS is fully managed file storage.)

</details>


# Question 240

A business must keep data near its core consumers. Which AWS Cloud advantage satisfies this?

A. Security  
B. High availability  
C. Elasticity  
D. Global footprint  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: D. Global footprint** ✅  

**Explanation:**  
- AWS has **data centers worldwide**, enabling **low-latency access near users**.

</details>


# Question 238

Example of a decoupled and scalable cloud application:

A. Single EC2 instance for mail/log  
B. Webpage on S3 + Lambda updating DynamoDB  
C. Load balancer, web server, DB for monolithic app  
D. Legacy DB on max-sized instance  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: B. Webpage on S3 + Lambda updating DynamoDB** ✅  

**Explanation:**  
- `**Serverless + managed DB** architecture is **decoupled, scalable, and event-driven**.`

</details>


# Question 271

Which Amazon EC2 pricing model is dynamically adjusted in response to EC2 instance availability and demand?

A. On-Demand Instances  
B. Reserved Instances  
C. Spot Instances  
D. Convertible Reserved Instances  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: C. Spot Instances** ✅  

**Explanation:**  
- **Spot Instances** pricing **fluctuates with supply and demand**.  
- On-Demand is fixed per hour, Reserved is long-term, Convertible Reserved can be exchanged but not dynamic per hour.

</details>


# Question 274

Which choices do users have when contacting AWS Support?

A. Create an email case in AWS Support Center  
B. Visit a local AWS Support Center  
C. Use live chat functionality  
D. Call the customer service phone number  
E. Use video conference functionality  

<details>
<summary>Answer & Explanation</summary>

**Correct answers: A & C** ✅✅  

**Explanation:**  
- Users can **create cases** in AWS Support Center and use **live chat**.  
- AWS Support does **not provide in-person visits, general phone support, or video conferencing**.

</details>

# Question

Which of the following tasks can only be performed after signing in with AWS account root user credentials? (Choose two.)

A. Closing an AWS account  
B. Creating a new IAM policy  
C. Changing AWS Support plans  
D. Attaching a role to an Amazon EC2 instance  
E. Generating access keys for IAM users  

<details>
<summary>Answer & Explanation</summary>

**Correct answers: A. Closing an AWS account & C. Changing AWS Support plans** ✅  

**Explanation:**  
- **A. Closing an AWS account** → Only the root user can close the account entirely.  
- **C. Changing AWS Support plans** → Upgrading or downgrading Support plans requires root user credentials.  

**Why the others are wrong:**  
- **B. Creating a new IAM policy** → Can be done by IAM users with sufficient permissions.  
- **D. Attaching a role to an EC2 instance** → Can be done by IAM users with appropriate permissions.  
- **E. Generating access keys for IAM users** → Can be done by IAM users with required privileges; root user is not required.

</details>



# Question

A company has deployed several relational databases on Amazon EC2 instances. Every month, the database software vendor releases new security patches that need to be applied to the databases.  
What is the MOST efficient way to apply the security patches?

A. Connect to each database instance on a monthly basis, and download and apply the necessary security patches from the vendor.  
B. Enable automatic patching for the instances using the Amazon RDS console.  
C. In AWS Config, configure a rule for the instances and the required patch level.  
D. Use AWS Systems Manager to automate database patching according to a schedule.  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: D. Use AWS Systems Manager to automate database patching according to a schedule** ✅  

**Explanation:**  
- **AWS Systems Manager (SSM)** allows you to automate patch management for EC2 instances, including operating system and database software patches.  
- You can define **patch baselines and schedules**, ensuring all instances are consistently updated without manual intervention.  

**Why the others are wrong:**  
- **A. Manual patching** → Inefficient, error-prone, and does not scale.  
- **B. Amazon RDS automatic patching** → Only applies to RDS-managed databases, not databases running on EC2.  
- **C. AWS Config rule** → Can monitor compliance but **cannot apply patches**.  

</details>



# Question

Which AWS service is used to automate configuration management using Chef and Puppet?

A. AWS Config  
B. AWS OpsWorks  
C. AWS CloudFormation  
D. AWS Systems Manager  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: B. AWS OpsWorks** ✅  

**Explanation:**  
- **AWS OpsWorks** is a configuration management service that supports **Chef and Puppet**, allowing you to **automate server configurations, deployments, and management**.  

**Why the others are wrong:**  
- **A. AWS Config** → Tracks resource configurations and compliance, but does not automate configurations.  
- **C. AWS CloudFormation** → Automates **infrastructure provisioning** via templates, not configuration management with Chef/Puppet.  
- **D. AWS Systems Manager** → Helps manage servers and automate tasks, but OpsWorks specifically integrates **Chef and Puppet**.  

</details>

# Question

What is the MINIMUM AWS Support plan level that will provide users with access to the AWS Support API?

A. Developer  
B. Enterprise  
C. Business  
D. Basic  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: C. Business** ✅  

**Explanation:**  
- The **AWS Support API** allows programmatic access to support cases, Trusted Advisor checks, and support plan details.  
- According to AWS documentation, a **Business, Enterprise On‑Ramp, or Enterprise Support plan** is required to use the Support API.  
- The **Business Support plan** is the **minimum plan** that grants access.  

**Why the others are wrong:**  
- **A. Developer** → Cannot access the AWS Support API.  
- **B. Enterprise** → Higher tier than necessary; provides API access but is not the minimum.  
- **D. Basic** → Free tier; does **not** include AWS Support API access.  

</details>




# Question

Which AWS service or feature requires an internet service provider (ISP) and a colocation facility to be implemented?

A. AWS VPN  
B. Amazon Connect  
C. AWS Direct Connect  
D. Internet gateway  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: C. AWS Direct Connect** ✅  

**Explanation:**  
- **AWS Direct Connect** establishes a **dedicated, private network connection** between your on-premises data center and AWS.  
- Requires:  
  - An **Internet Service Provider (ISP)** to reach the Direct Connect location.  
  - A **colocation facility** where your network equipment can physically connect to AWS routers.  

**Why the others are wrong:**  
- **A. AWS VPN** → Can be implemented over the public internet; does not require colocation.  
- **B. Amazon Connect** → Cloud-based contact center service; no physical connection required.  
- **D. Internet Gateway** → Provides internet access to a VPC; does not require ISP or colocation.  

</details>


# Question

Which AWS service or feature allows the user to manage cross-region application traffic?

A. Amazon AppStream 2.0  
B. Amazon VPC  
C. Elastic Load Balancer  
D. Amazon Route 53  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: D. Amazon Route 53** ✅  

**Amazon Route 53** is a **DNS-based global traffic management service** that allows you to route application traffic across multiple AWS Regions. Features include:

- **Latency-based routing** – Direct users to the region with the lowest latency.  
- **Geolocation routing** – Route traffic based on user location.  
- **Weighted routing** – Split traffic across resources according to specified weights.  
- **Failover routing** – Redirect traffic in case of regional failures.  

**Why the others are wrong:**

- **A. Amazon AppStream 2.0** → Provides streaming of applications, not traffic management.  
- **B. Amazon VPC** → Manages networking within a region, not cross-region traffic.  
- **C. Elastic Load Balancer** → Distributes traffic within a region, not across regions.

</details>


# Question

Which AWS service should a cloud practitioner use to identify security vulnerabilities of an AWS account?

A. AWS Secrets Manager  
B. Amazon Cognito  
C. Amazon Macie  
D. AWS Trusted Advisor  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: D. AWS Trusted Advisor** ✅  

**Explanation:**  
- **AWS Trusted Advisor** provides **security checks and best practice recommendations** for your AWS account, such as:  
  - Overly permissive IAM policies  
  - Open security groups  
  - Exposed access keys  
- It helps identify **vulnerabilities and potential security risks**.  

**Why the others are wrong:**  
- **A. AWS Secrets Manager** → Manages secrets like passwords or API keys; does not scan for vulnerabilities.  
- **B. Amazon Cognito** → Provides user authentication and identity management; not a security audit tool.  
- **C. Amazon Macie** → Detects sensitive data in S3, not general account vulnerabilities.  

</details>




# Question

Which AWS service can be used to track unauthorized API calls?

A. AWS Config  
B. AWS CloudTrail  
C. AWS Trusted Advisor  
D. Amazon Inspector  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: B. AWS CloudTrail** ✅  

**AWS CloudTrail** records all **API calls made in your AWS account**, including calls made by:

- IAM users  
- Roles  
- AWS services  

This allows you to **track unauthorized or unexpected API activity**, helping with security audits and compliance.

**Why the others are wrong:**

- **A. AWS Config** → Tracks **configuration changes**, not API calls.  
- **C. AWS Trusted Advisor** → Provides **best practice checks**, not detailed API logging.  
- **D. Amazon Inspector** → Performs **vulnerability assessments**, not API tracking.  

</details>



# Question

What can be used to reduce the cost of running Amazon EC2 instances? (Choose two.)

A. Spot Instances for stateless and flexible workloads  
B. Memory optimized instances for high-compute workloads  
C. On-Demand Instances for high-cost and sustained workloads  
D. Reserved Instances for sustained workloads  
E. Spend limits set using AWS Budgets  

<details>
<summary>Answer & Explanation</summary>

**Correct answers: A and D** ✅  

### A. Spot Instances for stateless and flexible workloads
- Spot Instances provide **up to 90% discount** compared to On-Demand instances.  
- Best for **flexible, fault-tolerant workloads** that can handle interruptions.  

### D. Reserved Instances for sustained workloads
- Reserved Instances give **up to 72% savings** for workloads that run **continuously over 1–3 years**.  
- Ideal for **predictable, long-running workloads**.  

**Why the others are wrong:**

- **B. Memory optimized instances** → Choosing an instance type, not a cost-reduction mechanism.  
- **C. On-Demand Instances** → Most expensive option for sustained workloads.  
- **E. Spend limits set using AWS Budgets** → Only tracks or alerts spending; does **not reduce EC2 cost**.

</details>




# Question

A user is planning to launch two additional Amazon EC2 instances to increase availability.  
Which action should the user take?

A. Launch the instances across multiple Availability Zones in a single AWS Region.  
B. Launch the instances as EC2 Reserved Instances in the same AWS Region and the same Availability Zone.  
C. Launch the instances in multiple AWS Regions, but in the same Availability Zone.  
D. Launch the instances as EC2 Spot Instances in the same AWS Region, but in different Availability Zones.  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: A. Launch the instances across multiple Availability Zones in a single AWS Region** ✅  

**Explanation:**  
- To **increase availability**, instances should be distributed across **multiple Availability Zones (AZs)** within a single AWS Region.  
- This protects against **AZ-level failures** while maintaining low-latency network connectivity.  

**Why the others are wrong:**  
- **B. Reserved Instances in the same AZ** → Reduces cost, not improves availability.  
- **C. Multiple Regions but same AZ** → AZs do not span regions; this is not feasible.  
- **D. Spot Instances** → Spot Instances are cost-effective but can be **interrupted**, which does not guarantee high availability.

</details>



# Question

A company must store critical business data in Amazon S3 with a backup to another AWS Region.  
How can this be achieved?

A. Use an Amazon CloudFront Content Delivery Network (CDN) to cache data globally  
B. Set up Amazon S3 cross-region replication to another AWS Region  
C. Configure the AWS Backup service to back up the data to another AWS Region  
D. Take Amazon S3 bucket snapshots and copy that data to another AWS Region  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: B. Set up Amazon S3 cross-region replication (CRR) to another AWS Region** ✅  

**Explanation:**  
- **S3 Cross-Region Replication (CRR)** automatically replicates objects from a source S3 bucket to a destination bucket in another AWS Region.  
- Ensures **business continuity** and **disaster recovery** for critical data.  

**Why the others are wrong:**  
- **A. CloudFront CDN** → Caches data for faster access; does **not store a backup**.  
- # **C. AWS Backup** → Can back up certain services, but S3 CRR is the standard for cross-region replication.  
- **D. S3 bucket snapshots** → S3 does not use snapshots like EBS; manual copying is error-prone and not automatic.

</details>



# Question

What is the recommended method to request penetration testing on AWS resources?

A. Open a support case  
B. Fill out the Penetration Testing Request Form  
C. Request a penetration test from your technical account manager  
D. Contact your AWS sales representative  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: A. Open a support case** ✅  

**Explanation:**  
- AWS allows customers to conduct **penetration testing** on certain services **without prior approval** for predefined tests on allowed services (like EC2, Lambda, RDS, etc.).  
- For tests that are **outside the allowed scope**, you must **open a support case** with AWS Security to request approval.  
- This is the official method listed in AWS documentation for requesting penetration testing on resources not covered by the self-service allowed tests.

**Why the others are wrong:**  
- **B. Penetration Testing Request Form** → Deprecated; AWS no longer uses a separate form.  
- **C. Technical account manager** → TAMs do not approve penetration tests.  
- **D. Sales representative** → Sales cannot approve security testing requests.  

</details>



# Question

Which components are required to build a successful site-to-site VPN connection on AWS? (Choose two.)

A. Internet gateway  
B. NAT gateway  
C. Customer gateway  
D. Transit gateway  
E. Virtual private gateway  

<details>
<summary>Answer & Explanation</summary>

**Correct answers: C and E** ✅  

### C. Customer Gateway
- Represents the **on-premises VPN device** (hardware or software) at your side of the VPN connection.  
- Provides AWS with information about the device’s **public IP address and routing**.

### E. Virtual Private Gateway
- Represents the **AWS side of the VPN connection**.  
- Attached to your **VPC**, allowing secure encrypted traffic from your on-premises network.

**Why the others are wrong:**

- **A. Internet Gateway** → Enables internet access to a VPC, not required for a VPN.  
- **B. NAT Gateway** → Used for outbound internet access from private subnets; unrelated to VPN.  
- **D. Transit Gateway** → Optional for connecting multiple VPCs or VPNs, but not strictly required for a single site-to-site VPN.  

</details>


# Question

What is the MOST effective resource for staying up to date on AWS security announcements?

A. AWS Personal Health Dashboard  
B. AWS Secrets Manager  
C. AWS Security Bulletins  
D. Amazon Inspector  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: C. AWS Security Bulletins** ✅  

**Explanation:**  
- **AWS Security Bulletins** provide official information about **security updates, patches, and vulnerabilities** affecting AWS services.  
- This is the most reliable and up-to-date resource for staying informed about AWS security issues.  

**Why the others are wrong:**  
- **A. AWS Personal Health Dashboard** → Shows the health status of your **specific AWS resources**, not general security announcements.  
- **B. AWS Secrets Manager** → Manages secrets like passwords or API keys; unrelated to security bulletins.  
- **D. Amazon Inspector** → Performs security assessments of your AWS resources but does not provide general security announcements.  

</details>



# Question

Which requirement must be met for a member account to be unlinked from an AWS Organizations account?

A. The linked account must be actively compliant with AWS System and Organization Controls (SOC).  
B. The payer and the linked account must both create AWS Support cases to request that the member account be unlinked from the organization.  
C. The member account must meet the requirements of a standalone account.  
D. The payer account must be used to remove the linked account from the organization.  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: C. The member account must meet the requirements of a standalone account** ✅  

**Explanation:**  
- To **remove a member account** from an AWS Organization, the account must be able to operate independently as a **standalone AWS account**.  
- This ensures it can manage billing, IAM users, and services outside of the organization.  

**Why the others are wrong:**  
- **A. SOC compliance** → Not required to unlink an account.  
- **B. Both accounts creating support cases** → Not required; unlinking is handled through the Organizations console or API.  
- **D. Payer account removal** → While the master account initiates the removal, the key requirement is that the member account meets standalone criteria.  

</details>



# Question

Which of the following assist in identifying costs by department? (Choose two.)

A. Using tags on resources  
B. Using multiple AWS accounts  
C. Using an account manager  
D. Using AWS Trusted Advisor  
E. Using Consolidated Billing  

<details>
<summary>Answer & Explanation</summary>

**Correct answers: A and B** ✅  

### A. Using tags on resources
- **Resource tagging** allows you to assign metadata to AWS resources (like `Department: Finance`).  
- Tags can then be used in **Cost Allocation Reports** to track costs per department.  

### B. Using multiple AWS accounts
- Creating separate accounts per department allows **isolated billing**.  
- You can still use **AWS Organizations with Consolidated Billing** to get an overall view, while seeing costs per account.  

**Why the others are wrong:**  
- **C. Using an account manager** → Helpful for guidance, but does not directly track costs.  
- **D. AWS Trusted Advisor** → Provides best practice recommendations, not cost tracking.  
- **E. Consolidated Billing** → Aggregates bills for multiple accounts but does not by itself separate costs by department; must be combined with accounts or tags.  

</details>


# Question

A company wants to allow full access to an Amazon S3 bucket for a particular user.  
Which element in the S3 bucket policy holds the user details that describe who needs access to the S3 bucket?

A. Principal  
B. Action  
C. Resource  
D. Statement  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: A. Principal** ✅  

**Explanation:**  
- In an **S3 bucket policy**, the **`Principal`** element specifies **who (which user, role, or account)** is allowed or denied access to the bucket.  
- It can include **IAM users, roles, or AWS accounts**.  

**Why the others are wrong:**  
- **B. Action** → Specifies **what actions** (like `s3:GetObject` or `s3:PutObject`) are allowed or denied.  
- **C. Resource** → Specifies **which bucket or object** the policy applies to.  
- **D. Statement** → A policy can contain multiple statements; it is a container for `Effect`, `Principal`, `Action`, and `Resource`.  

</details>


# Question

A company is piloting a new customer-facing application on Amazon Elastic Compute Cloud (Amazon EC2) for one month.  
What pricing model is appropriate?

A. Reserved Instances  
B. Spot Instances  
C. On-Demand Instances  
D. Dedicated Hosts  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: C. On-Demand Instances** ✅  

**Explanation:**  
- **On-Demand Instances** allow you to pay **by the hour or second** with no long-term commitment.  
- Ideal for **short-term workloads**, testing, or pilot projects where usage duration is uncertain.  

**Why the others are wrong:**  
- **A. Reserved Instances** → Require 1- or 3-year commitment; not cost-effective for a one-month pilot.  
- **B. Spot Instances** → Can be interrupted at any time; not ideal for customer-facing applications.  
- **D. Dedicated Hosts** → Provide physical servers for compliance/licensing; unnecessary for a temporary pilot.  

</details>


# Question

A company wants to ensure that AWS Management Console users are meeting password complexity requirements.  
How can the company configure password complexity?

A. Using an AWS IAM user policy  
B. Using an AWS Organizations service control policy (SCP)  
C. Using an AWS IAM account password policy  
D. Using an AWS Security Hub managed insight  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: C. Using an AWS IAM account password policy** ✅  

**Explanation:**  
- **IAM account password policies** allow administrators to enforce **password complexity requirements** for AWS Management Console users, including:  
  - Minimum length  
  - Required character types (uppercase, lowercase, numbers, symbols)  
  - Password expiration and reuse rules  

**Why the others are wrong:**  
- **A. IAM user policy** → Controls permissions for API actions, not password complexity.  
- **B. Service Control Policy (SCP)** → Restricts actions across accounts in AWS Organizations, not password rules.  
- **D. Security Hub managed insight** → Provides security findings and recommendations, but cannot enforce password policies.  

</details>



# Question

A workload on AWS will run for the foreseeable future by using a consistent number of Amazon EC2 instances.  
What pricing model will minimize cost while ensuring that compute resources remain available?

A. Dedicated Hosts  
B. On-Demand Instances  
C. Spot Instances  
D. Reserved Instances  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: D. Reserved Instances** ✅  

**Explanation:**  
- **Reserved Instances (RIs)** provide a **significant discount (up to 72%)** compared to On-Demand prices in exchange for a **1- or 3-year commitment**.  
- Ideal for workloads with **predictable, consistent usage**, ensuring resources are **always available**.  

**Why the others are wrong:**  
- **A. Dedicated Hosts** → Physical servers for licensing or compliance; more expensive and unnecessary here.  
- **B. On-Demand Instances** → Flexible, but more costly for long-running, consistent workloads.  
- **C. Spot Instances** → Cheapest option, but **can be interrupted**; not suitable for guaranteed availability.  

</details>


# Question

Which tool can be used to identify scheduled changes to the AWS infrastructure?

A. AWS Personal Health Dashboard  
B. AWS Trusted Advisor  
C. Billing Dashboard  
D. AWS Config  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: A. AWS Personal Health Dashboard** ✅  

**Explanation:**  
- The **AWS Personal Health Dashboard (PHD)** provides alerts and notifications about **scheduled changes, ongoing events, and potential issues** that may affect your AWS resources.  
- It gives **personalized guidance** for your account, unlike general service status pages.  

**Why the others are wrong:**  
- **B. AWS Trusted Advisor** → Provides best practice checks and recommendations, not scheduled change alerts.  
- **C. Billing Dashboard** → Shows cost and usage; unrelated to infrastructure changes.  
- **D. AWS Config** → Tracks **configuration changes and compliance**, but does not notify you of **scheduled AWS events**.  

</details>


# Question

What is the customer’s responsibility when using AWS Lambda?

A. Operating system configuration  
B. Application management  
C. Platform management  
D. Code encryption  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: B. Application management** ✅  

**Explanation:**  
- In **AWS Lambda**, AWS manages the underlying infrastructure, operating system, and runtime environment.  
- The **customer is responsible for writing, deploying, and managing their application code**.  

**Why the others are wrong:**  
- **A. Operating system configuration** → Managed by AWS; customers do not configure the OS.  
- **C. Platform management** → AWS handles the platform, including scaling, patching, and runtime.  
- **D. Code encryption** → Optional; customers may encrypt code or data, but it’s not a core responsibility for Lambda execution.  

</details>





# Question

Which AWS service enables users to create copies of resources across AWS Regions?

A. Amazon ElastiCache  
B. AWS CloudFormation  
C. AWS CloudTrail  
D. AWS Systems Manager  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: B. AWS CloudFormation** ✅  

**Explanation:**  
- **AWS CloudFormation** (specifically **StackSets**) allows users to **deploy and replicate infrastructure resources across multiple AWS Regions and multiple AWS accounts**.  
- This is the primary AWS service used to copy and maintain consistent infrastructure across Regions.

**Why the others are wrong:**  
- **A. Amazon ElastiCache** → In-memory caching service; does not replicate resources across Regions.  
- **C. AWS CloudTrail** → Records API calls; does not create or copy resources.  
- **D. AWS Systems Manager** → Manages and automates operations on resources but does not replicate them across Regions.

</details>


# Question

Which AWS container service will help a user install, operate, and scale the cluster management infrastructure?

A. Amazon Elastic Container Registry (Amazon ECR)  
B. AWS Elastic Beanstalk  
C. Amazon Elastic Container Service (Amazon ECS)  
D. Amazon Elastic Block Store (Amazon EBS)  

<details>
<summary>Answer & Explanation</summary>

**Correct answer: C. Amazon Elastic Container Service (Amazon ECS)** ✅  

**Explanation:**  
- **Amazon ECS** is a fully managed container orchestration service.  
- AWS handles the **installation, operation, and scaling of the cluster management infrastructure**, so the user does not need to manage control plane servers.

**Why the others are wrong:**  
- **A. Amazon ECR** → Stores container images; does not manage clusters.  
- **B. AWS Elastic Beanstalk** → Deploys applications, but does not provide container cluster orchestration infrastructure.  
- **D. Amazon EBS** → Block storage service; unrelated to containers.

</details>
