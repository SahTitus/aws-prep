# Reserved Instances (RIs)

### 🟩 **Most Effective (Overall)**

> **Standard Reserved Instances** are the **most cost-effective** if your workload is stable and predictable.

> If you expect to change instance types, **Convertible RIs** are more effective overall for flexibility.

| Feature              | **Standard RI**   | **Convertible RI** | **Scheduled RI**     |
| -------------------- | ----------------- | ------------------ | -------------------- |
| Discount             | 💰 Highest (~72%) | Moderate (~54%)    | Lowest               |
| Flexibility          | ❌ Low             | ✅ High             | ⏱️ Time-based        |
| Duration             | 1 or 3 years      | 1 or 3 years       | Defined schedule     |
| Capacity reservation | Optional          | Optional           | Specific time window |
| Use case             | Steady workloads  | Evolving workloads | Periodic workloads   |



| **Type**           | **Summary (≤5 words)**             | **Discount Level**    | **Flexibility**          | **Best For**                  | **Term Length** |
| ------------------ | ---------------------------------- | --------------------- | ------------------------ | ----------------------------- | --------------- |
| **Standard RI**    | Highest savings, low flexibility   | 💰 **Up to ~72%**     | ❌ Low                    | Steady, predictable workloads | 1 or 3 years    |
| **Convertible RI** | Moderate savings, flexible options | 💰 **Up to ~54%**     | ✅ High                   | Changing instance needs       | 1 or 3 years    |
| **Scheduled RI**   | Reserved for specific times        | 💰 **Lowest savings** | ⚙️ Moderate (time-based) | Periodic or timed workloads   | Custom schedule |



### 💡 **1. Standard Reserved Instances**

**Description:**

* Offers the **biggest discount (up to ~72%)** compared to On-Demand.
* You commit to a **specific instance type**, **region**, and **tenancy** for **1 or 3 years**.

**Pros:**

* **Highest cost savings**.
* Best for **steady, predictable workloads** (e.g., a database server that always runs).

**Cons:**

* **Least flexibility** — can’t change instance family, only attributes like AZ or networking.
* **Flexibility**: Low. You are locked into a specific instance type, region, and operating system.

**🟩 Best when:**
Your workload is **consistent** and long-term (e.g., always-on production servers).

---

### 🔁 **2. Convertible Reserved Instances**

**Description:**

* Offers up to **~54% discount**.
* You can **change instance type, family, OS, or tenancy** during the term.

**Pros:**

* **Flexible** — you can adapt to changing requirements.
* Still provides solid savings.

**Cons:**

* **Less discount** than Standard RIs.
* Requires some planning when exchanging.

**🟩 Best when:**
Your instance needs **may change over time**, but you still want **long-term savings**.

---

### 🕒 **3. Scheduled Reserved Instances**

**Description:**

* Lets you **reserve capacity** for specific time windows (e.g., weekdays 9 AM – 5 PM).

**Pros:**

* Useful for **periodic workloads** (like batch jobs or business-hour apps).

**Cons:**

* **Least flexible and least used** today.
* **No major cost advantage** over Spot or Auto Scaling in most cases.
* AWS now encourages using **Savings Plans** instead.

**🟩 Best when:**
You have **predictable, time-based workloads** (rare use case now).

