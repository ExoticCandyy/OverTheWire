# Bandit Level 6

## 🧩 Objective

> The goal of this level is to find the password which is stored in a file somewhere under the inhere directory and has all of the following properties:
  1.human-readable
  2.1033 bytes in size
  3.not executable


---

## 🧪 Credentials

- **Host**: `bandit5.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```
3. run ls:
```bash
ls
```
4. There is a directory named inhere:
```bash
cd inhere
```
5. we run ls which shows multiple directories.
```
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
maybehere03  maybehere07  maybehere11  maybehere15  maybehere19
```
6. now we want to work smart. we use the comand below. "." means search in this directory. "-type f" means it's a file. "-size 1033c" means it's 1033 bytes. "-not -executable" finds the nonexecutable files.
```
bandit5@bandit:~/inhere$ find . -type f -size 1033c -not -executable
./maybehere07/.file2
```
7. and the pass is:
```
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```
---
[← Level 05](./level05.md) | [Level 07 →](./level07.md)
