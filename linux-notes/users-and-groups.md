# Users and Groups in Linux (DevOps Focus)

This file explains how Linux users and groups work from a system administration and cloud engineering perspective.

---

# 1. What is a User?

A user is an account that can log into and interact with a Linux system.

Types:
- Root user (admin, full access)
- Regular users
- System users (services like nginx, mysql)

---

# 2. What is a Group?

A group is a collection of users used to manage permissions.

Example:
- developers group
- sudo group
- docker group

---

# 3. Why This Matters in DevOps

In cloud environments (AWS, Linux servers):

- You never give everyone full access
- You assign permissions through users/groups
- Services run under specific system users

---

# 4. Commands

## Create a user

```bash
sudo useradd devuser
```

## Set password

```bash
sudo passwd devuser
```

## Create a group

```bash
sudo groupadd devops
```

## Add user to group

```bash
sudo usermod -aG devops devuser
```

## Check user info

```bash
id devuser
```

## Switch user

```bash
su - devuser
```

---

# 5. Permissions Context

Each user belongs to:
- a primary group
- optional secondary groups

Check with:

```bash
groups devuser
```

---

# 6. Real-World DevOps Use Case

In AWS EC2:

- You create a user for deployment
- You restrict root access
- You assign only required permissions

Example:
- `deploy` user can restart nginx
- but cannot modify system files

---

# 7. Mini Lab (YOU WILL DO THIS LATER)

1. Create a user:
```bash
sudo useradd testuser
```

2. Create a group:
```bash
sudo groupadd testers
```

3. Add user to group:
```bash
sudo usermod -aG testers testuser
```

4. Verify:
```bash
id testuser
```

---

# 8. What to Add Later (After AWS practice)

After you start EC2:

- How AWS handles users via IAM vs Linux users
- SSH access as a user
- Permission issues on EC2 instances
