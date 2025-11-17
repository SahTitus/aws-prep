* **IAM User:** A specific identity in AWS with credentials to access services.
* **IAM Group:** A collection of users that share the same permissions.
* **IAM Role:** A temporary identity with defined permissions that AWS services or users can assume.
* **IAM Policy:** A document that defines permissions (what actions are allowed or denied).

* **IAM Identity Center** is specifically designed to **help organizations implement single sign-on** for **AWS resources** using their **existing identity providers.**

* In an S3 bucket policy, the **IAM Principal** element specifies **who (which user, role, or account)** is allowed or denied access to the bucket.
* It can **include IAM users, roles, or AWS accounts.**

* **IAM account password policies** allow administrators to enforce **password complexity requirements** for **AWS Management Console users**, including:  
  - Minimum length  
  - Required character types (uppercase, lowercase, numbers, symbols)  
  - Password expiration and reuse rules  

*

# Which tasks require use of the AWS account root user? (Select TWO.)
* Restoring IAM administrator permissions
* Closing an AWS account

# What is an IAM best practice for AWS account root user access keys?
**Delete all root user access keys, if possible.**

# What are characteristics of AWS IAM users and groups? (Select TWO.)
* A user can be a member of multiple groups.
* Groups can contain **users only and cannot be nested.**

# 
#
✅ **IAM role**

**Explanation:**

* An **IAM role** allows **cross-account access** by granting temporary permissions to users or services in another AWS account.


**Keywords:** cross-account access, temporary credentials, trust policy.

* **A. IAM group:**
  → Groups are used **within the same AWS account** to organize users and assign common permissions. They **cannot grant cross-account access**.

* **C. IAM tag:**
  → Tags are just **labels (metadata)** to categorize and organize IAM resources — they **don’t grant or manage permissions**.

* **D. IAM Access Analyzer:**
  → Used to **analyze and identify resources shared externally**, not to **grant** access. It’s for **monitoring and auditing**, not permission control.

✅ **Correct:** **B. IAM role** — because it’s the **only** option that can securely grant **cross-account permissions**.




# **IAM credential report**:
helps to audit its password and access key rotation details for compliance purposes.

# Explanation:
**IAM credential report** provides a **list of all IAM users and the status of their credentials**, including:
* Password age and last rotation
* Access key age and last rotation
* MFA status

This report is ideal for auditing and compliance checks related to credentials.




# **C. AWS Security Token Service (AWS STS)**

* **AWS STS** provides **temporary, limited-privilege credentials** that applications can use to **access AWS services securely**.
* These credentials **expire automatically**, reducing security risks compared to long-term IAM user credentials.

