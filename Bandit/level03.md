# Bandit Level 3

## 🧩 Objective

> The goal of this level is to find the password which is stored in a file which the filename has spaces init.

---

## 🧪 Credentials

- **Host**: `bandit0.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```
3. run ls:
```bash
ls
```
4. There is a file named "spaces in this filename". Linux recommends us not to use spaces in naming... . if filename has sapace init we just put it in double quote.
```bash
cat "spaces in this filename"
```
5. The pass is:
```bash
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```
---
[← Level 02](./level02.md) | [Level 04 →](./level04.md)
