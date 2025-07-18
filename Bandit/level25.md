# Bandit Level 25

## 🧩 Objective

> A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
You do not need to create new connections each time

---

## 🧪 Credentials

- **Host**: `bandit24.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit24@bandit.labs.overthewire.org -p 2220
```
3. let's write the command together. this simple command brute forces all the 4 numeric passcodes. The `|` symbol pipes the output into the localhost.

```
bandit24@bandit:~$ for i in {0000..9999}; do echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i"; done | nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Wrong! Please enter the correct current password and pincode. Try again.
.
.
.
Correct!
The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```
---
[← Level 24](./leve24.md) | [Level 26→](./level26.md)
