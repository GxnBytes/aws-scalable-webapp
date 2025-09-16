# Cloud Security Lab (AWS)  
![Status](https://img.shields.io/badge/status-In%20Development-yellow)

## Project Overview  
This project focuses on deploying and securing a cloud-native workload in **AWS**. The goal is to build a secure web application environment by applying best practices in **identity and access management (IAM)**, **network security**, **logging**, **monitoring**, and **data protection**.  

By configuring IAM roles, security groups, logging pipelines, and alerts, this lab demonstrates how to design a resilient and compliant cloud environment while ensuring visibility into potential threats.  

---

## Skills Developed
- Designing and implementing IAM policies and roles  
- Configuring AWS-native logging and monitoring tools  
- Building alerts for suspicious activities (failed logins, network anomalies)  
- Applying encryption at rest and in transit  
- Securing web applications using AWS security services  
- Understanding compliance-focused controls for cloud workloads  

---

## AWS Tools & Services Used
- **IAM** – User and role management  
- **CloudTrail** – API activity logging  
- **CloudWatch** – Log monitoring, metrics, and alerts  
- **Security Groups** – Ingress/egress filtering  
- **S3 (Encrypted)** – Secure storage for logs and artifacts  
- **KMS** – Key management for encryption  

---

## Lab Steps  

### 1. Environment Setup
- Deployed a secure web application on **AWS EC2**  
- Configured IAM roles and enforced least-privilege policies  
- Applied **Security Groups** for controlled inbound/outbound traffic  

### 2. Logging & Monitoring
- Enabled **CloudTrail** for event logging  
- Forwarded logs to **CloudWatch** for centralized monitoring  
- Configured alerts for:  
  - Multiple failed login attempts  
  - Unauthorized access to sensitive resources  
  - Suspicious network traffic patterns  

### 3. Data Protection & Compliance
- Enforced encryption at rest and in transit using **KMS**  
- Verified compliance against **CIS Benchmarks** and AWS best practices  
- Applied security posture recommendations from **AWS Trusted Advisor**  

---

## Challenges  
- Balancing granular IAM policies with operational usability  
- Fine-tuning Security Groups to allow functionality without overexposing resources  

---

## Learning Outcomes  
- Gained practical experience in **AWS cloud security architecture**  
- Applied **defense-in-depth** principles in a single-cloud environment  
- Strengthened troubleshooting skills in log forwarding and alert configuration  
- Learned to implement proactive monitoring and response in AWS  
