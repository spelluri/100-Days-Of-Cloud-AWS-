# Day01 - AWS Migration Task: Create an RSA Key Pair

## Overview

The Nautilus DevOps team is preparing to migrate a portion of their infrastructure to the AWS cloud. Due to the complexity and scale of this migration, the team has chosen an incremental, phased approach. By breaking the migration down into smaller and manageable tasks, the team can ensure smooth implementation, reduced risk, and optimal resource utilization.

This document outlines one of the initial tasks in the migration plan: **creating a key pair in AWS**.

---

## 🎯 Task Objective

Create an **RSA key pair** in AWS with the following requirements:

* **Key Pair Name:** `devops-kp`
* **Key Pair Type:** `rsa`

---

## 🛠️ Steps to Create the Key Pair

### **Using AWS Management Console**

1. Log in to the **AWS Management Console**.
2. Navigate to **EC2 Dashboard**.
3. In the left-hand menu, select **Key Pairs** under **Network & Security**.
4. Click on **Create key pair**.
5. Provide the following details:

   * **Name:** `devops-kp`
   * **Key pair type:** `RSA`
   * **Private key file format:** `.pem` (recommended) or `.ppk` (for Windows/Putty)
6. Click **Create key pair**.
7. The private key file will automatically download. Store it securely.



## 📌 Notes

* Save and protect the private key carefully. Losing it means losing access to any EC2 instances associated with it.
* Keys should **never** be shared or committed to a Git repository.

---

## ✅ Task Completed

The key pair `devops-kp` (type: RSA) is successfully created as part of the AWS migration preparation steps.
