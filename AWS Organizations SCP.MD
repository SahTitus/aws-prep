**B. AWS Organizations SCP**

**Service Control Policies (SCPs)** in **AWS Organizations** allow centralized restriction of **billing and cost management actions** (e.g., deny `aws-portal:ModifyBilling`) across all accounts in an OU or organization—**most effective** for governance at scale.

- **A. IAM policies**: Account-level only (not centralized).  
- **C. Billing Console permissions**: Limited to root/IAM users in the payer account.  
- **D. Control Tower**: Uses SCPs under the hood but is overkill for just billing control.