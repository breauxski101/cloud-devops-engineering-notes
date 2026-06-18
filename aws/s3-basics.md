# Amazon S3 Basics (Storage in AWS)

Amazon S3 (Simple Storage Service) is an object storage service used to store and retrieve data in the cloud.

---

# 1. What is S3?

S3 is used to store files such as:
- Images
- Videos
- Backups
- Website files
- Logs

It is highly durable and scalable.

---

# 2. Why S3 is Important in DevOps

DevOps engineers use S3 for:
- Storing application assets
- Hosting static websites
- Backups and disaster recovery
- CI/CD artifacts

---

# 3. Core Concepts

## Bucket
A container for storing objects.

Example:
- my-app-bucket
- devops-backups

---

## Object
A file stored in a bucket.

Example:
- image.png
- index.html
- logs.txt

---

## Key
The unique path to an object.

Example:
```
folder/file.txt
```

---

# 4. S3 Features

- Highly scalable storage
- Pay only for what you use
- Secure access control
- Versioning support
- Static website hosting

---

# 5. S3 Storage Classes

- Standard → frequently accessed data
- Infrequent Access → rarely used data
- Glacier → long-term archival storage

---

# 6. Basic S3 Actions

## Create Bucket
Done via AWS Console

## Upload File
Add files to bucket

## Delete File
Remove objects when no longer needed

---

# 7. S3 Permissions (Important)

Access is controlled using:
- IAM policies
- Bucket policies

By default:
- Buckets are private

---

# 8. Static Website Hosting (VERY IMPORTANT)

S3 can host websites like:

- HTML
- CSS
- JavaScript

Steps:
1. Upload website files
2. Enable static website hosting
3. Set index.html as entry point

---

# 9. Real-World DevOps Use Case

A company hosts a frontend app:

- React build files uploaded to S3
- CloudFront distributes content globally
- Route 53 handles domain name

---

# 10. Common Issues

## Access denied
- IAM permissions missing

## Website not loading
- Static hosting not enabled
- Missing index.html

---

# 11. Mini Lab (DO LATER)

1. Create S3 bucket
2. Upload a file
3. Make it public (temporarily for learning)
4. Enable static website hosting
5. Access file via URL

---

# 12. What to Add Later

After hands-on AWS practice:

- S3 + CloudFront integration
- Secure private buckets
- IAM roles for S3 access
- Backup strategies using S3
