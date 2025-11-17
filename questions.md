# What does the AWS Health Dashboard provide?
* A. Detailed troubleshooting guidance to address AWS events impacting your resources.

* E. Personalized view of AWS service health.

**


An organization has a large number of technical employees who operate their AWS Cloud infrastructure. What does AWS provide to help organize them into teams and then assign the appropriate permissions for each team?
A. IAM roles.
B. IAM users.
C. IAM user groups.
D. AWS Organizations.

✅ **Correct Answer:**
**C. IAM user groups**

### **Explanation:**

* **IAM user groups** allow you to **organize multiple IAM users into teams** and **assign permissions** collectively.
* This simplifies management because **permissions are applied to the group**, and all users in the group inherit those permissions.

**Other options:**

* **A. IAM roles:** Provide temporary permissions, not for grouping users.
* **B. IAM users:** Represent individual accounts, not teams.
* **D. AWS Organizations:** Manages multiple AWS accounts, not individual user teams within an account.





Which of the following services have Distributed Denial of Service (DDoS) mitigation features? (Choose two.)

* A. AWS WAF
* B. Amazon DynamoDB
* C. Amazon EC2
* D. Amazon CloudFront
* E. Amazon Inspector


# Answer
* **AWS WAF (Web Application Firewall):**

Protects web applications from common web exploits and can be used with AWS Shield for DDoS protection. ✅

* **Amazon CloudFront (CDN):**

Has built-in DDoS mitigation via AWS Shield Standard automatically.


* # Which Amazon EC2 instance pricing model can provide discounts of up to 90%?

* A. Reserved Instances
* B. On-Demand
* C. Dedicated Hosts
* D. Spot Instances

The correct answer is:

D. Spot Instances ✅

Explanation:

Spot Instances let you use spare EC2 capacity at very steep discounts, sometimes up to 90% off the On-Demand price.

Reserved Instances → Offer discounts (up to ~75%) if you commit to 1–3 years.

On-Demand → Pay full price per hour/second.

Dedicated Hosts → Physical servers for compliance, no huge discount.

Spot Instances are ideal for flexible, fault-tolerant workloads that can handle interruptions.


# Which AWS services can deploy applications to on-premises servers?”
* **AWS Elastic Beanstalk** → Manages **deployments to AWS cloud only**, **not** on-premises ❌

* **AWS OpsWorks** → Can manage **configuration and deployments** on both **EC2** and **on-premises servers** ✅

* **AWS CodeDeploy** → Can **deploy code** to **EC2 instances and on-premises servers** ✅

* **AWS Batch** → Runs batch jobs on AWS only, not on-premises ❌

* **AWS X-Ray** → **Monitoring and tracing service**, not for deployments ❌

✅ Correct answers:
B. AWS OpsWorks
C. AWS CodeDeploy



# Which of the following steps should be taken by a customer when conducting penetration testing on AWS?

A. Conduct penetration testing using Amazon Inspector, and then notify AWS support.
B. Request and wait for approval from the customer's internal security team, and then conduct testing.
C. Notify AWS support, and then conduct testing immediately.
D. Request and wait for approval from AWS support, and then conduct testing.
Answer
Correct Answer: D

Explanation:

AWS customers are welcome to carry out security assessments or penetration tests against their AWS infrastructure without prior approval for 8 services.