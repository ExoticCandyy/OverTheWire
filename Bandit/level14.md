# Bandit Level 14

## 🧩 Objective

> The goal of this level is to find the password which is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

---

## 🧪 Credentials

- **Host**: `bandit13.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```
3. There is a ssh key so we will use it to connect to the bandit14. If you ask why `localhost` because we already have connected to bandit13 and bandit14 is on the same host.
```
bandit13@bandit:~$ ssh -i sshkey.private -p 2220 bandit14@localhost
```
4. after connecting to bandit14 we go to after the specified file to get the pass.
```
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```
---
[← Level 13](./level13.md) | [Level 15 →](./level15.md)
