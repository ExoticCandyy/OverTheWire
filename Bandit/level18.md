# Bandit Level 18

## 🧩 Objective

> There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19



---

## 🧪 Credentials

- **Host**: `bandit17.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `EReVavePLFHtFlFsjn3hyzMlvSuSAcRD`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit17@bandit.labs.overthewire.org -p 2220
```
3. we will use the `diff` command to find the differences. the `<` represents the lines that have been removed and the `>` sign represents the lines that have been added in its place.
```
bandit17@bandit:~$ diff passwords.new passwords.old 
42c42
< x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
---
> C6XNBdYOkgt5ARXESMKWWOUwBeaIQZ0Y
```
4. i test the `x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`. i get the `Byebye` which means we did it (read the NOTE above).
```
.
.
.
Byebye !
Connection to bandit.labs.overthewire.org closed.
```
---
[← Level 17](./level17.md) | [Level 19→](./level19.md)
