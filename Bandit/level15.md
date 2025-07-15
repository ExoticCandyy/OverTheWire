# Bandit Level 15

## 🧩 Objective

> The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

---

## 🧪 Credentials

- **Host**: `bandit14.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit14@bandit.labs.overthewire.org -p 2220
```
3. i know there is a service running on port 30000. we use nc or netcat to check. it asks for pass so we give the one we found from the previoes level.
```
bandit14@bandit:~$ netcat localhost 30000
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```
---
[← Level 14](./level14.md) | [Level 16 →](./level16.md)
