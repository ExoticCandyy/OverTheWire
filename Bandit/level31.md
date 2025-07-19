# Bandit Level 31

## 🧩 Objective

> There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.

Clone the repository and find the password for the next level.

---

## 🧪 Credentials

- **Host**: `bandit30.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit30@bandit.labs.overthewire.org -p 2220
```
3. we clone the branch same as the previous lvl
```
bandit30@bandit:~$ mkdir /tmp/mylvl30
bandit30@bandit:~$ cd /tmp/mylvl30
bandit30@bandit:/tmp/mylvl30$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
```
4. well funny lil guys. there's no pass. i have checked the commits and branches there's still nothing.
```
bandit30@bandit:/tmp/mylvl30$ cd repo
bandit30@bandit:/tmp/mylvl30/repo$ ls
README.md
bandit30@bandit:/tmp/mylvl30/repo$ cat README.md 
just an epmty file... muahaha
```
5. we go for `git tag`. so what's tag? a `tag` is like a label you stick on a specific commit or in other words we mark important points in our project's history. i used `git tag` to show me the existing tags and then `git show` to show the content of the tag.
```
bandit30@bandit:/tmp/mylvl30/repo$ git tag
secret
bandit30@bandit:/tmp/mylvl30/repo$ git tag secret
fatal: tag 'secret' already exists
bandit30@bandit:/tmp/mylvl30/repo$ git show secret 
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```
---
[← Level 30](./leve30.md) | [Level 32→](./level32.md)
