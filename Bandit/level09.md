# Bandit Level 9

## 🧩 Objective

> The goal of this level is to find the password which is stored in the file data.txt and is the only line of text that occurs only once.

---

## 🧪 Credentials

- **Host**: `bandit8.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```
3. "sort" just sorts it then we used a pipeline and the "uniq -u" search for a uniq phrase.
```
bandit8@bandit:~$ sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```
---
[← Level 08](./level08.md) | [Level 10 →](./level10.md)
