# **AWS Systems Manager (SSM)**
 allows you to **automate patch management** for **EC2 instances**, including **operating system and database software patches**.  
- You can define **patch baselines and schedules**, ensuring all instances are consistently updated without manual intervention.  




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
