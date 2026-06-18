# Amazon EC2 Notes (Cloud + DevOps Focus)

This file explains Amazon EC2 and how it is used in cloud and DevOps engineering.

---

# 1. What is EC2?

Amazon EC2 (Elastic Compute Cloud) is a cloud service that provides virtual servers in the cloud.

You can:
- Launch servers in minutes
- Install software
- Run applications
- Scale resources up or down

---

# 2. Why EC2 is Important in DevOps

In traditional IT:
- You buy physical servers

In cloud (AWS):
- You create virtual servers instantly

DevOps engineers use EC2 to:
- Host applications
- Test deployments
- Run backend services
- Debug production issues

---

# 3. EC2 Key Concepts

## Instance
A virtual machine (server).

## AMI (Amazon Machine Image)
A pre-built template (e.g., Ubuntu, Amazon Linux).

## Instance Type
Defines CPU, memory, performance.

Example:
- t2.micro (small, free tier)
- t3.medium (more powerful)

---

## Security Group
A virtual firewall controlling traffic.

Example:
- Allow SSH (port 22)
- Allow HTTP (port 80)

---

## Key Pair
Used for SSH login into the instance.

---

# 4. Launching an EC2 Instance (Basic Steps)

1. Go to AWS Console
2. Select EC2
3. Click "Launch Instance"
4. Choose AMI (Ubuntu recommended)
5. Choose instance type (t2.micro)
6. Create or select key pair
7. Configure security group:
   - SSH (22)
   - HTTP (80 if web server)
8. Launch instance

---

# 5. Connecting to EC2 (SSH)

```bash
ssh -i key.pem ubuntu@public-ip
```

---

# 6. Basic EC2 Setup Commands

After connecting:

```bash
sudo apt update
sudo apt upgrade -y
```

Install web server:

```bash
sudo apt install nginx -y
```

Check service:

```bash
systemctl status nginx
```

---

# 7. Hosting a Simple Website

After installing nginx:

Open browser:
```
http://public-ip
```

You should see the default Nginx page.

---

# 8. Stop vs Terminate

## Stop
- Instance is shut down
- Can be restarted
- Storage may remain

## Terminate
- Instance is deleted
- Cannot be recovered

---

# 9. Real-World DevOps Use Case

A company wants to deploy a website:

1. Launch EC2 instance
2. Install Nginx
3. Upload website files
4. Open port 80
5. Route traffic via DNS

This is basic cloud deployment.

---

# 10. Common Problems

## Cannot connect via SSH
- Security group missing port 22
- Wrong key
- Wrong IP

## Website not loading
- Port 80 not open
- Nginx not running
- Firewall blocking traffic

---

# 11. Mini Lab (DO THIS)

1. Launch EC2 instance (Ubuntu)
2. SSH into it
3. Install nginx
4. Open port 80
5. Access website in browser

---

# 12. What to Add Later

After you gain more AWS experience:

- IAM roles for EC2
- EC2 user data scripts
- Auto Scaling Groups
- Load Balancers
- EC2 monitoring with CloudWatch
- Infrastructure automation with Terraform

---

# 13. Why This Matters

EC2 is the foundation of cloud computing.

If you understand EC2 well, you understand:
- Servers
- Networking basics
- Deployment workflows
- Cloud infrastructure patterns
