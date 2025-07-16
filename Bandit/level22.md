# Bandit Level 22

## 🧩 Objective

> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

---

## 🧪 Credentials

- **Host**: `bandit21.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `EeoULMCra2q0dSkYj561DX7s1CpBuOBt`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220
```
3. first i go for the `/etc/cron.d/` dir. we see there is a file named `cronjob_bandit22`. i use `cat` to see it's info. it's reffering to `/usr/bin/cronjob_bandit22.sh1` so we'll take a look on that.
```
bandit21@bandit:~$ cd /etc/cron.d/
bandit21@bandit:/etc/cron.d$ ls
clean_tmp         cronjob_bandit23  e2scrub_all  sysstat
cronjob_bandit22  cronjob_bandit24  otw-tmp-dir
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
```
4. i use `cat` to see what's the script. so what does this script do? it copies the pass into a file named `t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` in the `tmp` dir. we have the permission to check that file in temp and there's the password.
```
bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:/etc/cron.d$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```
---
[← Level 21](./leve21.md) | [Level 23→](./level23.md)
