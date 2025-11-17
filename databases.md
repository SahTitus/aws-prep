# DATABASES
---

# #️⃣ **AWS Shared Responsibility Model for Databases – Exam Notes**

AWS groups database services into **three responsibility levels**:

* **Fully Managed**
* **Managed**
* **Unmanaged**

---

# ✅ **1. Fully Managed Databases**

### **Definition**

AWS handles **almost everything**:

* Provisioning
* Scaling
* Backups
* Patching
* Monitoring
* High availability
* Performance optimizations
* Security patches

**Customer only manages:**
✔ Database schema
✔ Data modeling
✔ Access permissions

### **Examples**

* **Amazon DynamoDB**
* **Amazon Aurora (Serverless especially)**
* **Amazon RDS Proxy**
* **Amazon ElastiCache**
* **Amazon QLDB**
* **Amazon Neptune**
* **Amazon DocumentDB**
* **Amazon MemoryDB**

### **Exam Keyword Trigger**

> “AWS does everything except data and access control.”

### **Shortcut Memory Trick**

**Fully Managed = “AWS is the DBA.”**
(You only put your data in.)

---

# ✅ **2. Managed Databases**

### **Definition**

AWS handles:

* Hardware provisioning
* Backups
* Patching
* Basic maintenance

Customer handles:
✔ Database engine configurations
✔ Query tuning
✔ User/permission design
✔ Performance optimization
✔ Indexing

### **Examples**

* **Amazon RDS (MySQL, PostgreSQL, SQL Server, Oracle, MariaDB)**
* **Amazon Redshift** (AWS handles infra, you handle queries & schema)

### **Exam Keyword Trigger**

> “AWS handles infrastructure & maintenance, customer handles tuning.”

### **Shortcut Memory Trick**

**Managed = “AWS manages the box; you manage the brain.”**
(AWS gives you the database engine ready, but you tune and operate it.)

---

# ✅ **3. Unmanaged Databases**

### **Definition**

Customer handles EVERYTHING:

* OS installation
* Database installation
* Patching
* Backups
* Replication
* HA setup
* Scaling
* Monitoring
* Security hardening
* Query tuning
* Performance optimization

AWS only provides:
✔ EC2 infrastructure
✔ Networking
✔ Hypervisor security

### **Example**

* **MySQL/PostgreSQL/SQL Server installed on Amazon EC2**
* **MongoDB on EC2**
* **Cassandra on EC2**

### **Exam Keyword Trigger**

> “Customer is responsible for ALL administrative tasks.”

### **Shortcut Memory Trick**

**Unmanaged = “EC2 = You Do Everything.”**
(If it's on EC2, AWS does almost nothing for the database.)

---

# 🎯 **SUPER MEMORY TRICK (FASTEST)**

### **F → M → U = AWS work decreases**

Think:

> **F = Full AWS control**
> **M = Mixed**
> **U = You do everything**

Or even easier:

> **Fully Managed → AWS does 90%**
> **Managed → AWS does 50%**
> **Unmanaged → AWS does 0%**

---

# 📘 **Exam One-Liners**

Use these exact lines for quick recall:

* **Fully Managed** → “AWS is the DBA.”
* **Managed** → “AWS manages infra; you manage database engine.”
* **Unmanaged** → “EC2 self-hosted DB: customer manages everything.”

---



---

# #️⃣ **AWS Relational Databases – Summary**

---

# 🟦 **Relational Databases (Concept)**

* Use a **rigid schema**
* Organize data into **tables (rows + columns)**
* Support **relationships** between tables
* On AWS, the relational services you explore:
  ✔ **Amazon RDS**
  ✔ **Amazon Aurora**

---

# 🟧 **Amazon RDS (Managed Relational Database Service)**

### 🔹 **What RDS Handles**

* Backups
* Patching
* Hardware provisioning
* Automated monitoring
* Vertical/horizontal scaling

### 🔹 **Resilience Features**

* **Multi-AZ** deployment for automatic failover
* **Automated backups**
* **Manual DB snapshots** (full backups for PITR or archiving)

### 🔹 **Security**

* VPC network isolation
* Encryption **in transit**
* Encryption **at rest**

### 🔹 **Supported Engines**

* **Aurora**, **MySQL**, **PostgreSQL**, **MariaDB**, **Oracle**, **SQL Server**

### 🔹 **Use Cases**

* Web applications
* Enterprise workloads
* E-commerce product inventories

---

# 🟧 **Amazon RDS – Benefits**

### ✔ **Cost Optimization**

* No upfront hardware cost
* Pay-as-you-go
* Reduces operational cost via automation

### ✔ **Multi-AZ Deployment**

* Standby instance in another AZ
* Automatic failover
* Minimal downtime

### ✔ **Performance Optimization**

* Automated resource management
* Read replicas for offloading reads
* Performance Insights for analyzing load

### ✔ **Security Controls**

* VPC isolation
* Encryption (rest + transit)
* Automated backups + Multi-AZ = resiliency

---

# 🟦 **Amazon Aurora**

### 🔹 **General Description**

* Managed relational database
* Compatible with **MySQL** and **PostgreSQL**
* Designed to **reduce unnecessary I/O operations**
* Auto-scalable
* Auto replication across multiple AZs
* Fault-tolerant
* Automated backups + encryption + monitoring

### 🔹 **Use Cases**

* Gaming
* Media & content management
* Real-time analytics

---

# 🟧 **Aurora – Benefits**

### ✔ **High Performance & Availability**

* **5× throughput** of MySQL
* **3× throughput** of PostgreSQL
* Distributed storage across multiple nodes

### ✔ **Automated Storage + Backup Management**

* Auto-grow from **10 GB → 128 TB**
* Continuous backup to **Amazon S3**
* Supports point-in-time recovery

### ✔ **Advanced Replication + Fault Tolerance**

* Replicates data across **3 AZs**
* **6 total copies**
* **99.99% availability**
* Automatic failover to healthy replicas

---

# 🟩 **Test Your Skills — Explained (From Given Text)**

### **1. AnyCompany Retail — Needs continuous operation + critical inventory database**

➡ **Correct Answer: Multi-AZ deployments**

Why?

* Provides automatic failover
* Ensures minimal downtime
* Ensures continued database operation during failures
  *(Exactly stated in the text.)*

---

### **2. AnyCompany Financial — Needs high throughput MySQL replacement**

➡ **Correct Answer: Aurora high-performance storage architecture (5× MySQL)**

Why?

* Aurora distributed system gives **5× throughput of MySQL**
* Designed for **high transaction workloads**
  *(Exactly stated in the text.)*

---





Below is a **clean, exam-ready summary** **ONLY based on the information you provided** — optimized for fast memorization and AWS exam recall.

---

# #️⃣ **NoSQL Databases & Amazon DynamoDB — Exam Summary (Based ONLY on Your Text)**

---

# 🟦 **NoSQL Databases (Concept)**

### 🔹 What makes NoSQL different from relational DBs?

* **Non-relational** structure
* No tables with rows/columns
* Uses **key-value pairs**
* Data stored as **items** with **unique keys**
* Supports **flexible schemas**

---

# 🟧 **Amazon DynamoDB (Fully Managed NoSQL)**

### 🔹 What DynamoDB Is

* Fully managed NoSQL database
* Supports **document + key-value** data
* Designed for **fast, predictable performance**
* **Flexible schema**
* **Scales automatically**
* Only pay for resources used
* Built-in security
* Data automatically spread across multiple servers for performance and workload handling

### 🔹 Use Cases

* Gaming platforms
* Financial services apps
* Mobile apps with global user bases

---

# 🟩 **DynamoDB Benefits**

---

## ✔ **1. Scalability with Provisioned Capacity**

* Auto scales throughput **up or down**
* Maintains performance based on **target utilization**
* No practical limits on table size
* Supports unpredictable or growing workloads

---

## ✔ **2. Consistent High Performance**

* **Single-digit millisecond response times**
* Automatic data distribution across many servers + SSDs
* Predictable performance at any scale

---

## ✔ **3. High Availability & Durability**

* **99.999% availability**
* Replicates data across **3 distinct facilities in a Region**
* Maintains multiple copies **in separate AWS Regions**
* Resilient to facility-level failures

---

## ✔ **4. Data Encryption**

* Encryption **at rest & in transit**
* Data automatically encrypted before storage
* Choose from different encryption key types

---

# 🟦 **Test Your Skills — Explained (from your content)**

### **Scenario:**

Unpredictable traffic + need consistent performance + don’t want to manage DB operations.

### **Correct Answer:**

➡ **Auto scaling with provisioned capacity**

### **Why? (Based on the text)**

* Automatically adjusts capacity when traffic spikes
* Keeps performance consistent
* Reduces cost during low traffic
* Eliminates manual DB management

---





---

# #️⃣ **In-Memory Caching & Amazon ElastiCache — Exam Summary**

---

# 🟦 **In-Memory Caching (Concept)**

### 🔹 What is an in-memory cache?

* High-speed storage layer using **RAM**
* Retrieves data **hundreds/thousands of times faster** than disk-based storage
* Applications check the **cache first**, reducing load on primary DBs
* Ideal for frequently accessed / repeated data

### 🔹 Common cached data

* Session data
* API responses
* Database query results
* Frequently used info across apps

---

# 🟥 **Amazon ElastiCache (Fully Managed In-Memory Cache)**

### 🔹 What ElastiCache Is

* Fully managed **in-memory caching** service
* Supports **Redis, Valkey, and Memcached**
* Automatically detects & replaces **failed nodes**
* Provides **consistent high performance**

### 🔹 Use Cases

* Session data management
* Database query acceleration
* Gaming leaderboards

---

# 🟩 **ElastiCache Benefits**

---

## ✔ **1. High Performance for Redis, Valkey, Memcached**

* Automates provisioning, patching, monitoring
* Easily scale nodes up/down
* Ensures low-latency, high-throughput caching

---

## ✔ **2. High Availability**

* Continuously monitors primary nodes
* Auto-promotes replica to primary during failures
* Failover completes within minutes
* Minimizes downtime

---

## ✔ **3. Multi-AZ Replication**

* Replicates across multiple Availability Zones
* Protects against AZ failures
* Ensures data availability during outages

---

## ✔ **4. Data Encryption**

* **At rest:** encrypts data on disk + backups
* **In transit:** TLS encryption during transfers
* Protects sensitive data end-to-end

---

# 🟦 **Test Your Skills — Answer Summary**

### ❓ **Which problem does Amazon ElastiCache solve?**

➡️ **Performance bottlenecks due to high latency and throughput constraints**

### ✔ Why?

ElastiCache stores frequently accessed data in RAM → lowers DB load → improves response times.

---





---

# 📘 Additional AWS Database Services — Exam-Ready Summary

## 📌 Amazon DocumentDB (MongoDB-Compatible)

### **What It Is**

A fully managed **document database** designed for **semi-structured JSON-like data**, compatible with **MongoDB APIs, drivers, and tools**.

### **When to Use**

* Frequent **schema changes**
* Document-oriented workloads
* Applications needing flexible JSON document storage

### **Key Use Cases**

* Content management systems (CMS)
* Catalog & inventory management
* User profiles & personalization systems

### **Benefits**

#### ✅ **MongoDB Compatibility**

* Drop-in replacement
* Minimal migration changes
* Use same MongoDB tools & commands

#### ✅ **Performance & Scalability**

* Auto-scales storage **up to 64 TB**
* Millions of requests/sec
* Scale compute up/down anytime

#### ✅ **High Read Throughput**

* Up to **15 replicas** sharing the same storage
* Great for read-heavy workloads

---

---

## 📌 AWS Backup

### **What It Is**

A fully managed, **centralized backup management** service for AWS resources and on-prem systems.

- With **AWS Backup**, you can define and manage **backup policies** at the **organization level** and implement them **across all related AWS accounts and Regions** automatically.

### **Why It Exists**

Solves **fragmented backup approaches** by centralizing everything in **one dashboard**.

### **Key Use Cases**

* Disaster recovery across Regions
* Compliance-driven backup retention
* Centralizing backups for many services

### **Benefits**

#### ✅ **Centralized Backup Management**

* One dashboard for EBS, EFS, RDS, DynamoDB, etc.
* Automated backup schedules
* Enforce **organization-wide backup policies**

#### ✅ **Cross-Region Backup Replication**

* Automatic replication for DR
* Restore from another Region during outages

#### ✅ **Compliance & Security**

* Detailed logs & reports
* Policy enforcement
* Encrypted backups

---

---

## 📌 Amazon Neptune

### **What It Is**

A fully managed **graph database** designed for **highly connected datasets**.

- **Neptune** is optimized for **storing and querying highly connected data** with **millisecond latency.**

### **Best For**

Understanding **relationships**, not just data.

### **Key Use Cases**

* Social network connections
* Fraud detection & pattern analysis
* Recommendation systems & search graphs

### **Benefits**

#### ✅ **Purpose-Built for Graphs**

* Supports **Property Graph** + **RDF** models
* Optimized for relationship traversal

#### ✅ **High Performance at Scale**

* Query **billions of relationships in milliseconds**
* Storage auto-grows up to **64 TB**
* Fast graph traversal engine

---

---

# 📝 Exam Quick Answers (For Fast Recall)

## ✔️ What problem does AWS Backup solve?

➡️ **Fragmented backup approaches across AWS services**

## ✔️ Primary feature of Amazon DocumentDB?

➡️ **MongoDB compatibility**

## ✔️ Benefit of Amazon Neptune?

➡️ **Low-latency queries on highly connected data**

---

# 🎯 Ultra-Fast Memorization Cheats

### **DocumentDB = MongoDB in AWS**

* JSON docs
* Flexible schemas
* Scales to 64 TB
* 15 replicas

### **AWS Backup = One Backup Dashboard**

* Centralized
* Automated
* Cross-Region
* Compliance-ready

### **Neptune = Social Graph Brain**

* Relationship-focused
* Graph traversal
* Millisecond query speed

---



| **Resource Link**                                   | **Description**                                                                                                                                                                                     |
| --------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Amazon Relational Database Service (Amazon RDS)** | A relational database service supporting multiple engines like MySQL, PostgreSQL, and Microsoft SQL Server with automated maintenance and backups                                                   |
| **Amazon RDS Security**                             | Detailed information about security configurations in Amazon RDS                                                                                                                                    |
| **Amazon Aurora**                                   | A cloud-native database offering superior performance and availability over traditional databases while maintaining MySQL and PostgreSQL compatibility                                              |
| **AWS Database Migration Service (AWS DMS)**        | A service that provides seamless database migration between source and target databases while keeping the source database operational                                                               |
| **Amazon DynamoDB**                                 | A NoSQL database service providing single-digit millisecond performance at any scale with built-in security                                                                                         |
| **Amazon ElastiCache**                              | An in-memory caching service that supports Redis, Valkey, or Memcached to improve application performance through faster data retrieval                                                             |
| **Amazon DocumentDB**                               | A MongoDB-compatible document database service designed for mission-critical workloads with automatic scaling                                                                                       |
| **Amazon Backup**                                   | A centralized service for automating and managing data backups across AWS services and on-premises resources                                                                                        |
| **Amazon Neptune**                                  | A graph database service optimized for storing and querying highly connected data relationships                                                                                                     |
| **What Is a Relational Database?**                  | A structured database using tables with predefined schemas, supporting complex queries and transactions through SQL for consistent data relationships                                               |
| **What Is a NoSQL Database?**                       | A nonrelational database offering flexible schemas and high scalability for varied data types, optimized for specific data models and patterns                                                      |
| **What Is an In-Memory Caching Service?**           | A high-speed data storage layer using RAM instead of disk storage, delivering microsecond latency for frequently accessed data                                                                      |
| **AWS Shared Responsibility Model**                 | AWS is responsible for security of the cloud (infrastructure, hardware, networking, facilities) while customers are responsible for security in the cloud (data, configuration, access management). |
