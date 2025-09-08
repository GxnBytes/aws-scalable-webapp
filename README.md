# Cloud Security Lab  
![Status](https://img.shields.io/badge/status-In%20Development-yellow)

## Project Overview  
This project focuses on deploying and securing a cloud-native workload in **AWS** and **Azure**.  
The objective is to build a secure web application environment by applying best practices in **identity and access management (IAM)**, **network security**, **logging**, **monitoring**, and **data protection**.  

By configuring IAM roles, security groups, logging pipelines, and alerts, this lab demonstrates how to design a resilient and compliant cloud environment while ensuring visibility into potential threats.  

---

## Skills Developed
- Designing and implementing IAM policies and roles  
- Configuring cloud-native logging and monitoring tools  
- Building alerts for suspicious activities (failed logins, network anomalies)  
- Applying encryption at rest and in transit  
- Securing web applications using AWS and Azure security services  
- Understanding compliance-focused controls for cloud workloads  

---

## Tools & Services Used  

### AWS
- IAM – User and role management  
- CloudTrail – API activity logging  
- CloudWatch – Log monitoring, metrics, and alerts  
- Security Groups – Ingress/egress filtering  
- S3 (Encrypted) – Secure storage for logs and artifacts  

### Azure
- Azure Active Directory (AAD) – Identity and access control  
- Azure Monitor – Logging and alerting  
- Azure Security Center – Posture management and threat protection  
- Network Security Groups (NSG) – Network segmentation  
- Key Vault – Secret and key management  

---

## Lab Steps  

### 1. Environment Setup
- Deployed a secure web application in both AWS EC2 and Azure VM  
- Configured IAM roles and enforced least privilege policies  
- Applied security groups and NSGs for controlled inbound/outbound traffic  

### 2. Logging & Monitoring
- Enabled CloudTrail (AWS) and Azure Monitor (Azure) for event logging  
- Forwarded logs to centralized monitoring  
- Configured alerts for:  
  - Multiple failed login attempts  
  - Unauthorized access to sensitive resources  
  - Suspicious network traffic patterns  

### 3. Data Protection & Compliance
- Enforced encryption at rest and in transit (KMS and Key Vault)  
- Verified compliance against CIS Benchmarks and security best practices  
- Enabled security posture recommendations from Azure Security Center and AWS Trusted Advisor  

---

## Challenges  
One of the main challenges was ensuring parity between AWS and Azure security controls. While the core principles of IAM, monitoring, and encryption remain the same, service-specific configurations required significant fine-tuning.  

Another challenge was balancing granular IAM policies with operational usability.  

---

## Learning Outcomes  
- Gained practical experience in multi-cloud security architecture  
- Learned to apply defense-in-depth principles in cloud environments  
- Strengthened troubleshooting skills in log forwarding and alert configuration  
- Understood how to implement proactive monitoring and response in AWS and Azure  

---

## Future Work  
- Automate security configuration using Terraform or Bicep  
- Integrate with SIEM tools such as Microsoft Sentinel or Splunk  
- Extend the lab to include container security (EKS and AKS)  
- Simulate attack scenarios to validate detection rules  

---
