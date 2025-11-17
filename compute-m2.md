* **Multi-tenancy** allows multiple virtual machines to share resources on the same physical host, with isolation between them.

# THREE PHASES IN LAUNCHING AND EC2
* ## **Launch**:
When launching an EC2 instance, you select 
* an **AMI** (which defines the **OS** and addtional software) and 
* an **instance type** (CPU, memory, and network capacity).
* **instance type**: determines the underlying hardware resources, such as CPU, memory, and network performance.

* ## **Connect**:
**Ways to connect to an EC2 instance:**

* 🔹 **SSH** — for Linux instances
* 🔹 **Remote Desktop Protocol (RDP)** — for Windows instances
* 🔹 **AWS Systems Manager** — secure, browser-based access (no direct network login)
* 🔹 **Network connections** — for applications interacting over the internet or VPC

* ## **Use**:
After you are connected to the instance, you can begin using it to run commands, install software, add storage, organize files, and perform other tasks.


#
# 🧠 EC2 Instance Types 

## ⚙️ General Purpose
- **Balanced** mix of **compute, memory, and networking**.  
- Ideal for **web services**, **code repos**, and **uncertain workloads**.  
**Trick:** *Think “G” = “General use” — good for most workloads.*

---

## 💻 Compute Optimized
- Best for **compute-intensive tasks** like **gaming servers**, **HPC**, **ML**, **scientific modeling**.  
- Focus on **high CPU performance**.  
**Trick:** *“C” = CPU power.*

---

## 🧮 Memory Optimized
- For **memory-intensive tasks**: **large datasets**, **data analytics**, **databases**.  
- Delivers **fast memory performance**.  
**Trick:** *“R” = RAM heavy.*

---

## 💾 Storage Optimized
- Designed for **high I/O** and **locally stored data**.  
- Used in **data warehousing**, **large databases**, **I/O-intensive apps**.  
**Trick:** *“I” = I/O performance.*



#
#

# 🧩 Amazon Machine Images (AMIs)

## 📦 What is an AMI?
- **Pre-built virtual machine image** used to **launch EC2 instances**.  
- Includes **OS**, **storage setup**, **architecture**, **launch permissions**, and **pre-installed software**.  
- One AMI can launch **multiple identical instances**.

**Trick:** *“AMI = A Machine Image” — blueprint for your EC2.*

* OR
* An AMI is a pre-configured virtual machine image that contains the operating system, application server, and applications. This helps to launch EC2 instances quickly with the desired software and settings.

---

## 🛠️ Three Ways to Use AMIs
1. **Custom AMIs** – Build your own with specific configs & software.  
2. **AWS AMIs** – Pre-configured by AWS for common OS/software.  
3. **Marketplace AMIs** – From third-party vendors for specialized use cases.

**Trick:** *Remember “CAM” — Custom, AWS, Marketplace.*

---

## 🔁 AMI Repeatability
- Ensures **consistent environments** across instances.  
- Supports **automation, scaling, and testing consistency**.  
- Reduces **errors** and simplifies **management**.

**Trick:** *Same AMI = Same setup every time.*



* To launch an EC2 instance for a web server, configure the **AMI** to define the **operating system and software**; select the **instance type** to allocate CPU, memory, and storage; and set up **storage options**, including the **type and size of the volume**.


#\



# ⚙️ Additional Compute Services — Exam-Ready Notes

AWS provides **purpose-built compute services** for specialized use cases — from web app deployment to hybrid cloud integration.

---

## 🌐 **Elastic Beanstalk**
- **Type:** Fully managed **web app deployment & management** service.  
- **Key Features:** Automates **infrastructure provisioning**, **load balancing**, **scaling**, and **health monitoring**.  
- **Supports:** Java, .NET, Python, Node.js, Docker, and more.  
- **Good For:** Web apps, RESTful APIs, microservices, and mobile backends.

🧠 **Trick:** *“Beanstalk grows your web apps automatically.”*

---

## 🧮 **AWS Batch**
- **Type:** Fully managed **batch computing service**.  
- **Key Features:** Automatically **schedules, manages, and scales** compute resources for jobs.  
- **Good For:** Large-scale **parallel workloads** — scientific computing, ML training, risk analysis, data processing.

🧠 **Trick:** *“Batch = Big jobs, auto handled.”*

---

## 💡 **Amazon Lightsail**
- **Type:** Simplified **virtual private server (VPS)** service.  
- **Key Features:** Offers **compute, storage, databases, and networking** at a **predictable monthly price**.  
- **Good For:** Small businesses, blogs, test environments, and simple web apps.

🧠 **Trick:** *“Lightsail = Light AWS experience.”*

---

## 🏠 **AWS Outposts**
- **Type:** **Hybrid cloud** service extending AWS **on-premises**.  
- **Key Features:** Brings **AWS compute, storage, and networking** to **local data centers**.  
- **Good For:** **Low-latency**, **regulatory**, and **legacy app** workloads that need on-prem + cloud consistency.

🧠 **Trick:** *“Outposts = AWS inside your data center.”*

---

### 🧩 **Summary Table**

| Service | Type | Management | Best For | Trick |
|----------|------|-------------|-----------|--------|
| **Elastic Beanstalk** | Web app platform | Fully managed | Web apps & APIs | *Grows your app automatically* |
| **AWS Batch** | Batch compute | Fully managed | Parallel processing | *Big jobs auto handled* |
| **Lightsail** | VPS service | Simplified | Small projects | *Light AWS experience* |
| **Outposts** | Hybrid cloud | Fully managed | On-prem + cloud | *AWS inside your data center* |




