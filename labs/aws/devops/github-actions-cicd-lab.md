# GitHub Actions CI/CD Pipeline Lab

This project demonstrates a basic CI/CD pipeline using GitHub Actions.

---

# 🎯 Objective

- Understand CI/CD concepts
- Automate build and test process
- Learn how deployments are triggered automatically
- Use GitHub Actions for workflow automation

---

# 🧠 What is CI/CD?

## Continuous Integration (CI)
Automatically:
- Builds code
- Runs tests
- Validates changes

## Continuous Deployment (CD)
Automatically:
- Deploys code after successful CI

---

# 🧱 Technologies Used

- GitHub Actions
- GitHub Repository
- Docker (optional later)
- Linux commands

---

# 📁 Step 1: Create Workflow Folder

In your repo:

```
.github/workflows/
```

---

# ⚙️ Step 2: Create Workflow File

Create:

```
.github/workflows/ci-cd.yml
```

---

# 🧾 Step 3: Add CI Pipeline

```yaml
name: CI Pipeline

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Run simple script
        run: echo "Building project successfully 🚀"
```

---

# ▶️ Step 4: Trigger Pipeline

Push changes to GitHub:

```bash
git add .
git commit -m "Add CI pipeline"
git push origin main
```

Go to:
- GitHub → Actions tab

You should see pipeline running.

---

# 🧠 What You Learned

- How CI/CD pipelines work
- How automation replaces manual processes
- How GitHub Actions runs workflows
- How DevOps engineers ship code automatically

---

# 📌 Real-World DevOps Use Case

In real companies:

1. Developer pushes code
2. CI pipeline runs tests
3. Docker image is built
4. CD pipeline deploys to cloud
5. Monitoring tracks performance

---

# 🔄 How this evolves later

This simple pipeline will later expand into:

- Running unit tests
- Building Docker images
- Pushing images to Docker Hub / ECR
- Deploying to EC2 or Kubernetes
- Production-grade workflows

---

# 🚨 Common Issues

## Workflow not running
- File not in `.github/workflows/`
- Wrong YAML syntax

## No trigger
- Wrong branch name

## Permission errors
- GitHub Actions not enabled

---

# 🧭 Status

✔ First CI pipeline created  
✔ GitHub Actions triggered  
✔ Automation concept understood  
