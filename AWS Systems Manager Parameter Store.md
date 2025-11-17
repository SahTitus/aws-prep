# **A. AWS Systems Manager Parameter Store**

It provides **centralized, secure, and hierarchical storage** for configuration data and passwords at **no additional cost** (free tier for standard parameters; low cost for advanced), making it the **most cost-effective** choice compared to Secrets Manager (per-secret pricing), AWS Config (compliance tracking), or S3 (object storage without native secret management).

✅ **Correct Answer:**
**A. AWS Systems Manager Parameter Store**

### **Explanation:**

* **AWS Systems Manager Parameter Store** provides **centralized storage for configuration data and secrets** (like passwords, API keys).
* It is **fully managed, secure, and cost-effective**, especially for **standard parameters**.
* **AWS Secrets Manager** is more feature-rich (automatic rotation) but **more expensive**.
* **AWS Config** is for **configuration compliance monitoring**, not storing secrets.
* **Amazon S3** is object storage, not optimized for managing secrets or configuration data.


# **AWS Secrets Manager**  

Fully managed service for **storing, rotating, and retrieving sensitive data** (e.g., database credentials, API keys) with **automatic rotation**, fine-grained IAM access, and audit via CloudTrail—**more secure and automated** than Parameter Store, but **not the most cost-effective** due to per-secret and per-API-call pricing.