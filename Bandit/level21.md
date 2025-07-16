# Bandit Level 21

## 🧩 Objective

> There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think


---

## 🧪 Credentials

- **Host**: `bandit20.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO`
---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
```
3. first we will craete a port which will echo the `bandit20` pass on that then we will run the setuid binary and then it will give the next level's pass.
4. here in the command `nc -lp 1234 &`, `l` tells netcat to listen for incoming connections, `-p` sets the port to listen on and the `&` runs the whole proccess in the background (here we just have one terminal. in normal cases you open one shell to listen and open another shell to do other things). the `jobs` command shows the whole commands that are running in the background.
```
bandit20@bandit:~$ echo "0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO" | nc -lp 1234 &
[1] 861847
bandit20@bandit:~$ jobs
[1]+  Running                 echo "0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO" | nc -lp 1234 &
```
5. we run the `./suconnect 1234` command and it gives the pass.
```
bandit20@bandit:~$ ./suconnect 1234
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Password matches, sending next password
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
[1]+  Done                    echo "0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO" | nc -lp 1234
```
---
[← Level 20](./leve20.md) | [Level 22→](./level22.md)
