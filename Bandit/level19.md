# Bandit Level 19

## 🧩 Objective

> The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.



---

## 🧪 Credentials

- **Host**: `bandit18.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220
```
3. after trying to login we get this. when we use the `ssh bandit18@bandit.labs.overthewire.org -p 2220
` command it uses `/bin/bash` as default to connect. we know that someone messed with `.bashrc` so i will use different shell.
```
.
.
.
Byebye !
Connection to bandit.labs.overthewire.org closed.
```
4. if you want to know what sheel you have just type:
```
─[phantom@parrot]─[~]
└──╼ $cat /etc/shells
# /etc/shells: valid login shells
/bin/sh
/usr/bin/sh
/bin/bash
/usr/bin/bash
/bin/rbash
/usr/bin/rbash
/bin/dash
/usr/bin/dash
/usr/bin/tmux
/usr/bin/screen
```
5. i'll use `/bin/sh`. as you see it worked.
```
└──╼ $ssh bandit18@bandit.labs.overthewire.org -p 2220 -t "/bin/sh"
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 
$ 
$ ls
readme
$ cat readme
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```
---
[← Level 18](./level18.md) | [Level 20→](./level20.md)
