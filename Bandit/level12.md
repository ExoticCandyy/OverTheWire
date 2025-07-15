# Bandit Level 12

## 🧩 Objective

> The goal of this level is to find the password which is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

---

## 🧪 Credentials

- **Host**: `bandit11.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```
3. There is a file named data.txt which the pass is rotated by 13. we will use `tr` command to do the job.
```
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```
---
[← Level 11](./level11.md) | [Level 13 →](./level13.md)
