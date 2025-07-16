# Bandit Level 23

## 🧩 Objective

> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

---

## 🧪 Credentials

- **Host**: `bandit22.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit22@bandit.labs.overthewire.org -p 2220
```
3. now we go for `/etc/cron.d/`. it's basically the same as lvl22. now what does this script do? this script creates a filename using `echo I am user $myname | md5sum | cut -d ' ' -f 1` which `$myname` can be bandit1, bandit2, ... . then it goes for the passwords at `/etc/bandit_pass/` and copies it to the file created in `/tmp`.
```
bandit22@bandit:~$ cd /etc/cron.d/
bandit22@bandit:/etc/cron.d$ ls
clean_tmp         cronjob_bandit23  e2scrub_all  sysstat
cronjob_bandit22  cronjob_bandit24  otw-tmp-dir
bandit22@bandit:/etc/cron.d$ cat cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
```
4. if i run this command it'll give me the filename which has the pass of this lvl.
```
bandit22@bandit:/etc/cron.d$ echo "I am user bandit23" | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
```
5. now i run this command and it'll give me the pass.
```
bandit22@bandit:/etc/cron.d$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```
---
[← Level 22](./leve22.md) | [Level 24→](./level24.md)
