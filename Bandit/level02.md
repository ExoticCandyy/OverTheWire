# Bandit Level 2

## 🧩 Objective

> The goal of this level is to find the password which is stored in a file called -.

---

## 🧪 Credentials

- **Host**: `bandit1.labs.overthewire.org`
- **Port**: `2220`
- **Username**: `bandit1`
- **Password**: `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```
3. run ls:
```bash
ls
```
4. There is a file named -. We don't acctualy name files with special characters. In case you face this just type the path like this:
```bash
cat ./-
```
5. The pass is:
```bash
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```
---
[← Level 01](./level01.md) | [Level 03 →](./level03.md)
