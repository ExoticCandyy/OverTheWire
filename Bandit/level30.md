# Bandit Level 30

## 🧩 Objective

> There is a git repository at ssh://bandit29-git@localhost/home/bandit29-git/repo via the port 2220. The password for the user bandit29-git is the same as for the user bandit29.

Clone the repository and find the password for the next level.

---

## 🧪 Credentials

- **Host**: `bandit29.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit29@bandit.labs.overthewire.org -p 2220
```
3. we clone the branch same as the previous lvl
```
bandit29@bandit:~$ mkdir /tmp/mylvl29
bandit29@bandit:~$ cd /tmp/mylvl29
bandit29@bandit:/tmp/mylvl29$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
```
4. well there is no password. i have checked the previous versions still there isn't any pass.
```
bandit29@bandit:/tmp/mylvl29$ cd repo
bandit29@bandit:/tmp/mylvl29/repo$ ls
README.md
bandit29@bandit:/tmp/mylvl29/repo$ cat README.md 
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>
```
5. let's check the branches. there is a branch named `dev` let's check that first. and here it is the password we were looking for.
```
bandit29@bandit:/tmp/mylvl29/repo$ git branch -a
  _a
  master
* sploits-dev
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/mylvl29/repo$ git checkout dev 
branch 'dev' set up to track 'origin/dev'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/mylvl29/repo$ ls
code  README.md
bandit29@bandit:/tmp/mylvl29/repo$ cat README.md 
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```
---
[← Level 29](./leve29.md) | [Level 31→](./level31.md)
