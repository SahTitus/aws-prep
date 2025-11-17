# AWS Storage Services – Exam-Ready Notes

---

## **1. Block Storage**

Block storage provides **persistent**, **low-latency**, block-level storage volumes that attach to EC2 instances like physical hard drives.  
Volumes can be **encrypted**, **snapshotted**, and **modified while in use** without disrupting the instance.

### **1.1 Amazon EC2 Instance Store** -  no data persistence
- **EC2 instance store** is **best** for **temporary memory-based storage** needs like **buffers, caches, and scratch data**. It is not recommended for applications that require data retention.
- **Unmanaged**
- **Non-persistent**
- **High-performance** block storage  
- Directly attached to EC2  
- Used for **temporary data**

### **1.2 Amazon Elastic Block Store (EBS)**
- **Managed service**
- **Persistent** block storage for EC2 instances  
- Multiple **volume types** for different workloads

---

## **2. Object Storage**

Object storage manages data as **objects** in a **flat address space**.  
It provides:  
- **Unlimited scalability**  
- Support for **massive unstructured datasets**  
- **Enhanced metadata** for search, analytics, and management

### **2.1 Amazon Simple Storage Service (S3)**
- **Fully managed**
- **Scalable object storage**
- Store and retrieve **any amount** of data from anywhere

---

## **3. File Storage**

File storage provides **shared file systems**, accessible over a network.  
Multiple users/applications can access the same data at once.  
Automatically **scales** without managing physical infrastructure.

### **3.1 Amazon Elastic File System (EFS)**
- **Fully managed**
- **Scalable NFS** file system  
- Works with AWS services and **on-premises** environments
- Amazon EFS **core value proposition** as a service that **automatically grows and shrinks with the storage needs without manual provisioning**.


### **3.2 Amazon FSx**
- **Fully managed**
- Provides file systems such as:  
  - **Windows**  
  - **Lustre**  
  - **NetApp ONTAP**

---

## **4. Additional Storage Services**

### **4.1 AWS Storage Gateway**
- **Fully managed**
- **Hybrid-cloud** storage  
- Provides on-premises access to **unlimited cloud storage**

### **4.2 AWS Elastic Disaster Recovery**
- **Fully managed**
- Simplifies recovery of **physical, virtual, and cloud servers** into AWS

---

# **5. AWS Shared Responsibility Model (Storage Focus)**

AWS groups storage services into three responsibility categories:  
**Fully managed**, **Managed**, and **Unmanaged**.

---

## **5.1 Fully Managed Services**
AWS handles:  
- Hardware & infrastructure  
- **Durability**, **availability**, **replication**  
- **Encryption at rest**

Customer handles:  
- **Data management**  
- **Access controls**  
- Proper **configuration**

➡️ **Least customer responsibility**

---

## **5.2 Managed Services**
AWS handles:  
- Storage infrastructure  
- **Hardware redundancy**  
- **Volume replication**

Customer handles:  
- **Backups**  
- **Encryption settings**  
- **Performance tuning**  
- **Capacity planning**

➡️ **More customer responsibility than fully managed**

---

## **5.3 Unmanaged Services**
Customer handles:  
- **All data management**  
- **Backup/recovery**  
- **Encryption**  
- **Performance**  
- **Durability**

AWS handles only:  
- **Physical hardware**  
- **Network infrastructure**

➡️ **Highest customer responsibility**

---






# AWS Block Storage Deep Dive – Exam-Ready Notes

---

## **1. Amazon EC2 Instance Store**

Amazon EC2 instance store is **not a standalone storage service**.  
It refers to **block-level storage physically attached** to the **host computer** of an EC2 instance.

It may come **automatically attached** depending on the instance type.

👉 **Key Takeaway: _No data persistence_**  
When an EC2 instance is **stopped or terminated**, **all data** on the instance store is **deleted**.

Best for **temporary**, **memory-based**, or **fast-processing** workloads such as:
- Buffers  
- Caches  
- Scratch data  

Not recommended for workloads requiring **data retention**.

---

### **1.1 Benefits of EC2 Instance Store**

#### **✓ Automatically available storage**
- Comes **included** with many EC2 types  
- **No extra cost**  
- Physically attached → **very high I/O performance**  
- Ideal for temporary data that disappears when the instance stops  

#### **✓ Cost effective**
- Included in EC2 pricing  
- Great for workloads that don't need persistent storage  
- Reduces cost for temporary data workloads  

#### **✓ High performance**
- **Low-latency**, **direct-attached** storage  
- Extremely high I/O throughput  
- Ideal for fast processing of temporary data  

---

## **2. Amazon Elastic Block Store (EBS)**

Amazon EBS provides **persistent block-level storage** for EC2 instances.  
Acts like an **external hard drive** that stays intact even if the instance stops.

👉 **Key Takeaway: _Data persistence_**  
When an EC2 instance is **stopped or terminated**, all data on the **EBS volume remains available**.

EBS volumes support:
- **Backups (snapshots)**  
- **Resizing**  
- **Attach/detach** to EC2 instances  
- **Different volume types** for different workloads  

Because EBS is persistent, it's recommended to take **incremental snapshots** for backup.

---

### **2.1 Common Use Cases**
- Hosting **databases**  
- Application **backup storage**  
- Rapid deployment of dev environments using **snapshots**  

---

### **2.2 Benefits of Amazon EBS**
## Amazon EBS provides **high availability and durability** by **automatically replicating volumes** within the **same Availability Zone**.

#### **✓ Data migration**
- Move volumes across **Availability Zones** using **snapshots**  
- The **snapshots create cross-region copies** 

#### **✓ Instance type changes**
- Since EBS is **independent** of the EC2 instance, it can be reattached to different instance types  
- Enables easy upgrades/downgrades  

#### **✓ Disaster recovery**
- Snapshots can be restored in **any region**  
- Regular automated snapshots provide strong protection  

#### **✓ Cost optimization**
- Resize volumes without downtime  
- Change volume types to match usage patterns  

#### **✓ Performance tuning**
- Multiple EBS volume types (e.g., general purpose, provisioned IOPS)  
- Adjust performance characteristics on demand  

---



# Amazon EBS Snapshots – Exam-Ready Notes

---

## **1. What Are EBS Snapshots?**

**EBS snapshots** are **point-in-time backups** of an Amazon EBS volume.  
They support:
- **Disaster recovery**
- **Data migration**
- **Volume resizing**
- **Consistent backups of production workloads**

Snapshots are **incremental** — after the first snapshot, only **changed blocks** are stored.

New volumes created from a snapshot are **exact copies** of the original volume at the time the snapshot was taken.

Snapshots are stored **redundantly across multiple Availability Zones** using **Amazon S3**.

---

## **2. Working With EBS Snapshots (Shared Responsibility)**

Under the AWS shared responsibility model, the **customer** is responsible for:
- Scheduling and managing regular snapshots  
- Monitoring snapshot **costs**  
- Deleting old/unnecessary snapshots  
- Ensuring **encryption** of sensitive data  
- Verifying snapshot integrity  
- Testing restore procedures  

---

## **3. How EBS Snapshots Work Over Time**

### **3.1 Initial Snapshot**
- The first snapshot is a **full copy** of all data on the volume.  
- Serves as the **baseline** for future incremental snapshots.

### **3.2 Subsequent Incremental Snapshots**
- Only **changed blocks** since the previous snapshot are stored.  
- Much **smaller** and **faster** to create.  
- Each snapshot contains references to earlier snapshots, allowing **point-in-time recovery**.

### **3.3 Snapshot Consolidation & Management**
- Each snapshot appears as a **full copy**, even though stored incrementally.  
- AWS manages relationships between snapshots automatically.  
- When a snapshot is deleted, only **unique data** is removed — shared data required by other snapshots is retained.

---

## **4. Benefits of EBS Snapshots**

### **✓ Data protection and recovery**
- Quick recovery from **corruption**, **accidental deletion**, or **system failures**.

### **✓ Operational flexibility**
- Supports cross-Region migration  
- Used for volume resizing & cloning  
- Enables cross-account data sharing  

### **✓ Cost effective**
- Incremental backups save only changed blocks → reduced storage cost and faster backups.

---

# Amazon Data Lifecycle Manager (DLM) – Snapshot Automation

for **automating the creation, retention, and deletion** of **EBS snapshots** and **EBS backed Amazon Machine Images (AMIs)** according to a schedule

Amazon Data Lifecycle Manager helps:
- Reduce manual backup efforts  
- Automate snapshot creation and deletion  
- Enforce retention rules  
- Maintain compliance  

You can create policies using:
- EC2 Console  
- API  
- AWS CLI  
- SDKs  
- CloudFormation  

---

## **5. DLM Snapshot Policy Workflow**

### **Step 1: Select Target Resource Type**
Choose:
- **EBS volume**, or
- **EC2 instance** (to automatically include its volumes)

### **Step 2: Exclude Volumes**
Optionally exclude:
- Root volumes  
- Data volumes  

### **Step 3: Set Custom Schedules**
Automate:
- Snapshot creation  
- Retention periods  
- Snapshot deletion  

### **Step 4: Apply Additional Actions**
Configure snapshot features such as:
- **Tags**  
- **Snapshot archiving**  
- **Fast Snapshot Restore (FSR)**  
- **Cross-Region copy**  
- **Cross-account sharing**

---



Below is your **clean, complete, exam-ready, well-structured Markdown (.md) file** covering all the key information you wrote about **Amazon S3**.
You can **copy & paste directly into a .md file**.

---

# 📦 **Amazon S3 — Exam-Ready Notes**

## **1. Overview**

**Amazon Simple Storage Service (S3)** is a **fully managed, highly available object storage service** used to store and retrieve any amount of data.

* **Storage type:** Object storage
* **Durability:** **99.999999999% (11 nines)**
* **Scalability:** Virtually unlimited
* **Data stored as:** Objects inside Buckets
* **Common use cases:** Backups, static website hosting, big data lakes, archives, media distribution
* **Key features:** Versioning, lifecycle rules, encryption, multiple storage classes

---

# **2. Core Concepts**

## **2.1 S3 Objects**

Objects are the fundamental units stored in S3.

Each object contains:

* **Object data** (file content)
* **Metadata**
* **Key** (unique identifier / file name)
* **Version ID** (if versioning enabled)
* **ACLs & permissions**

**Size:** a few bytes → several TB.

---

## **2.2 S3 Buckets**

Buckets are containers for objects.

* **Globally unique name** (across all AWS accounts)
* Created in a specific **AWS Region**
* Act as the main boundary for:

  * Permissions
  * Versioning
  * Logging
  * Lifecycle rules
  * Replication settings

**You can have virtually unlimited objects per bucket.**

---

# **3. Key Features & Capabilities**

## **3.1 Virtually Unlimited Storage**

No capacity planning required. You pay only for what you use.

---

## **3.2 Lifecycle Management**

Lifecycle policies automatically:

* Transition objects to cheaper storage classes
* Delete objects on schedule
* Expire previous versions

**Used for cost optimization over time.**

---

## **3.3 Multiple Use Cases**

S3 supports a wide spectrum of workloads:

* Static website hosting
* Application data storage
* Backup & restore
* Data archiving
* Disaster recovery
* Media files & content delivery
* Big data analytics (data lakes, ML pipelines)
* Compliance & long-term retention

---

# **4. Security & Access Control**

All S3 data is **private by default**. You explicitly grant access.

## **4.1 Bucket Policies (Resource-Based Policies)**

* Attached **only to buckets**
* Define **who can access the bucket and what actions they can perform**
* Can allow or deny:

  * Access to the bucket
  * Access to all objects in the bucket

**Useful for public access, cross-account access, and service access.**

---

## **4.2 Identity-Based Policies**

These attach to:

* IAM users
* IAM groups
* IAM roles

Used to define:

* Which buckets/objects the identity can access
* What operations they can perform (GetObject, PutObject, etc.)

---

# **5. Encryption**

Amazon S3 supports encryption **at rest** and **in transit**.

## **5.1 Encryption at Rest**

Protects stored data using:

* **SSE-S3** (S3-managed keys)
* **SSE-KMS** (AWS Key Management Service)
* **SSE-C** (customer-provided keys)

Ensures unauthorized users cannot read the data.

---

## **5.2 Encryption in Transit**

Data traveling between:

* Your system → S3
* S3 → your applications

is protected using **HTTPS (TLS)**.

---

# **6. Exam Highlights & Keywords to Remember**

* S3 = **Object storage** (not block, not file)
* **11 nines durability**
* Stores data as **objects inside buckets**
* **Global bucket names**
* **Private by default**
* Use **bucket policies** for resource-level control
* Use **IAM policies** for identity-level control
* **Lifecycle policies** = automate cost optimization
* Supports **static website hosting**
* Integrates with almost every AWS service
* Encryption:

  * **SSE-S3 / SSE-KMS / SSE-C**
  * **TLS for in-transit**

---






Understood.
Here is the **exact same format as the previous one** — clean, exam-ready, structured **Markdown**, **no deviation**, **no extra styling**, **no commentary**, **no summaries**.

---

# **Amazon S3 Storage Classes & Use Cases — Exam-Ready Notes**

## **1. Overview**

Amazon S3 provides multiple storage classes designed for different performance, access patterns, resiliency, and cost requirements. These classes support unpredictable access, archival needs, data residency, and cost optimization.

---

# **2. Amazon S3 Storage Classes**

## **2.1 S3 Standard**

General-purpose storage for:

* Cloud applications
* Dynamic websites
* Content distribution
* Mobile/gaming apps
* Big data analytics

**Default class** if none is specified.

---

## **2.2 S3 Intelligent-Tiering**

Best for **unknown or changing access patterns**.

Automatically moves objects across:

* Frequent access tier
* Infrequent access tier
* Archive instant access tier

Amazon S3 monitors access and optimizes cost automatically.

---

## **2.3 S3 Standard-Infrequent Access (S3 Standard-IA)**

* Data accessed infrequently
* Requires rapid access when needed
* Stored across **3 Availability Zones**
* Lower storage price than Standard, but retrieval fee

Use cases:

* Long-term backups
* Disaster recovery data

---

## **2.4 S3 One Zone-Infrequent Access (S3 One Zone-IA)**

* Data stored in **one Availability Zone only**
* Cheaper than Standard-IA

Use cases:

* Secondary backups
* Easily re-creatable data
* **Data with lower availability requirements**

---

## **2.5 S3 Express One Zone**

* Stored in a **single Availability Zone**
* Built for **single-digit millisecond** latency
* Up to **10× faster** access than S3 Standard
* Up to **80% lower request costs**

Use cases:

* Latency-sensitive workloads
* High-performance applications

---

## **2.6 S3 Glacier Instant Retrieval**

* For archives rarely accessed
* Retrieval in **milliseconds**
* Up to **68% cheaper** than Standard-IA
* Same performance as S3 Standard-IA

Use cases:

* Rarely accessed but must be retrieved instantly
* Insurance documents
* Medical images

---

## **2.7 S3 Glacier Flexible Retrieval**

* Accessed **1–2 times per year**
* Expedited retrieval: **1–5 minutes**
* Bulk retrieval: **5–12 hours**, no extra cost

Use cases:

* Backup
* Disaster recovery
* Offsite archives
* Data occasionally needed in minutes

---

## **2.8 S3 Glacier Deep Archive**

* **Lowest-cost storage class**
* Retrieval time: **12 hours**
* Designed for **7–10+ years retention**

Use cases:

* Regulatory compliance
* Long-term archives
* Financial services, healthcare, public sector

---

## **2.9 S3 Outposts**

* S3 storage delivered **on-premises** via AWS Outposts
* Supports local data residency
* Uses S3 APIs & features

Use cases:

* Local processing requirements
* Applications needing low-latency on-premises access

---

# **3. S3 Lifecycle Management**

Lifecycle configurations automate moving or deleting objects.

Two action types:

### **3.1 Transition Actions**

Move objects to another storage class based on time.

Example:

* After 30 days → Move to S3 Standard-IA
* After 60 more days → Move to Glacier Instant Retrieval

### **3.2 Expiration Actions**

Delete objects permanently after a set time.

---

# **4. Lifecycle Example (Timeline)**

### **After 30 days**

Move from **S3 Standard → S3 Standard-IA** if not accessed.

### **After 60 days**

Move from **Standard-IA → Glacier Instant Retrieval** if still not accessed.

### **After 365 days**

Object is **deleted** if not accessed.

---

# **5. Lifecycle Use Cases**

### **Periodic Logs**

* Needed for 1 week or 1 month
* Delete afterwards

### **Data with changing access patterns**

* Frequently accessed early
* Later infrequent
* Eventually archived for compliance
* Deleted after retention period

---





Here’s your **Amazon FSx notes** in the same **exam-ready Markdown format** as before:

---

# **Amazon FSx — Exam-Ready Notes**

## **1. Overview**

Amazon FSx is a **fully managed, high-performance file storage service** that supports multiple file system protocols. It simplifies launching, running, and scaling feature-rich file systems in the cloud.

**Comparison to EFS:**

* **Amazon EFS:** Focuses on **NFS compatibility**
* **Amazon FSx:** Supports **Windows File Server, Lustre, OpenZFS, NetApp ONTAP**

**Built on:** Latest AWS compute, networking, and disk technologies

**Managed aspects:** Hardware provisioning, patching, and backups

---

## **2. Benefits of Amazon FSx**

### **2.1 File System Integration**

* Supports **industry-standard protocols**
* Integrates with existing applications, workflows, and dev tools

### **2.2 Managed Infrastructure**

* Reduces complexity of managing storage
* Provides full features of traditional file systems

### **2.3 Scalable Storage**

* Dynamically adjusts resources
* Eliminates manual capacity planning

### **2.4 Cost Effective**

* Pay only for **used storage**
* Automated **tiering** moves infrequently accessed data to lower-cost tiers

---

## **3. Amazon FSx File Systems**

### **3.1 FSx for Windows File Server**

* Fully managed **Windows-based file system**
* Supports **SMB protocol** and integrates with **Active Directory**

**Use Cases:**

* **Migrate Windows file servers to AWS**
* Accelerate hybrid workloads
* Reduce **SQL Server deployment** costs
* Streamline virtual desktops and streaming


- Provide a fully managed service.
- Seamlessly **integrate with Windows applications**.
- Support **SMB protocol.**
- Offer **Active Directory integration** for **user authentication**.
- Support **data deduplication** to optimize storage costs.
- Provide consistent **sub-millisecond latencies.**
- Provide **high availability.** 

---

### **3.2 FSx for NetApp ONTAP**

* Fully managed shared storage with **ONTAP capabilities**

**Use Cases:**

* Seamless migration to AWS
* Build modern applications
* Modernize data management
* Streamline business continuity

---

### **3.3 FSx for OpenZFS**

* Fully managed **OpenZFS file system**
* Accessible via **NFS v3, v4, v4.1, v4.2**

**Use Cases:**

* Seamless migration to AWS
* Accelerate data analytics insights
* Boost content management
* Increase dev/test velocity

---

### **3.4 FSx for Lustre**

* Fully managed **Lustre file system**
* High **scalability and performance**

**Use Cases:**

* Accelerate **machine learning (ML)**
* Enable **high-performance computing (HPC)**
* Unlock **big data analytics**
* Increase **media workload agility**

---

## **4. Key Takeaway**

* **FSx for Windows File Server:** Best for **Windows workloads**, **SMB protocol**, AD integration, and scenarios needing full Windows compatibility







Perfect! Here's your **AWS Storage Gateway content** rewritten in your **exam-ready Markdown format** with headings, mnemonics, and tables for readability:

---

# 🗄️ AWS Storage Gateway — Exam-Ready Notes

## **Overview**

* **AWS Storage Gateway**: Hybrid cloud storage service that **connects on-premises environments with AWS Cloud storage**.
* Enables **low-latency access** to frequently used data while **leveraging cloud scalability**.
* Streamlines **storage management** and **reduces costs**.

🧠 **Trick:** *Storage Gateway = Bridge between on-prem + cloud storage.*

---

## **Benefits**

### 🔹 **Seamless Integration**

* Preserves **existing workflows** and minimizes disruption.
* Provides smooth **connectivity** between on-premises apps and AWS Cloud.

### 🔹 **Improved Data Management**

* Centralized management of **hybrid storage**.
* Enhances **accessibility, security, and compliance**.

### 🔹 **Local Caching**

* Frequently accessed data is cached **locally**.
* Less-used data is managed in the **cloud** for efficiency.

### 🔹 **Cost Optimization**

* Reduces on-premises storage costs.
* Ideal for **backup, disaster recovery, and archiving**.

---

## **Gateway Types**

### 1️⃣ **Amazon S3 File Gateway**

* Bridges on-premises apps with **Amazon S3**.
* Provides access via **familiar file protocols**.
* **Behavior:**

  * Files written locally are **automatically uploaded to S3**.
  * Frequently used files are **cached locally** for low-latency access.

**Use Cases:**

* Extend local file servers to **cloud storage**
* Hybrid apps that need **S3 integration** without changing workflow

🧠 **Trick:** *S3 File Gateway = Files appear local, stored in S3.*

---

### 2️⃣ **Volume Gateway**
**iSCSI** => **Internet Small Computer System Interface**
* Presents **cloud storage as virtual iSCSI volumes** for on-prem apps.
* Two modes:

  * **Cached Volume Mode:** Primary data stored in cloud; frequently accessed data **cached locally**.  while maintaining the **complete dataset in Amazon S3**. This provides both  **local performance** and a **secure cloud backup.**
  * **Stored Volume Mode:** Complete dataset stored locally; asynchronously backed up to cloud via **EBS snapshots**. **Stored Volume** mode does **store the entire dataset locally for low latency access**, but **not in Amazon S3.**

**Use Cases:**

* On-premises apps needing **low-latency cloud access**
* Backup and disaster recovery for existing workloads

🧠 **Trick:** *Volume Gateway = Cloud volumes, local access.*

---

### 3️⃣ **Tape Gateway**

* Replaces **physical tape infrastructure** with **virtual tapes**.
* Fully compatible with **existing tape backup software**.
* Virtual tapes stored in **Amazon S3**, optionally transitioned to **low-cost storage classes**.

**Use Cases:**

* Replace **physical tapes** with cloud backups
* Long-term retention and archiving

🧠 **Trick:** *Tape Gateway = Virtual tape library in the cloud.*

---

## **Summary Table**

| Gateway Type        | Key Feature        | Storage Location      | Access Mode              | Best For                             | Trick                            |
| ------------------- | ------------------ | --------------------- | ------------------------ | ------------------------------------ | -------------------------------- |
| **S3 File Gateway** | File-level access  | Cloud (S3)            | Local caching            | Hybrid apps using files              | Files appear local, stored in S3 |
| **Volume Gateway**  | Block-level access | Cloud + Local         | Cached or Stored         | Backup, low-latency apps             | Cloud volumes, local access      |
| **Tape Gateway**    | Tape replacement   | Cloud (S3 + archival) | Standard backup software | Physical tape replacement, archiving | Virtual tape library             |

---


---

# 🛡️ AWS Elastic Disaster Recovery — Exam-Ready Notes

## **Overview**

* **Elastic Disaster Recovery (AWS DRS)**: Service that **replicates critical workloads to AWS** with **minimal downtime**.
* Supports **physical and virtual servers**, enabling **rapid recovery** during disruptions.
* **Continuously replicates **block-level server data** to AWS, reducing data loss and downtime.**

🧠 **Trick:** *Elastic DR = Instant server recovery in AWS.*

---

## **Benefits**

### 🔹 **Business Resilience**
* Continuous **block-level replication** of critical workloads.
* Protects mission-critical workloads from outages.
* Recover servers in **minutes** during disruptions.

### 🔹 **Streamlined Disaster Recovery**
* Fully managed via **simple AWS console**.
* Automates DR workflows → **reduces manual steps** and **human errors**.
* Launch **non-disruptive DR tests** anytime.
* Supports **non-disruptive DR testing**.
* Quickly launches **recovery instances** without affecting production.

### 🔹 **Cost Optimization**

* Eliminates the need for **secondary data centers**.
* Pay only for **resources used during recovery** — minimal upfront investment.

---

## **Use Cases**

### 🏥 **Healthcare Data Protection**

* Protects hospital systems and **patient records**.
* Ensures **regulatory compliance** with minimal downtime.
* Supports **regular DR testing** to validate procedures.

### 💳 **Financial Services Continuity**

* Protects **core banking apps** by replicating transaction systems.
* Enables **fast recovery** in case of primary site failure.
* Maintains **customer trust** and compliance.

### 🏭 **Manufacturing Operations Recovery**

* Safeguards **production planning systems**.
* Minimizes **supply chain disruptions** during disasters.
* **Failover testing** validates recovery strategies.

---

## **Key Features**

| Feature                                 | Description                                                  | Benefit                                    |
| --------------------------------------- | ------------------------------------------------------------ | ------------------------------------------ |
| **Continuous Block-Level Replication**  | Replicates data from source servers to AWS in near real-time | Near-instant recovery at target AWS Region |
| **Non-Disruptive Testing**              | Launch recovery instances without affecting production       | Validates DR plans without downtime        |
| **Supports Physical & Virtual Servers** | Works with on-premises or cloud-based workloads              | Flexible recovery options                  |
| **Cost-Efficient**                      | No need for secondary data centers; pay-as-you-go            | Reduces DR infrastructure costs            |

---

## **Exam Tip / Scenario**

**Scenario:** AnyCompany Telecommunications needs a disaster recovery solution for on-premises servers, with limited IT staff. They want **exact replicas** of production servers and **minimal recovery time**.

**Key Benefit:**

> **Continuous block-level replication with frequent backup intervals, providing near-instant recovery of servers at the target AWS Region.** ✅

**Other options explained:**

* **Automated dev/test environments** → Not the primary DR function.
* **Direct connection to Storage Gateway** → Unrelated to DRS replication.
* **Elimination of source-side agents** → Not a main benefit; DRS uses lightweight agents but replication is the key point.

---


---

# 🧩 AWS Disaster Recovery Strategies

AWS provides several approaches to disaster recovery (DR), depending on **recovery time objective (RTO)**, **recovery point objective (RPO)**, and cost considerations.

---

## **A. Backup and Restore**

A **simple, low-cost** DR method where data is **backed up** and restored when needed.
No standby systems → **slower recovery**, higher **RTO**.

a simple, straightforward, cost-effective method that backs up and restores data as needed.
Keep in mind that because none of your data is on standby, this method, while cheap, can be quite **time-consuming**.

🧠 **Trick:** *“Backup & restore = slow but cheap.”*

---

## **B. Pilot Light**

This method keeps **critical applications** and **data** at the ready so that it can be **quickly retrieved** if needed.

🧠 **Trick:** *“Pilot light = spark ready to ignite full environment.”*

---

## **C. Warm Standby**

This method keeps a **duplicate version** of your business' core elements running on standby at all times, which makes for a little downtime and an almost seamless transition.

A **scaled-down** but **continuously running** version of your environment.
Faster recovery than Pilot Light, moderate cost.

🧠 **Trick:** *“Warm standby = partially running environment, ready to scale.”*

---

## **D. Multi-Site Active-Active / Hot Standby**

Full production environment **running in two or more active locations**.
Traffic load is shared. Failover is instant → **near-zero downtime**.

🧠 **Trick:** *“Active-active = full power everywhere, always on.”*

---

### **Summary Table**

| DR Strategy                  | Running Resources | RTO      | RPO      | Cost     | Use Case                               |
| ---------------------------- | ----------------- | -------- | -------- | -------- | -------------------------------------- |
| **Backup & Restore**         | None (cold)       | High     | High     | Low      | Non-critical data                      |
| **Pilot Light**              | Minimal           | Moderate | Moderate | Moderate | Small workloads, dev/test              |
| **Warm Standby**             | Partial           | Low      | Low      | Higher   | Production apps needing quick recovery |
| **Multi-Site Active-Active** | Full              | Minimal  | Minimal  | High     | Mission-critical apps, zero downtime   |

---


# **AWS Storage — Resource Table Summary Table**
| Resource | Description |
|---------|-------------|
| Amazon EC2 Instance Store User Guide | A temporary storage option directly attached to the host computer of an EC2 instance, offering high-performance but non-persistent storage. |
| Amazon Elastic Block Store (Amazon EBS) | Scalable block storage that provides persistent, high-performance volumes for EC2 instances. |
| Amazon Elastic Block Store (Amazon EBS) FAQ | Frequently asked questions about Amazon EBS. |
| Amazon EBS Snapshots User Guide | Documentation on point-in-time backups of EBS volumes for data protection and restoration. |
| Amazon Data Lifecycle Manager User Guide | Automates the creation, retention, and deletion of EBS snapshots. |
| Amazon Simple Storage Service (Amazon S3) | Scalable object storage for storing and retrieving any amount of data from anywhere. |
| Amazon Simple Storage Service (Amazon S3) FAQ | Frequently asked questions about Amazon S3. |
| Amazon S3 Storage Classes | Information on the different S3 storage classes optimized for varying access patterns and cost needs. |
| Amazon S3 Versioning User Guide | Details on S3 versioning, which preserves multiple variants of objects to protect against deletions and overwrites. |
| Amazon S3 Buckets User Guide | Documentation on S3 buckets — cloud containers that store and manage data objects. |
| Amazon Elastic File System (Amazon EFS) | Fully managed, scalable file storage system for shared data access across multiple AWS resources. |
| Amazon Elastic File System (Amazon EFS) FAQ | Frequently asked questions about Amazon EFS. |
| Amazon FSx | Fully managed service that deploys file systems like Windows File Server, Lustre, NetApp ONTAP, and OpenZFS. |
| Amazon FSx for Windows File Server | FSx option delivering reliable, high-performance shared storage compatible with Windows workloads. |
| Amazon FSx for NetApp ONTAP | FSx option offering advanced data management with ONTAP, supporting both Windows and Linux workloads. |
| Amazon FSx for OpenZFS | FSx option providing high-performance, scalable file storage using the OpenZFS file system. |
| Amazon FSx for Lustre | FSx option optimized for compute-intensive workloads requiring fast data access. |
| AWS Storage Gateway | Hybrid cloud storage service integrating on-premises environments with AWS storage solutions. |
| Amazon S3 File Gateway | Gateway type enabling local file access to S3 objects with local caching for performance. |
| Tape Gateway | Gateway type supporting virtual tape backups to S3 using existing tape-based backup apps. |
| Volume Gateway | Gateway type offering iSCSI block storage volumes in both cached and stored configurations. |
