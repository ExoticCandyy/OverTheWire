# Bandit Level 10

## 🧩 Objective

> The goal of this level is to find the password which is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

---

## 🧪 Credentials

- **Host**: `bandit9.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```
3. we used the command below. "cat" gets the data. "strings -e" gets the human readable characters. we know that pass starts with several "=" commands so we use grep.
```
bandit9@bandit:~$ cat data.txt | strings -e s | grep ===
========== the
========== password{k
=========== is
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```
---
[← Level 09](./level09.md) | [Level 11 →](./level11.md)
