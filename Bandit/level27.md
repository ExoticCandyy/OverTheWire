# Bandit Level 27

## 🧩 Objective

> Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

NOTE: if you’re a Windows user and typically use Powershell to ssh into bandit: Powershell is known to cause issues with the intended solution to this level. You should use command prompt instead.
---

## 🧪 Credentials

- **Host**: `bandit26.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `you need to loggin here from previous level`
---

## 🖥️ Steps

1. Open your terminal.
2. there are two files. the `text.txt` is useless it just shows a banner. `bandit27-do` file is a setuid ELF file which means it has special permissions that allow it to be executed with the privileges of its owner, we have seen this previous levels.
```
bandit26@bandit:~$ ls
bandit27-do  text.txt
```
4. we can use this command to check the next level's password.
```
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```
---
[← Level 26](./leve26.md) | [Level 28→](./level28.md)
