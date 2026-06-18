# IAM User + Policy Lab (AWS Security Basics)

This lab demonstrates how AWS Identity and Access Management (IAM) controls access to cloud resources.

---

# 🎯 Objective

- Create an IAM user
- Assign permissions using policies
- Test access restrictions
- Understand least privilege principle

---

# 🧱 Technologies Used

- AWS IAM
- S3
- AWS Console

---

# 🧠 Concept Overview

IAM controls:
- Who can access AWS
- What they can access
- What actions they can perform

---

# 🔐 Step 1: Create IAM User

In AWS Console:

1. Go to IAM service
2. Click "Users"
3. Click "Create user"
4. Enter name (e.g. dev-user)
5. Select:
   - Provide user access to AWS Management Console (optional for lab)

---

# 📦 Step 2: Attach Permissions

Choose one:

## Option A (simple)
Attach policy directly:
- AmazonS3ReadOnlyAccess

## Option B (better practice)
Add user to group:
- Create group: S3-ReadOnly-Group
- Attach policy to group
- Add user to group

---

# 🪣 Step 3: Create S3 Bucket (for testing)

If not already created:
- Create S3 bucket
- Upload a test file

Example:
```
test-file.txt
```

---

# 👤 Step 4: Test IAM Permissions

Login as IAM user (not root)

Try:
- View S3 bucket → should work
- Upload file → should fail (if read-only policy applied)

---

# 🚫 Step 5: Verify Access Control

If everything is correct:

| Action | Result |
|-------|--------|
| List S3 buckets | Allowed |
| Download objects | Allowed |
| Upload objects | Denied |

---

# 🧠 What You Learned

- IAM users represent identities
- Policies define permissions
- Groups simplify management
- AWS enforces least privilege by default (if configured correctly)

---

# 🔐 Key Concept: Least Privilege

Users should ONLY have the permissions they need.

Example:
- Dev user → read-only access
- Admin → full access (limited users)

---

# 📌 Real-World DevOps Use Case

In production:

- Developers get limited access
- EC2 instances use IAM roles (not users)
- Access is tightly controlled for security

---

# ⚠️ Common Issues

## Access denied
- Missing policy
- Wrong user login
- Policy not attached correctly

## Cannot see S3 bucket
- Region mismatch
- Permission not granted

---

# 🚀 Future Upgrade (IMPORTANT)

Later this lab evolves into:

- IAM roles for EC2
- Cross-service permissions (EC2 → S3 access)
- CloudTrail auditing
- Advanced security policies

---

# 🧭 Status

✔ IAM user created  
✔ Policies applied  
✔ Permissions tested  
✔ Cloud security basics understood  
