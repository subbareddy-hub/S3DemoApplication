# AWS Parameter Store


- [x] Spring Cloud Config Recap
- [x] What Is Parameter Store
- [x] Setup And Demo




**AWS  Parameter Store** is a fully managed service that allows you to **store, manage, and retrieve configuration data and secrets** as key-value pairs.
 It provides a **centralized, secure, and versioned** way to manage environment-specific settings like database URLs, API keys, or feature flags.

 # AWS SQS (Simple Queue Service)
- [x] What Is SQS ?
- [x] Queue Types
- [x] Features
- [x] Hands On Demo
- [x] Use Cases




##  **What is SQS?**
- Amazon **Simple Queue Service** is a **fully managed message queueing service**.
- It helps **decouple microservices, distributed systems, and serverless applications**.
- Core idea: _Producer → Queue → Consumer_
- No direct connection between producer and consumer — they communicate via queue.






## Use Cases
### 1. **Order Processing in E-commerce**
- Customers place orders → requests go into an **OrderQueue**.
- Workers pick up orders one by one and process them (inventory check, payment, shipping).
 ✅ Ensures **no order is lost** even if the system is busy.
 ✅ Handles **high spikes on sale days** (like Flipkart Big Billion Day / Amazon sale).
---

### 2. **Decoupling Microservices**
- In a microservices setup:
    - **User Service** creates a user and puts a message in SQS.
    - **Email Service** reads the message and sends a welcome email.

- If the email service is down, messages wait in SQS until it’s back.
 ✅ Services are **loosely coupled** and don’t depend on each other being live.
---

### 3. **Video / Image Processing**
- A user uploads a video.
- Upload service pushes a message into **VideoProcessingQueue**.
- Background workers read the queue and process the video (compression, thumbnail creation, etc.).
 ✅ Handles **long-running background jobs**.
 ✅ Scales workers **up and down** easily.
---

### 4. **Payment Transactions**
- When you pay via UPI / card:
    - Payment request goes into **PaymentQueue**.
    - Worker processes payment with retry logic.
 ✅ Avoids **duplicate processing** (because of visibility timeout).
 ✅ Ensures **reliable transaction handling** even if bank API is slow.







# AWS SNS (Simple Notification Service)
- [x] What Is SNS ?
- [x] Key Features
- [x] Hands On Demo
- [x] Use Cases




# 📌 What is Amazon SNS?
Amazon **SNS** is a **fully managed messaging service** that helps you send messages or notifications from one place to many systems, apps, or users at the same time.

Think of it as a **megaphone** 📢:

- You (publisher) speak into it once,
- Everyone who has subscribed (subscribers) hears the message instantly.




## **Use Cases of SNS**
1. **Push notifications to users** (SMS/email alerts).
 👉 e.g., OTPs, delivery updates.
2. **Microservices eventing** – decouple services.
 👉 Order Service publishes → Inventory, Billing, and Notification services subscribe.
3. **Fan-out messaging** – One event → multiple systems.
 👉 Upload a file → trigger Lambda, notify via email, push to analytics.






# Github Copilot 
- [x] What is Copilot?
- [x] Integration With Intellij IDE
- [x] Copilot Modes - Chat, Autocomplete & Agent
- [x] Free & Paid Plans








# AWS Secret Manager
- [x] What is Secret Manager?
- [x] Features Of Secret Manager
- [x] Demo


**AWS Secrets Manager** is a fully managed service that helps you securely store, manage, and retrieve **secrets** like database credentials, API keys, OAuth tokens, and other sensitive configuration data.

It automatically handles **encryption, rotation, fine-grained access control (via IAM)**, and integrates easily with AWS services and applications. Instead of hardcoding credentials in your code, you fetch them securely at runtime from Secrets Manager.



###  Features of Secrets Manager
- **Secure Storage**: Stores DB creds, API keys, OAuth tokens, SSH keys.
- **Automatic Rotation**: For supported DBs like RDS MySQL, PostgreSQL, Aurora.
- **Tight IAM Integration**: Control who can access which secret.
- **Audit with CloudTrail**: See who accessed secrets and when.
- **Multi-Region replication**: Secrets can be replicated across regions for global apps.








# Host Static Website On AWS S3
- [x] AWS S3
- [x] Simple Static Website
- [x] Create S3 Bucket
- [x] Upload files
- [x] Configure Bucket For Static Website Hosting
- [x] Set Permissions
- [x] costing




### **1. Storage Costs**
- You pay for **how much data your website stores** in S3.
- S3 Standard: ~$0.023 per GB per month.
- Example: A 50 MB portfolio site costs **almost nothing**, around $0.001 per month.
---

### **2. Data Transfer / Bandwidth**
- You pay for data transferred **from S3 to your users**.
- First 1 GB per month → **Free**.
- 1 GB – 10 TB → ~$0.09 per GB.
- Small sites with ~1,000 visitors/month typically **stay free**.
---

### **3. Requests Costs**
- AWS charges for **requests to your bucket**: GET, PUT, POST, etc.
- GET requests are cheapest (~$0.0004 per 1,000 requests).
- Example: 100,000 GET requests → ~$0.04.
---

### 
### **1. Storage Costs**
- You pay for **how much data your website stores** in S3.
- S3 Standard: ~$0.023 per GB per month.
- Example: A 50 MB portfolio site costs **almost nothing**, around $0.001 per month.
---

### **2. Data Transfer / Bandwidth**
- You pay for data transferred **from S3 to your users**.
- First 1 GB per month → **Free**.
- 1 GB – 10 TB → ~$0.09 per GB.
- Small sites with ~1,000 visitors/month typically **stay free**.
---

### **3. Requests Costs**
- AWS charges for **requests to your bucket**: GET, PUT, POST, etc.
- GET requests are cheapest (~$0.0004 per 1,000 requests).
- Example: 100,000 GET requests → ~$0.04.


---

### **4. Total Estimate for a Small Portfolio**
- Storage: ~$0.001
- Bandwidth: $0 (for ~1 GB/month)
- Requests: ~$0.04
- **Total: ~$0.05/month**
>  “So, hosting a small portfolio on AWS S3 is almost free!” 







