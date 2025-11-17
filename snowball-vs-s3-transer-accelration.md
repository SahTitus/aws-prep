# AWS Large-Scale Data Transfer Options

**S3 Transfer Acceleration** is more suitable for **recurring data transfer jobs**, and **not** for a **one-time migration.**

**S3 Transfer Acceleration** can speed up transfers to and from Amazon S3 for long-distance transfers or large files. **S3 Transfer Acceleration** would **not** **remediate the 100 Mbps** connection speed

## Scenario
A company needs to perform a **one-time migration of 40 TB** of data from on-premises storage to Amazon S3.  
- The transfer must happen **as quickly as possible**  
- **Cost should be minimized**  
- Current internet speed: **100 Mbps**

## Options Considered

### 1. AWS Snowball Edge ✅
- **Best choice for this scenario**
- **Physical device** shipped by AWS to your data center
- **Securely transfers large amounts of data** (TBs to PBs) into AWS
- Faster than internet-based transfers for large datasets, especially when bandwidth is limited
- Reduces transfer times and costs for one-time migrations

### 2. S3 Transfer Acceleration ❌
- Speeds up transfers to S3 over the internet using **optimized AWS edge locations**
- Best for **long-distance transfers or recurring large files**
- **Does not solve the 100 Mbps internet bottleneck** for a one-time massive migration
- Higher cost if used for large one-time data transfers

## Key Takeaway
- **Use Snowball Edge for large one-time migrations** when internet bandwidth is limited  
- **Use S3 Transfer Acceleration** for repeated transfers over long distances where network latency is a concern
