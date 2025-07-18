# Bandit Level 29

## 🧩 Objective

> There is a git repository at ssh://bandit28-git@localhost/home/bandit28-git/repo via the port 2220. The password for the user bandit28-git is the same as for the user bandit28.

Clone the repository and find the password for the next level.

---

## 🧪 Credentials

- **Host**: `bandit28.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit28@bandit.labs.overthewire.org -p 2220
```
3. let's clone the git branch it's same as the previous lvl.
```
bandit28@bandit:~$ cd /tmp/mylvl28
bandit28@bandit:/tmp/mylvl28$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
.
.
.
```
4. as you see in the `README.md` the pass has been censored. one thing we can do is to go and check the previous versions something might come up.
```
bandit28@bandit:/tmp/mylvl28$ cd repo
bandit28@bandit:/tmp/mylvl28/repo$ ls
README.md
bandit28@bandit:/tmp/mylvl28/repo$ cat README.md 
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx
```
5. i used `git log` to see the log and the commit hashes. i'll use it in the `git checkout` command to go to previous versions. as you see in the second commit it says `add missing data` let's check.
```
bandit28@bandit:/tmp/mylvl28/repo$ git log
commit 674690a00a0056ab96048f7317b9ec20c057c06b (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Apr 10 14:23:19 2025 +0000

    fix info leak

commit fb0df1358b1ff146f581651a84bae622353a71c0
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Apr 10 14:23:19 2025 +0000

    add missing data

commit a5fdc97aae2c6f0e6c1e722877a100f24bcaaa46
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Apr 10 14:23:19 2025 +0000

    initial commit of README.md

```
6. here it is we got the password.
```
bandit28@bandit:/tmp/mylvl28/repo$ git checkout fb0df1358b1ff146f581651a84bae622353a71c0
Previous HEAD position was 674690a fix info leak
HEAD is now at fb0df13 add missing data
bandit28@bandit:/tmp/mylvl28/repo$ cat README.md 
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```
---
[← Level 28](./leve28.md) | [Level 30→](./level30.md)
