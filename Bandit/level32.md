# Bandit Level 32

## 🧩 Objective

> There is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.

Clone the repository and find the password for the next level.

---

## 🧪 Credentials

- **Host**: `bandit31.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit31@bandit.labs.overthewire.org -p 2220
```
3. we clone the branch same as the previous lvl
```
bandit31@bandit:~$ mkdir /tmp/mylvl31
bandit31@bandit:~$ cd /tmp/mylvl31
bandit31@bandit:/tmp/mylvl30$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
```
4. let's check the `READ.md` file. as you see it asks us to push the `key.txt` file with the following content.
```
bandit31@bandit:/tmp/mylvl31$ cd repo/
bandit31@bandit:/tmp/mylvl31/repo$ cat README.md 
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
```
5. ok we wrote the `key.txt` file. let's check the `.gitignore`. we see it forbids all `.txt` files from being pushed into the remote repository so let's remove that.
```
bandit31@bandit:/tmp/mylvl31/repo$ echo "May I come in?" > key.txt
bandit31@bandit:/tmp/mylvl31/repo$ cat key.txt 
May I come in?
bandit31@bandit:/tmp/mylvl31/repo$ ls -a
.  ..  .git  .gitignore  key.txt  README.md
bandit31@bandit:/tmp/mylvl31/repo$ cat .gitignore 
*.txt
bandit31@bandit:/tmp/mylvl31/repo$ rm .gitignore 
bandit31@bandit:/tmp/mylvl31/repo$ ls -a
.  ..  .git  key.txt  README.md
```
6. now we `add` the `key.txt` to the next commit change and then we `commit` the changes and it enters the changes to the existing branch. after that we `push` and send this to the remote repositiory then it gives us the password.
```
bandit31@bandit:/tmp/mylvl31/repo$ git add key.txt 
bandit31@bandit:/tmp/mylvl31/repo$ git commit -m "upload key.txt"
[master f972c6f] upload key.txt
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/mylvl31/repo$ git push -u origin master 
.
.
remote: Well done! Here is the password for the next level:
remote: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K 
.
.
```
---
[← Level 31](./leve31.md) | [Level 33→](./level33.md)
