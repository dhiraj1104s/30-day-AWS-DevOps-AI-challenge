# Day 1 - Enterprise-Grade IAM Access System

### 🚩 Problem
Permanent IAM user credentials pose a significant security risk if leaked, as they provide long-term access to cloud resources.

### 💡 Solution
I implemented a **Role-Based Access Control (RBAC)** system using **AWS STS** (Security Token Service). This setup grants temporary credentials only when needed, reducing the attack surface.

### 🛡️ Security Features
* **MFA Enforcement**: Configured Trust Policies with conditions that prevent role assumption unless the user has a valid MFA session.
* **Least Privilege**: The `DeveloperRole` is strictly limited to EC2 and S3 services. 
* **Validation**: Verified the security boundaries via "Access Denied" testing in the IAM console while assuming the Developer role.

### 🧪 How to Test
1. Log in to the AWS Console as an IAM user with `AssumeRole` permissions.
2. Click on the username in the top-right nav bar and select **Switch Role**.
3. Enter the Account ID (`238841126042`) and the role name (e.g., `DeveloperRole`).
4. Observe the color change in the navigation bar and verify restricted access to unauthorized services like IAM or RDS.

---
*Note: This project is part of my 30-Day AWS + DevOps + AI Challenge.*
