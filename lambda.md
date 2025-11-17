# ⚙️ AWS Lambda — Key Components & Responsibilities

**AWS Lambda** is a **serverless compute service** that runs your code in response to events — without managing servers, scaling, or OS maintenance.  

---

## 🧩 **Key Components**

- **Function:**  
  The core **code logic** you write to perform a specific task or operation.

- **Trigger:**  
  The **event source** (like S3 upload, API Gateway request, or DynamoDB stream) that **invokes** your Lambda function.

- **Runtime:**  
  The **language environment** (e.g., Node.js, Python, Java) that executes your function code.

---

## ☁️ **AWS Responsibility**
AWS automatically manages:
- **Server provisioning**  
- **Auto-scaling**  
- **Operating system patching**

---

## 🧠 **Trick:**  
👉 *“Lambda = Code runs when Trigger fires — AWS does the rest!”*
