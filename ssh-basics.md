# SSH Basics (Linux + Cloud DevOps Focus)

This file explains SSH (Secure Shell), which is the main way to remotely access Linux servers in cloud environments like AWS.

---

# 1. What is SSH?

SSH (Secure Shell) is a protocol used to securely connect to remote Linux machines over a network.

Instead of sitting in front of a server, you:
- Connect remotely
- Run commands
- Manage systems

---

# 2. Why SSH is Important in DevOps

In cloud environments (AWS, Azure, GCP):

- Servers are remote (EC2 instances)
- You NEVER access them physically
- SSH is the primary access method

Without SSH, you cannot:
- Configure servers
- Deploy applications
- Fix production issues

---

# 3. Basic SSH Command

```bash
ssh user@ip-address
```

Example:

```bash
ssh ubuntu@192.168.1.10
```

---

# 4. SSH Key Authentication (VERY IMPORTANT)

Instead of passwords, cloud systems use SSH keys.

## Key types:
- Private key (kept on your computer)
- Public key (placed on the server)

---

# 5. Generate SSH Key

```bash
ssh-keygen -t rsa -b 4096
```

This creates:
- Private key → ~/.ssh/id_rsa
- Public key → ~/.ssh/id_rsa.pub

---

# 6. Copy Key to Server

```bash
ssh-copy-id user@ip-address
```

Or manually add public key to:

```bash
~/.ssh/authorized_keys
```

---

# 7. Connect Using Key

```bash
ssh -i key.pem ubuntu@ip-address
```

---

# 8. File Permissions (IMPORTANT)

SSH keys must be secure:

```bash
chmod 400 key.pem
```

If permissions are wrong, SSH will fail.

---

# 9. Common SSH Issues

## Permission denied
- Wrong username
- Wrong key
- Incorrect permissions

## Connection timeout
- Security group not open (AWS issue)
- Firewall blocking port 22

## Host not reachable
- Wrong IP
- Instance stopped

---

# 10. Real-World DevOps Use Case

You launch an AWS EC2 instance and need to:

1. Connect to server:
```bash
ssh -i mykey.pem ubuntu@ec2-ip
```

2. Install software:
```bash
sudo apt update
sudo apt install nginx -y
```

3. Restart services:
```bash
sudo systemctl restart nginx
```

---

# 11. Security Groups (AWS Connection)

SSH requires port 22 to be open.

In AWS EC2:
- Inbound rule must allow:
  - Port: 22
  - Source: your IP

---

# 12. Mini Lab (DO LATER ON EC2)

1. Launch EC2 instance
2. Download key pair (.pem file)
3. Set permissions:
```bash
chmod 400 key.pem
```
4. Connect:
```bash
ssh -i key.pem ubuntu@public-ip
```

5. Run:
```bash
whoami
uname -a
```

---

# 13. What to Add Later (After AWS Practice)

After working with EC2:

- Troubleshooting SSH failures in real environments
- Bastion hosts
- SSH tunneling
- Multi-server access patterns
- Role-based server access

---

# 14. Why This Matters

SSH is the **entry point to cloud infrastructure**.

If you understand SSH well, you can:
- Manage EC2 instances
- Debug production servers
- Deploy applications manually
- Understand cloud security basics
