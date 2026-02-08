# 🔐 AWS Key Management Service (KMS) – Data Encryption & Audit Lab

**Portfolio Project – CloudWthAlex**

---

## 📌 Project Overview

This hands-on lab demonstrates how to protect cloud data using **AWS Key Management Service (KMS)** and how encryption activity is tracked using **CloudTrail**.

In this project, I created and managed encryption keys, secured data stored in Amazon S3, and monitored how keys were used through audit logs. This simulates how real companies protect sensitive data such as customer records, financial files, and internal documents.

This lab focuses on **cloud security fundamentals**, **data protection**, and **access control**, which are critical skills for Cloud Engineers and Security Engineers.

---

## 🎯 Objectives

By completing this lab, I was able to:

* Create and configure AWS KMS encryption keys
* Encrypt files stored in Amazon S3 using SSE-KMS
* Configure CloudTrail logging for security auditing
* Monitor key usage and encryption activity
* Control which users can access and manage encryption keys

---

## 🧱 Architecture Diagram (Simplified)

```
                ┌────────────────────────────┐
                │        AWS CloudTrail       │
                │   (Logs all key activity)   │
                └──────────────┬─────────────┘
                               │
                               │ Logs stored
                               ▼
                       ┌─────────────────┐
                       │      Amazon S3   │
                       │  (Encrypted File)│
                       └─────────┬───────┘
                                 │
                                 │ Uses encryption key
                                 ▼
                        ┌─────────────────┐
                        │      AWS KMS     │
                        │  (myFirstKey)    │
                        └─────────────────┘
                                 │
                                 │ Permissions controlled by
                                 ▼
                           ┌────────────┐
                           │     IAM     │
                           │ Users/Roles │
                           └────────────┘
```

---

## 🔧 Technical Steps Completed

### 1️⃣ Created a KMS Encryption Key

* Created a **symmetric key** named: `myFirstKey`
* Assigned:

  * Key administrators
  * Key usage permissions
* Learned how AWS manages encryption keys using secure hardware (HSM)

**Skill demonstrated:** Cloud data protection & encryption management

---

### 2️⃣ Configured CloudTrail Logging

* Created a new CloudTrail trail
* Sent logs to an S3 bucket
* Enabled:

  * Management events
  * Data events
  * Insights events

**Skill demonstrated:** Governance, compliance, and activity monitoring

---

### 3️⃣ Encrypted Data in Amazon S3

* Uploaded an image file to S3
* Enabled:

  * Server-Side Encryption with KMS (SSE-KMS)
* Selected `myFirstKey` to encrypt the file

**What happens behind the scenes:**

* S3 requests KMS to encrypt the file
* KMS protects the encryption key
* Data is stored securely

**Skill demonstrated:** Secure cloud storage architecture

---

### 4️⃣ Tested Secure Access to Encrypted Data

* Accessed the file via AWS Console (success)
* Tried accessing via public URL (blocked)

**Security lesson learned:**
Even if a file is public:

* KMS encryption prevents unauthorized access
* Requests must be authenticated

**Skill demonstrated:** Understanding real-world cloud security controls

---

### 5️⃣ Monitored Encryption Activity Using CloudTrail

* Opened CloudTrail logs stored in S3
* Searched for:

  * Encryption key ID
  * File upload activity
* Verified audit trail of encryption usage

**Skill demonstrated:** Security auditing & forensic investigation

---

### 6️⃣ Managed Key Permissions

* Removed user access to the KMS key
* Re-added access again

This demonstrated:

* How to control who can use encryption keys
* How organizations protect sensitive systems

**Skill demonstrated:** IAM + KMS integration

---

## 🧠 Cloud Fundamentals Demonstrated

This lab strengthened my understanding of:

* Data encryption in the cloud
* Key lifecycle management
* Identity and access control
* Secure storage architecture
* Audit logging and compliance tracking

---

## 🌍 Real-World Relevance

This type of setup is commonly used in real companies to protect:

* Customer data
* Financial records
* Medical information
* Internal company documents

Typical use cases:

* Encrypting backups
* Protecting databases
* Securing confidential files
* Meeting compliance standards (ISO, SOC2, HIPAA)

---

## 🏆 Skills Gained

* AWS KMS key creation & management
* Data encryption using SSE-KMS
* CloudTrail log monitoring
* Secure S3 storage configuration
* Access control for encryption keys
* Understanding encryption workflows in AWS

---

## 🛠️ Services Used

* AWS Key Management Service (KMS)
* Amazon S3
* AWS CloudTrail
* AWS IAM

---

## 💼 Why This Project Matters (For Recruiters)

This project demonstrates hands-on experience with:

* Cloud security best practices
* Encryption at rest in AWS
* Access control design
* Compliance-ready audit logging
* Real-world enterprise security architecture

It shows the ability to:

* Protect sensitive cloud data
* Monitor encryption activity
* Manage security permissions

---

## 🚀 Author

**GitHub:** CloudWthAlex
**Career Path:** Cloud Engineer (Security-focused)
**Focus Areas:** AWS • Cloud Security • Infrastructure • Monitoring

---

## 📈 Next Improvements

Planned future enhancements:

* Encrypt EC2 volumes using KMS
* Apply KMS to RDS databases
* Automate key rotation
* Build Terraform version of this setup
* Create a full secure data pipeline project

---
