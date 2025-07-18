# Bandit Level 26

## 🧩 Objective

> Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

NOTE: if you’re a Windows user and typically use Powershell to ssh into bandit: Powershell is known to cause issues with the intended solution to this level. You should use command prompt instead.
---

## 🧪 Credentials

- **Host**: `bandit25.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `iCi86ttT4KSNe1armKiwbQNmB3YJP3q4`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit25@bandit.labs.overthewire.org -p 2220
```
3. i type `ls` to show me what we have here. There is a `` here we can use it login to `bandit26`. but it fails.
```
bandit25@bandit:~$ ssh -i bandit26.sshkey bandit26@localhost -p 2220
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
.
.
.
Connection to localhost closed.
```
4. let's check the shell being used by users. here we head to `/etc/passwd` this is where this info is being stored. we see it uses `showtext` shell. let's see the coding of this shel.
```
bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
```
5. here we have `more` command. `more` shows text one page at a time in the terminal when reading big files when you minimize the window while using it it shows a percentage to indicate how much of the file you have viewed. when the percentage hits 100 this line is completed then goes to the next line which is `exit0`, this part is the cause of our logging out. so what do we do? we will minimize the windows to stop it from executing `exit 0`, it sounds kinda nuts but that's how it is.
```
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
```
6.it'll look something like this. `more` has some interactive like commands like `v`, `:n`, `:p` and etc. which we will use `v`. `v`, `vi`, `vim` almost the same thing. and as you know we can execute commands through `v`. we can change our shell.
```
  _                     _ _ _  
 ___   __  
 | |                   | (_) | 
|__ \ / /  
 | |__   __ _ _ __   __| |_| |_
   ) / /_  
 | '_ \ / _` | '_ \ / _` | | __
--More--(62%)
```
7. press `v` on your keyboard then you'll go into an editor. type `:set shell=/bin/bash` the shell will change from `showtext` to `bash`. then type `:set shell?` to make sure it's changed. then type `:shell`. now we're in `bandit27`.
```
:set shell=/bin/bash
:set shell?
shell=/bin/bash                                                                                           2,2           All
:shell
bandit26@bandit:~$ ls
bandit27-do  text.txt
```
---
[← Level 25](./leve25.md) | [Level 27→](./level27.md)
