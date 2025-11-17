# AWS Systems Manager Session Manager
 **Session Manager** is a **node management service** for the cloud or for on-premises compute units.
 **Session Manager** provides a **secure connection through shell scripting**. You can establish the **connection without the need to open ports.**

# A company wants to improve its security and audit posture by limiting Amazon EC2 inbound access.
# What should the company use to access instances remotely instead of opening inbound SSH ports and managing SSH keys?
* **AWS Systems Manager Session Manager**


# **A. AWS Security Hub**

### **Explanation:**

* **AWS Security Hub** is a **Cloud Security Posture Management (CSPM)** service.
* It **aggregates security findings** from multiple AWS services (like GuardDuty, Inspector, Macie) and supported partner products into a **centralized, standardized view**.
* Provides **security alerts and compliance checks** to help organizations monitor and improve their security posture.

**Other options:**

* **B. AWS Trusted Advisor:** Offers best practice recommendations for cost, performance, and security — not CSPM.

* **D. Amazon GuardDuty:** Threat detection service, but it **does not aggregate findings from multiple sources** like Security Hub does.


✅ **Correct Answer:**
**A. Amazon Macie**

* **Amazon Macie** is a **security service** that uses **machine learning** to:

  * **Discover sensitive data** (like **PII** or **financial information**) in **Amazon S3 buckets**
  * **Classify and protect data** automatically
  * Provide **alerts** and **dashboards** for **data security** and **compliance monitoring**

**Other options:**

* **B. Amazon Detective:** Investigates and visualizes **security issues** and **potential threats**.
* **C. Amazon GuardDuty:** Detects **malicious activity** and **threats** across AWS accounts, but doesn’t classify data.
* **D. AWS IAM Access Analyzer:** Analyzes **resource policies** for **unintended access**, not sensitive data discovery.


Good question 👍

Here’s the **difference** 👇

| Feature             | **Security Group (SG)**                              | **Network ACL (NACL)**                                  |
| ------------------- | ---------------------------------------------------- | ------------------------------------------------------- |
| **Level**           | Instance level (attached to EC2)                     | Subnet level (applies to all instances in subnet)       |
| **Traffic control** | Controls **inbound/outbound** for specific instances | Controls **inbound/outbound** for the entire **subnet** |
| **Stateful**        | ✅ Yes (responses automatically allowed)              | ❌ No (need explicit inbound/outbound rules)             |
| **Used for**        | Protecting specific **resources**                    | Setting general **subnet-wide firewall rules**          |

👉 So, the question specifically says:

> “...control traffic going into and coming out of an **Amazon VPC subnet**.”

That’s why the correct answer is **D. Network ACL**, not Security Group.





**GuardDuty** is a **threat detection** service that can monitor AWS accounts and workloads for **malicious activity**. **GuardDuty** can **generate security findings and remediation suggestions.** 






#
#
#
#
#




---

# **Authentication, Authorization & AWS Shared Responsibility Model**

## **Authentication and Authorization**

**Authentication**
Authentication is the process of **verifying the identity** of a user or entity using credentials such as **username and password**.

**Use case:** An employee logs into an employee portal.

**Authorization**
Authorization determines the **access rights and permissions** a user has after authentication, defining **which actions they can perform** in a system.

**Use case:** An employee can access **only their own employee records** inside the portal.

These two work together: you first prove **who you are** (authentication), then the system decides **what you can do** (authorization).

---

## **AWS Shared Responsibility Model**

AWS cloud security is split into **Security in the cloud** (customer responsibility) and **Security of the cloud** (AWS responsibility).

### **Customers: Security in the cloud**

Customers are responsible for **everything they create, store, configure, and manage** inside AWS. This includes:

* Managing the **security of data, systems, and applications**
* Deciding **what data and workloads** to run in AWS
* Determining **which AWS services** to use
* Controlling **who has access** to AWS environments and resources

In short, customers secure **their content, applications, configurations, and identity/access controls**.

---

### **AWS: Security of the cloud**

AWS manages and secures the **infrastructure that runs AWS services**. This includes:

* The **foundational software** powering AWS services
* The **virtualization layer**
* The **hardware and global infrastructure**, including:

  * **AWS Regions**
  * **Availability Zones**
  * **Edge locations**

AWS ensures the **physical security**, **network infrastructure**, and **core platform** are protected.

---

## **AWS Security Controls**

AWS provides multiple security control mechanisms to help customers:

* **Prevent** security incidents through proper permissions and access management
* **Protect** networks, applications, and data
* **Detect and respond** to security incidents as they occur

These controls work together to strengthen privacy, protect systems, and maintain the overall security posture in the AWS Cloud.

---





Here’s a **proper, exam-ready Markdown summary** of your AWS IAM content, keeping **all keywords intact** and ensuring it’s meaningful, not shallow or over-paraphrased.

---

# **AWS Identity and Access Management (IAM)**

## **Purpose**

* Securely **manage identities** and **access** to AWS services and resources.
* Prevent security incidents through **proper permission and access management**.

---

## **Default Behavior**

* **All actions are denied by default**.
* You must **explicitly grant permission** for users to perform actions.

---

## **Principle of Least Privilege**

* Provide **access only on a need-to-have basis**.
* Only give **people and systems access to what they need and nothing else**.

---

## **IAM Components**

* **Users** — individual identities accessing AWS resources.
* **Groups** — collections of users; permissions assigned to the group are inherited by all members.
* **Roles** — temporary identities that can be assumed to gain specific permissions.
* **Policies** — JSON documents defining **permissions and access levels** for users, groups, or roles.

---

## **Key Takeaways**

* Configure access according to your company’s **specific operational and security needs**.
* IAM policies **define the access required** for each identity.
* Proper IAM setup is one of the best ways to **prevent security incidents**.

---


## **AWS Account Root User**

* Every AWS account has a **root user**, who is the **account owner**.
* **Permissions:** Full access to everything in the account.
* **Best Practices:**

  * Use a **strong password**.
  * Enable **multi-factor authentication (MFA)** — requires **at least two verification methods** to log in.
* **Daily operations:** Should be performed by **other IAM identities** (not the root user).

---

## **IAM Users**

* An **IAM user** represents a **person or application** that interacts with AWS services and resources.
* **Components:** Name + credentials.
* **Best Practice:** Create **individual IAM users** for each person who needs access.
* **Benefit:** Each user has a **unique set of security credentials**.

---

## **IAM Groups**

* An **IAM group** is a **collection of IAM users**.
* **Permissions:** Assign permissions to a group → **all users inherit** the permissions.
* **Example:** Group called `employees` can have **standard access**, automatically applied to all employees.

---

## **IAM Roles**

* An **IAM role** is an **identity you can assume** to gain **temporary access** to permissions.
* **Behavior:**

  * Assumes the role → abandons previous permissions → **inherits new role permissions**.
* **Example:** An employee might act as a **barista in the morning** and a **cashier in the afternoon**.

---

## **IAM Policies**

* An **IAM policy** is a **JSON document** that allows or denies **access to AWS services and resources**.
* **Capabilities:**

  * Define **level of access** (full, limited, read-only).
  * Can be applied to **users, groups, or roles**.
* **Example:** Allow access to **all S3 buckets** or restrict to **a specific bucket**.

---

## **IAM Principles**

### **Permission Management**

* By default, **all actions are denied** in IAM.
* You must **explicitly grant permission** to allow actions.

### **Principle of Least Privilege**

* Grant **only the access needed**, and **nothing more**.
* Ensures minimal exposure to security risks.

### **IAM Components**

* **Users** — individual identities.
* **Groups** — collections of users sharing permissions.
* **Roles** — temporary identities for specific tasks.
* **Policies** — define **access and permissions** for identities.

---

## **IAM Security Best Practices**

* Secure **AWS accounts** and **resources** with proper IAM management.
* Use **multiple security control mechanisms** to:

  * Prevent unauthorized access
  * Protect networks, applications, and data
  * Detect and respond to security incidents

---






---

# **Additional AWS Access Management Services — Exam Summary**

## **Purpose**

* Enforce the **principle of least privilege** across AWS environments.
* Streamline **administration** while **bolstering security practices**.

---

## **AWS IAM Identity Center**

* Centralizes **identity and access management** across AWS accounts and applications.
* Can connect to an **existing identity source**.
* Provides **single sign-on (SSO)** access to connected AWS services and accounts.
* Supports **federated identity management**:

  * Allows users to access multiple **applications, services, or domains** using a single set of credentials.

---

## **AWS Secrets Manager**

* Provides a secure way to **manage, rotate, and retrieve secrets** such as:

  * Database credentials
  * API keys
  * Passwords
* Protects **applications, services, and IT resources** throughout the **secret lifecycle**.
* **Secrets** are confidential information intended to be known only to specific individuals or groups.

---

## **AWS Systems Manager**

* Provides a **centralized view of nodes** across accounts, Regions, and multi-cloud/hybrid environments.
* Enables quick access to **node information**, such as:

  * Node ID
  * Operating system details
* Supports **automation** of:

  * Registry edits
  * User management
  * Security patching

*Nodes* are connection points in a network, system, or structure.

---

## **Key IAM Concepts & Scenarios**

### **Multi-Factor Authentication (MFA)**

* Adds an **additional layer of security** for root user accounts.
* Requires **two or more verification methods** to gain access.
* Example: Password + one-time code from smartphone app.

### **IAM Roles**

* Provides **temporary access to permissions**.
* When assumed, previous permissions are abandoned and **new role permissions** are applied.

### **IAM Policies**

* **JSON documents** that allow or deny access to AWS services/resources.
* Can be assigned to **IAM users, groups, or roles**.
* Example: Grant accountants access to a specific **Amazon S3 bucket**.

### **Secrets Management**

* Teams can use **AWS Secrets Manager** to centrally manage **database credentials** and **API keys** securely throughout their lifecycle.

---






---

# **Protecting Networks and Applications on AWS**

## **Network and Application Attacks**

### **DoS (Denial of Service) Attacks**

* Attacker floods a **web application** with **excessive network traffic**.
* **Legitimate customer requests** are denied if the web application becomes overloaded and cannot respond.

### **DDoS (Distributed Denial of Service) Attacks**

* Uses **multiple compromised computers or devices (zombie bots)** to send traffic to a web application.
* Different from DoS attacks, which originate from a **single source**.

---

## **AWS Network and Application Protection**

### **Infrastructure-Level Protection**

* AWS automatically protects against **low-level, brute-force attacks**, including **DDoS**, via its **built-in infrastructure**.
* AWS infrastructure includes:

  * **Multiple Regions**
  * **Availability Zones**
  * **Edge locations**
* Designed to **make it difficult for attackers to overwhelm the system**.

#### Key Components:

1. **Security Groups**

   * Allow only **proper request traffic**.
   * Operate at the **AWS network level**, leveraging the **entire Region's capacity** to resist attacks.

2. **Elastic Load Balancing (ELB)**

   * Handles traffic before passing it to **frontend servers**.
   * Prevents any single server from being **overwhelmed**.
   * Operates at the **Region level**.

3. **AWS Regions**

   * Enormous **capacity** makes them **extremely difficult to overwhelm**.
   * Attack would be **massively expensive** to achieve.

---

### **Service-Level Protection**

#### **AWS Shield**

* **AWS Shield Standard**: Automatic protection against **common DDoS attacks** at **no cost**.

  * Uses **analysis techniques** to detect and mitigate malicious traffic in **real time**.
* **AWS Shield Advanced**: Paid service with:

  * Detailed **attack diagnostics**
  * Mitigation of **sophisticated DDoS attacks**
  * Integration with **Amazon CloudFront, Amazon Route 53, and ELB**
* Can integrate with **AWS WAF** for **custom rules** to mitigate complex attacks.

#### **AWS WAF (Web Application Firewall)**

* Monitors **network requests** to web applications.
* Checks incoming requests against a **web access control list (web ACL)**.
* **Blocks** requests from **denied IPs**; allows **legitimate requests**.

---

## **Key Takeaways**

* **DoS vs DDoS**: DDoS uses **multiple compromised computers**; DoS uses a **single source**.
* **Infrastructure Protection**: Use **security groups** and **ELB** to absorb and manage large-scale attacks.
* **Service Protection**: Use **AWS Shield** and **AWS WAF** for detection, mitigation, and request filtering.

---

✅ **Example Exam Scenario**

* An online boutique targeted by **DDoS attacks**:
  **Recommended AWS components**:

  * **Security Groups** → allow only authenticated traffic
  * **Elastic Load Balancing (ELB)** → distribute traffic to prevent server overload

---



---

# **AWS Data Encryption — Exam Summary**

## **Encryption Basics**

* **Encryption** = lock and key mechanism:

  * **Encryption key** → turns data into randomized characters
  * **Decryption key** → accesses the original data when needed

* Example: Protecting a **customer’s profile**: encryption secures their data, decryption unlocks it for application use.

---

## **Types of Data Encryption**

1. **Data encryption at rest**

   * Data is **idle**, stored in **databases or storage systems**.

2. **Data encryption in transit**

   * Data is **moving between locations** (e.g., database → application).
   * Uses **SSL/TLS certificates** to establish **encrypted network connections**.

---

## **AWS Data Protection**

### **Built-in Data Protection**

* **Amazon S3** → new buckets have **encryption configured by default**; uploaded objects are **encrypted at rest**.
* **Amazon EBS** → volumes and snapshots (**boot and data volumes**) can be **encrypted at rest**.
* **Amazon DynamoDB** → **server-side encryption at rest** enabled for all table data using **AWS KMS keys**.

### **AWS Data Protection Services**

1. **AWS Key Management Service (AWS KMS)**

   * Create and manage **cryptographic keys**.
   * Control which **IAM users and roles** can use/manage keys.
   * Keys never leave KMS; can be **temporarily disabled**.

2. **Amazon Macie**

   * Monitors **sensitive data at rest** in **Amazon S3**.
   * Uses **ML and automation** to discover sensitive data.
   * Helps assess **security posture** and meet **compliance requirements**.

3. **AWS Certificate Manager (ACM)**

   * Centralizes **SSL/TLS certificate management**.
   * Provides **encryption in transit** for AWS services and connected on-premises resources.

---

## **Key Takeaways**

* **Encryption and decryption** → lock and unlock data using a **special key**; ensures **only authorized users** can access it.
* **Data at rest** → use S3, EBS, DynamoDB with encryption.
* **Data in transit** → use **ACM-managed SSL/TLS certificates**.
* **AWS KMS** → manages cryptographic keys for encryption/decryption.
* **Amazon Macie** → monitors sensitive data and ensures compliance.

---

✅ **Example Exam Scenarios**

1. Locking/unlocking data → **Encryption and decryption**.
2. Securing data moving from database → web application → **AWS Certificate Manager (ACM)**.

---






Here’s a **clean, exam-ready Markdown summary** of **AWS Detection and Response Services**, keeping all keywords intact for easy review:

---

# **AWS Detection and Response Services — Exam Summary**

## **Overview**

* Securing AWS resources involves **preventing, protecting, detecting, and responding** to security incidents.
* AWS offers multiple services for **detection and response** to security threats.

---

## **Amazon Inspector**

* Purpose: Improve **security and compliance** of applications.
* Runs **automated security assessments** for:

  * **Amazon EC2 instances**
  * **Containers**
  * **Lambda functions**
* Checks for:

  * **Security vulnerabilities**
  * **Deviations from security best practices** (e.g., open access, vulnerable software versions)
* Outputs:

  * **Security findings** prioritized by **severity level**
  * **Detailed descriptions** and **recommendations for remediation**
  * Findings available via **console or API**

---

## **Amazon GuardDuty**

* Provides **intelligent threat detection** across AWS infrastructure and resources.
* Continuously monitors:

  * **Account metadata streams**
  * **Network activity**
* Uses:

  * **Known malicious IP addresses**
  * **Anomaly detection**
  * **Machine learning**
* Outputs:

  * **Detailed findings** with **recommended remediation steps**
  * Optional: Automate remediation with **AWS Lambda functions**

---

## **Amazon Detective**

* Purpose: **Investigate root cause** after a threat is detected.
* Provides **interactive visualizations** of security data in a **unified AWS Management Console view**.
* Visualizations include:

  * **Resource and user interactions**
  * **Configurable timeline**
  * **Recommended remediation steps**
* Best for: **Analyzing security threats over time**

---

## **AWS Security Hub**

* Aggregates **multiple security services** into **one comprehensive view**.
* Automatically collects **security findings** from AWS and partner services.
* Organizes findings into **actionable insights**.
* Supports **automated remediation** to accelerate **time to resolution (TTR)**.
* Best for: **Compliance reporting** and **centralized security monitoring**

---

## **Key Takeaways**

| AWS Service          | Purpose / Best Use Case                                                                                                       |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **Amazon Inspector** | Automated security assessments of EC2, containers, Lambda; identifies vulnerabilities and deviations from best practices.     |
| **Amazon GuardDuty** | Intelligent threat detection via metadata and network activity monitoring; uses ML and anomaly detection.                     |
| **Amazon Detective** | Investigate threats with interactive visualizations and timeline analysis; root cause investigation.                          |
| **AWS Security Hub** | Aggregate findings from multiple services; centralize security and compliance monitoring; automated insights and remediation. |

---

## **Example Exam Scenarios**

1. Investigate root cause with interactive visualizations → **Amazon Detective**
2. Aggregate security findings from multiple services for compliance → **AWS Security Hub**

---


---

# **AWS Additional Security Resources — Exam Summary**

## **AWS Security Documentation**

* AWS provides extensive documentation to guide securing resources; varies **by service**.
* Key sources:

  * **Security, Identity, and Compliance on AWS** — General AWS security, identity, and compliance information
  * **AWS Knowledge Center** — Troubleshooting, Q&A, and learning about AWS security services
  * **AWS Security Documentation** — Search documentation by **product category**
  * **AWS Security Blog** — Expert insights, best practices, and security feature updates

---

## **AWS Marketplace Security Resources**

* AWS Marketplace offers **third-party security software and services** that run on AWS.
* Security service types available:

  1. **Threat detection and prevention tools** — Identify and block malicious activities
  2. **Identity and access management tools** — Control user permissions and authentication
  3. **Data protection tools** — Encrypt and safeguard sensitive information
  4. **Compliance and governance tools** — Meet regulatory security requirements
* Reference: **Cloud Security Software** on AWS Marketplace

---



| **Resource link** | **Description** |
|------------------|----------------|
| **AWS Identity and Access Management (IAM)** | Securely manage **identities** and **access** to AWS **services** and **resources**. |
| **AWS IAM Identity Center** | Connect your existing **workforce identity source** and centrally manage **access** to AWS with **single sign-on**. |
| **AWS Secrets Manager** | Centrally store and manage **credentials**, **API keys**, and other **secrets**. |
| **AWS Systems Manager** | Manage **nodes**, or **connection points**, at scale on AWS and in **multi-cloud** and **hybrid environments**. |
| **AWS Shield** | Protect your **network** and **applications** from the most common, frequently occurring types of **DDoS attacks**. |
| **AWS WAF** | Protect your **network** and **applications** from blocked **IP addresses** defined by a **web ACL**. |
| **AWS Key Management Service (AWS KMS)** | Create and manage **cryptographic keys** to **encrypt** and **decrypt** your **data**. |
| **Amazon Macie** | Certify that **sensitive data** is discovered and protected in **Amazon S3**. |
| **AWS Certificate Manager (ACM)** | Create and manage **SSL/TLS certificates** that provide **data encryption in transit**. |
| **Amazon Inspector** | Check **applications** for **security vulnerabilities** and deviations from **security best practices**. |
| **Amazon GuardDuty** | Continuously monitor the AWS **environment** with **intelligent threat detection**. |
| **Amazon Detective** | Analyze **threats** with **interactive visualizations** contained in a unified view. |
| **AWS Security Hub** | Aggregate **security findings** and organize them into actionable **insights**. |
