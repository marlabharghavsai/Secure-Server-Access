# 🔐 Secure Server Access  
*(Website Deployment in Private EC2 with NGINX Reverse Proxy in Public EC2)*

## 📌 Project Overview
**Secure Server Access** is a cloud networking project designed to **securely host a website** on a **private EC2 instance** inside a VPC, while making it accessible through a **public EC2 reverse proxy (NGINX)**.  
This setup ensures backend isolation, prevents direct internet access to the private server, and follows AWS security best practices.

---

## 🎯 Objectives
- Host a website on a **private EC2 instance** within a VPC.  
- Configure a **public EC2 instance** with **NGINX** as a reverse proxy.  
- Enable **restricted and secure SSH access** via a Bastion Host.  
- Apply **least-privilege access controls** using AWS Security Groups.  
- Ensure **end-to-end secure and isolated architecture**.

---

## 🏗 Architecture
- **VPC** with two subnets:  
  - Public Subnet → Bastion Host & Reverse Proxy (NGINX)  
  - Private Subnet → Web Server (Apache/NGINX)  
- **Internet Gateway (IGW)** for outbound connectivity in the public subnet.  
- **Security Groups** enforcing restricted access:  
  - Bastion Host → SSH from local machine  
  - Reverse Proxy → HTTP from 0.0.0.0/0, SSH only from Bastion  
  - Private Web Server → HTTP only from Reverse Proxy, SSH only from Bastion  

---

## ⚙️ Services & Tools Used
- **Amazon VPC** – Network isolation (public & private subnets)  
- **Amazon EC2** – Instances for Bastion, Proxy, and Web Server  
- **NGINX** – Configured as reverse proxy in the public EC2  
- **Security Groups** – Instance-level firewall and traffic control  
- **Elastic IPs** – Stable IPs for Bastion & Proxy  
- **Apache/NGINX** – Web server hosting the website on private EC2  

---

## 🚀 Implementation Steps
1. **VPC & Subnet Setup** – Created custom VPC, public/private subnets, IGW, and route tables.  
2. **EC2 Provisioning** – Launched 3 EC2 instances: Bastion Host, Reverse Proxy, and Private Web Server.  
3. **Secure Access** – SSH access restricted to Bastion Host → Web Server & Proxy.  
4. **Web Server Deployment** – Hosted a static website on the private EC2 instance.  
5. **NGINX Reverse Proxy** – Configured public EC2 with NGINX to forward requests to the private Web Server.  
6. **Testing & Validation** – Verified SSH paths, firewall restrictions, and web access only via the proxy.  
7. **Documentation** – Created full test plans, security group mappings, and architecture diagrams.  

---

## ✅ Key Outcomes
- Website is **accessible only via Reverse Proxy** (public EC2).  
- **Direct access to private EC2 is blocked** – ensuring backend isolation.  
- Implemented **secure SSH access** with Bastion Host.  
- Achieved a **secure, production-ready AWS architecture**.  

---

## 📊 Future Enhancements
- Enable **SSL/TLS with Let’s Encrypt** on the NGINX proxy.  
- Add **CloudWatch monitoring** and alerting for security logs.  
- Automate deployment with **Terraform or AWS CloudFormation**.  

---

## 👨‍💻 Project Duration
📅 Completed in **6 days** with step-by-step execution (Planning → Setup → Deployment → Testing → Documentation).  

---
