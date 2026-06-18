# VPC Basic Networking Lab (AWS Cloud Networking)

This lab demonstrates how AWS networking works using VPC, subnets, and security groups.

---

# 🎯 Objective

- Understand how AWS networking is structured
- Create a custom VPC
- Create a public subnet
- Launch EC2 inside VPC
- Test internet connectivity
- Understand routing and access flow

---

# 🧱 Technologies Used

- AWS VPC
- Subnets
- Route Tables
- Internet Gateway
- EC2
- Security Groups

---

# 🧠 Concept Overview

A VPC is a virtual network in AWS where all resources live.

Inside a VPC you define:
- IP range (CIDR)
- Subnets (public/private)
- Routing rules
- Internet access rules

---

# 🏗️ Step 1: Create VPC

In AWS Console:

1. Go to VPC service
2. Click "Create VPC"
3. Select:
   - Name: devops-vpc
   - CIDR: 10.0.0.0/16

---

# 🌐 Step 2: Create Public Subnet

1. Go to Subnets
2. Create subnet:
   - Name: public-subnet
   - CIDR: 10.0.1.0/24
   - Attach to devops-vpc

---

# 🌍 Step 3: Create Internet Gateway

1. Go to Internet Gateways
2. Create IGW:
   - Name: devops-igw
3. Attach to VPC

---

# 🛣️ Step 4: Configure Route Table

1. Go to Route Tables
2. Select VPC route table
3. Add route:

```
Destination: 0.0.0.0/0
Target: Internet Gateway
```

4. Associate route table with public subnet

---

# 🖥️ Step 5: Launch EC2 in Custom VPC

When launching EC2:

- Select VPC: devops-vpc
- Subnet: public-subnet
- Auto-assign public IP: enabled
- Security group:
  - SSH (22)
  - HTTP (80)

---

# 🔑 Step 6: Connect via SSH

```bash
ssh -i key.pem ubuntu@public-ip
```

---

# 🌐 Step 7: Test Internet Access

Inside EC2:

```bash
ping google.com
```

Install Nginx:

```bash
sudo apt update
sudo apt install nginx -y
```

Open browser:

```
http://public-ip
```

---

# 🧠 What You Learned

- How AWS networking is structured
- What a VPC actually does
- How subnets control access
- How routing enables internet connectivity
- How EC2 depends on networking configuration

---

# 🔐 Key Concepts

| Component | Purpose |
|-----------|--------|
| VPC | Virtual network |
| Subnet | Network segment |
| Internet Gateway | Internet access |
| Route Table | Traffic rules |
| Security Group | Firewall |

---

# 🚨 Common Issues

## No internet access
- Missing route to Internet Gateway

## Cannot SSH
- Security group missing port 22

## Website not loading
- HTTP (80) not open
- Wrong subnet configuration

---

# 📌 Real-World DevOps Use Case

Production systems use:

- Private subnets for databases
- Public subnets for web servers
- Strict routing rules for security
- Multi-AZ VPC designs for reliability

---

# 🚀 Future Upgrades

This lab will later evolve into:

- Multi-tier architecture (frontend/backend/database)
- NAT Gateway setup
- Private subnet architecture
- High availability design
- VPC peering between environments

---

# 🧭 Status

✔ Custom VPC created  
✔ Subnets configured  
✔ Internet gateway attached  
✔ EC2 deployed in custom network  
✔ Networking fundamentals understood  
