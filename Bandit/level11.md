# Bandit Level 11

## 🧩 Objective

> The goal of this level is to find the password which is stored in the file data.txt, which contains base64 encoded data

---

## 🧪 Credentials

- **Host**: `bandit10.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```
3. we used the command below. "base64 -d" decodes the file.
```
bandit10@bandit:~$ base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
---
[← Level 10](./level10.md) | [Level 12 →](./level12.md)
