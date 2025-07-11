# Bandit Level 5

## 🧩 Objective

> The goal of this level is to find the password which is stored in the only human-readable file in the inhere directory.

---

## 🧪 Credentials

- **Host**: `bandit4.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```
3. run ls:
```bash
ls
```
4. There is a directory named inhere:
```bash
cd inhere
```
5. we run ls which shows multiple files (-file00, ... , -file09)
```
bandit4@bandit:~/inhere$ ls
-file00  -file02  -file04  -file06  -file08
-file01  -file03  -file05  -file07  -file09

```
6. Since we know that the file is human readable we use the file command. this shows us the encoding of each file. the ./* means do this for all the files in this directory.
```
bandit4@bandit:~/inhere$ file ./*
./-file00: PGP Secret Sub-key -
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
```
7. and the pass is:
```
bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```
---
[← Level 04](./level04.md) | [Level 06 →](./level06.md)
