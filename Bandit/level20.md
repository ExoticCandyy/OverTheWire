# Bandit Level 20

## 🧩 Objective

> To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.



---

## 🧪 Credentials

- **Host**: `bandit19.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit19@bandit.labs.overthewire.org -p 2220
```
3. the `id` command shows the userId, groupID and the group memberships. so what does  this `bandit20-do` do? we can use this to execute commands in behalf of the user `bandit20`. here you can see we can execute commands and the IDs have been shown here.
```
bandit19@bandit:~$ id
uid=11019(bandit19) gid=11019(bandit19) groups=11019(bandit19)
bandit19@bandit:~$ ./bandit20-do 
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$ ./bandit20-do id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
```
4. here i can get the password of bandit20 in behalf of user bandit20. and as you know the passwords of these challenges are stored in the `/etc/bandit_pass` dir it's why we're reffering to it.
```
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```
---
[← Level 19](./level19.md) | [Level 21→](./level21.md)
