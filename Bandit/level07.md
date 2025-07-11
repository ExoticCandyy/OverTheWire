# Bandit Level 6

## 🧩 Objective

> The goal of this level is to find the password which is stored somewhere on the server and has all of the following properties:


---

## 🧪 Credentials

- **Host**: `bandit6.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```
3. we run the command below and search the whole server. "/" means search the whole server. "-type f" searches for files. "-user bandit7" searches for the files whiich owned by this user. "-group bandit6" searchs for the files which belongs to this group. "-size 33c" means the file size is 33 bytes. "2>/dev/null" this part is to get rid of the "Permission denied" errors.
```bash
bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
```
4. and the pass is:
```bash
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```
---
[← Level 06](./level06.md) | [Level 08 →](./level08.md)
