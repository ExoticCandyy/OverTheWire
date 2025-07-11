# Bandit Level 8

## 🧩 Objective

> The goal of this level is to find the password which is stored in the file data.txt next to the word millionth.

---

## 🧪 Credentials

- **Host**: `bandit7.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```
3. we use grep to get the pass:
```
bandit7@bandit:~$ grep millionth data.txt
millionth	dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
---
[← Level 07](./level07.md) | [Level 09 →](./level09.md)
