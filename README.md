# Pet Care Blog – Cloud Server Project  
**Student Name:** Alen Anand  
**Student ID:** 35115038  

---

## Project Overview  
This project is a **Pet Sitting and Pet Care Blog**, deployed on an AWS EC2 Ubuntu instance using **Apache** as the web server.  
The site provides helpful guidance for pet owners, including advice on nutrition, grooming, and finding trustworthy pet sitters.  

The goal of this project is to demonstrate the implementation of a cloud-based web server using Amazon Web Services (IaaS), including setup, deployment, DNS configuration, and basic scripting for maintenance.

---

## Cloud Server Configuration  

| Configuration Item | Details |
|--------------------|----------|
| **Cloud Provider** | Amazon Web Services (AWS) |
| **Instance Type** | t3.micro (Free Tier) |
| **Operating System** | Ubuntu 22.04 LTS |
| **Web Server** | Apache2 |
| **Elastic IP** | `51.21.80.118` |
| **Domain Name** | [http://petcareblog.online](http://petcareblog.online) |
| **Deployment Method** | Manual (SSH + Apache) |
| **Hosting Duration** | Continuous (demonstration project) |

---

## Setup Instructions  

### 1. Launch EC2 Instance  
- Selected Ubuntu 22.04 LTS, type `t3.micro`.  
- Created a key pair (`petcare.pem`).  
- Configured security group with inbound rules for:  
  - HTTP (Port 80) → 0.0.0.0/0  
  - SSH (Port 22) → 0.0.0.0/0  

### 2. Connect via SSH  
```bash
ssh -i "petcare.pem" ubuntu@51.21.80.118

### 3. Install and Enable Apache Web Server and Deploy HTML Website  

```bash
# Update and install Apache
sudo apt update
sudo apt install apache2 -y

# Enable and start Apache service
sudo systemctl enable apache2
sudo systemctl start apache2

# Check that Apache is active
sudo systemctl status apache2

# Deploy HTML website
cd /var/www/html

# Create or edit the website file
sudo nano index.html
# (Paste your Pet Care Blog HTML code here)

# Restart Apache to apply changes
sudo systemctl restart apache2

# Verify deployment by visiting in browser:
# http://51.21.80.118
# or your domain:
# http://petcareblog.online

