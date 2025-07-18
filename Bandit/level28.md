# Bandit Level 28

## 🧩 Objective

> There is a git repository at ssh://bandit27-git@localhost/home/bandit27-git/repo via the port 2220. The password for the user bandit27-git is the same as for the user bandit27.

Clone the repository and find the password for the next level.
---

## 🧪 Credentials

- **Host**: `bandit27.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit27@bandit.labs.overthewire.org -p 2220
```
3. ok we head to the `/tmp` and craete a directory there. then we will clone the repo. i just added the port number to the localhost. then it'll ask for the pass, enter this level's pass.
```
bandit27@bandit:~$ mkdir /tmp/mylevel27
bandit27@bandit:~$ cd /tmp/mylevel27
bandit27@bandit:/tmp/mylevel27$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
.
.
.
```
4. and here is the pass:
```
bandit27@bandit:/tmp/mylevel27$ ls
repo
bandit27@bandit:/tmp/mylevel27$ cd repo
bandit27@bandit:/tmp/mylevel27/repo$ ls
README
bandit27@bandit:/tmp/mylevel27/repo$ cat README 
The password to the next level is: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
```
---
[← Level 27](./leve27.md) | [Level 29→](./level29.md)
