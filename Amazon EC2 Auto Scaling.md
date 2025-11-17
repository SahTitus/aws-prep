# ⚙️ Amazon EC2 Auto Scaling — Exam Ready Notes

## 🚀 Overview
- **Automatically adjusts** EC2 instance count based on **application demand**.  
- Ensures **high availability** and **cost efficiency**.  
- Two scaling types:  
  - **Dynamic scaling:** Reacts in real time to demand changes.  
  - **Predictive scaling:** Anticipates future demand using trends.  
**🧠 Trick:** *“Dynamic = Now, Predictive = Ahead.”*

---

## 🧩 Auto Scaling Groups (ASG)
A **collection of EC2 instances** that automatically scales **in/out** to match workload demand.

---

### 🔹 1. Minimum Capacity
- **Lowest number of instances** that must always run.  
- Ensures application never scales below safe threshold.  
- Example: **4 instances**.  
**🧠 Trick:** *“Minimum = Must always have.”*

---

### 🔹 2. Desired Capacity
- **Target instance count** for normal workload.  
- If not set, defaults to **minimum capacity**.  
- Example: **6 instances**.  
**🧠 Trick:** *“Desired = Sweet spot.”*

---

### 🔹 3. Maximum Capacity
- **Upper limit** on number of instances to prevent overscaling or cost spikes.  
- Example: **12 instances**.  
**🧠 Trick:** *“Maximum = Money cap.”*

---

### ✅ Summary Table

| Setting | Purpose | Example | Trick |
|----------|----------|----------|-------|
| Minimum | Always running baseline | 4 | Must always have |
| Desired | Target instance count | 6 | Sweet spot |
| Maximum | Scaling upper limit | 12 | Money cap |




#
#

# 🌐 Elastic Load Balancing (ELB) — Routing Methods

To **optimize traffic distribution**, ELB uses multiple **routing algorithms** for efficient load management and better performance.

---

## ⚙️ Routing Methods

### 🔸 **Round Robin**
- Distributes traffic **evenly** across all servers in a **cyclic** order.  
**🧠 Trick:** *“Takes turns — like a wheel.”*

---

### 🔸 **Least Connections**
- Sends traffic to the server with the **fewest active connections**.  
**🧠 Trick:** *“Go where it’s least busy.”*

---

### 🔸 **IP Hash**
- Uses the **client’s IP address** to always route requests to the **same server**.  
**🧠 Trick:** *“Same IP → Same server.”*

---

### 🔸 **Least Response Time**
- Chooses the server with the **fastest response time** and **lowest load**.  
**🧠 Trick:** *“Fastest wins.”*
