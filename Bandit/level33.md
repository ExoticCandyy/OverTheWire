# Bandit Level 33

## 🧩 Objective

> After all this git stuff, it’s time for another escape. Good luck!


---

## 🧪 Credentials

- **Host**: `bandit32.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit32@bandit.labs.overthewire.org -p 2220
```
3. as you see we have an unusuall shell named `UPPERCASE SHELL`. after typing some commands we understand that it's basically a custom shell that uses `/bin/sh` and changes the letters to uppercase.
```
WELCOME TO THE UPPERCASE SHELL
>> ls
sh: 1: LS: Permission denied
>> cd
sh: 1: CD: Permission denied
>> 
```
4. to get out of this shell and go for the `sh` shell we type `$0` this spawns a new shell. now we can run commands. we can easily get the pass through the `/etc/bandit_pass/` dir.
```
$ pwd
/home/bandit32
$ cat /etc/bandit_pass/bandit33
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
```
---
[← Level 32](./leve32.md) | [Level 34→](./level34.md)
