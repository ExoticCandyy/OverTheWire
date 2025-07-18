# Bandit Level 24

## 🧩 Objective

> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

---

## 🧪 Credentials

- **Host**: `bandit23.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `0Zf11ioIjMVN551jX3CmStKLYqjk54Ga`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit23@bandit.labs.overthewire.org -p 2220
```
3. first we'll head to the `/etc/cron.d/` dir and check the existing script. so what does this script do? we will write a script in the `/var/spool/bandit24/foo` dir then this script will run it and delete it within 1 minute.
```
bandit23@bandit:/var/spool/bandit24/foo$ cd /etc/cron.d
bandit23@bandit:/etc/cron.d$ ls
clean_tmp         cronjob_bandit23  e2scrub_all  sysstat
cronjob_bandit22  cronjob_bandit24  otw-tmp-dir
bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done
```
4. let's write the script it's simple. i typically use `vim` but to make easy to show here i wrote it using like this. it's simplle when executed it copies the pass to the `/tmp/outputtt.txt`. and the `chmod 777` gives all the read, write and execution permissions to the script.
```
bandit23@bandit:/var/spool/bandit24/foo$ echo "cat /etc/bandit_pass/bandit24 > /tmp/outputtt.txt" > scripttt.sh
bandit23@bandit:/var/spool/bandit24/foo$ chmod 777 scripttt.sh
```
5. if we check out the `/tmp/outputtt.txt` we'll see
```bandit23@bandit:/var/spool/bandit24/foo$ cat /tmp/outputtt.txt
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
```
---
[← Level 23](./leve23.md) | [Level 25→](./level25.md)
