# Bandit Level 13

## 🧩 Objective

> The goal of this level is to find the password which is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

---

## 🧪 Credentials

- **Host**: `bandit12.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```
3. first we will make a directory in `tmp`.
```
bandit12@bandit:~$ mkdir /tmp/zeuss
```
4. then i will copy the data.txt to this dir
```
bandit12@bandit:/tmp/zeuss$ cp ~/data.txt .
```
5. i will use `xxd` to decomposition.
```
bandit12@bandit:/tmp/zeuss$ xxd -r data.txt > output
```
6. the data is not clear so i'll use `file` command to know which data have been stored there which is `gzip`.
7. We can see that the file was compressed using qzip so we can decompress the data using the `gunzip` command.
```
bandit12@bandit:/tmp/zeuss$ mv output output.gz
bandit12@bandit:/tmp/zeuss$ gunzip output.gz
bandit12@bandit:/tmp/zeuss$ ls
data.txt  output  output.txt
```
8. here i use the `file` command and see that the data have been composed using `bzip2` so we need another decomposition.
```
bandit12@bandit:/tmp/zeuss$ bzip2 -d output
bzip2: Can't guess original name for output -- using output.out
```
9. i use file command and it says the data is still composed using gzip.
```
bandit12@bandit:/tmp/zeuss$ file output.out
output.out: gzip compressed data, was "data4.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32 20480
```
10. here we go the same step as 7.
```
bandit12@bandit:/tmp/zeuss$ mv output.out output.gz
bandit12@bandit:/tmp/zeuss$ gzip -d output.gz
bandit12@bandit:/tmp/zeuss$ ls
data.txt  output  output.txt
```
11. i use `file` command and says it's `tar`.
```
bandit12@bandit:/tmp/zeuss$ file output
output: POSIX tar archive (GNU)
```
12. we use `tar` command to decompose.
```
bandit12@bandit:/tmp/zeuss$ tar -xf output
bandit12@bandit:/tmp/zeuss$ ls
data5.bin  data.txt  output  output.txt
```
13. the steps are same decompose check the data using `file` until you get the ASCII text.
```
bandit12@bandit:/tmp/zeuss$ file output
output: POSIX tar archive (GNU)
bandit12@bandit:/tmp/zeuss$ tar -xf output
bandit12@bandit:/tmp/zeuss$ ls
data5.bin  data.txt  output  output.txt
bandit12@bandit:/tmp/zeuss$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/zeuss$ tar -xf data5.bin
bandit12@bandit:/tmp/zeuss$ ls
data5.bin  data6.bin  data.txt  output  output.txt
bandit12@bandit:/tmp/zeuss$ tar -xf data6.bin
bandit12@bandit:/tmp/zeuss$ ls
data5.bin  data8.bin  output
data6.bin  data.txt   output.txt
bandit12@bandit:/tmp/zeuss$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/zeuss$ mv data8.bin data8.gz
bandit12@bandit:/tmp/zeuss$ gzip -d data8.gz
bandit12@bandit:/tmp/zeuss$ ls
data5.bin  data6.bin  data8  data.txt  output  output.txt
bandit12@bandit:/tmp/zeuss$ file data8
data8: ASCII text
bandit12@bandit:/tmp/zeuss$ cat data8
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```
---
[← Level 12](./level12.md) | [Level 14 →](./level14.md)
