# Bandit Level 4

## 🧩 Objective

> The goal of this level is to find the password which is stored in a hidden file in the inhere directory.

---

## 🧪 Credentials

- **Host**: `bandit3.labs.overthewire.org`
- **Port**: `2220`
- **Username**: `bandit3`
- **Password**: `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```
3. run ls -a. This searches for all files including hidden ones:
```bash
ls -a
```
4. There is a directory named inhere:
```bash
cd inhere
```
5. we run ls -a which shows the "...Hiding-From-You" file.
```bash
cat ...Hiding-From-You
```
6. The pass is:
```bash
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```
---
[← Level 05](./level05.md) | [Level 06 →](./level06.md)
