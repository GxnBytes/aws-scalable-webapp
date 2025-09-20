# React App Deployment on AWS with Elastic Beanstalk & Terraform

![Status](https://img.shields.io/badge/status-In%20Development-yellow)

## 🚀 Project Overview

This project demonstrates how to deploy a **React application** to **AWS Elastic Beanstalk**, using **Terraform** for automation.

Elastic Beanstalk simplifies cloud deployment by handling **provisioning, scaling, and load balancing**, so you can focus on building your app—not managing infrastructure manually.

All infrastructure is created using **Infrastructure as Code (IaC)**, not through the AWS Console.

---

## 🎯 Objectives

- Efficiently deploy a React app on AWS
- Learn how to use Elastic Beanstalk for managing app environments
- Automate infrastructure setup using **Terraform**
- Practice IaC and version control using GitHub

---

## 🛠 Tools & Technologies

- **React** – Frontend application
- **AWS Elastic Beanstalk** – Managed deployment, scaling, and load balancing
- **Terraform** – Infrastructure as Code
- **GitHub** – Version control and source hosting

---

## 🧱 Project Structure

```bash
.
├── terraform/               # All Terraform configuration files
│   ├── main.tf
│   ├── variables.tf
│   └── outputs.tf
├── react-app/               # React frontend application
│   └── ...
├── README.md
└── .gitignore
```

## ✅ Key Takeaways

- Hands-on experience deploying frontend apps to AWS
- Practiced real-world Infrastructure as Code workflows
- Gained exposure to auto scaling, load balancing, and cost management
- Reinforced use of Terraform for production-like environments

## 💡 Notes

- Always version control your code and infrastructure using GitHub.
- Elastic Beanstalk makes it easy to manage deployments, but learning Terraform gives you total control and automation.
- Don’t forget to 'terraform destroy' resources to avoid unnecessary charges.
