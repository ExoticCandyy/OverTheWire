# Bandit Level 16

## 🧩 Objective

> The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

---

## 🧪 Credentials

- **Host**: `bandit15.labs.overthewire.org`
- **Port**: `2220`
- **Password**: `8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo`

---

## 🖥️ Steps

1. Open your terminal.
2. Connect to the Bandit server via SSH:

```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
```
3. we use the `openssl` command to do the job. then if asks for  the pass we give the previous pass that we've found.
```
bandit15@bandit:~$ openssl s_client -connect localhost:30001
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 6018B1DD41B3F2F95A63BD843AE3D542BEBCEC7E955CCF45D9762A1B10D5F653
    Session-ID-ctx: 
    Resumption PSK: 8541B4E5727B93C9DD38FC9F97A8F37AEE9058269B97910AB8E81C9FFA99BB868E55A16411151289E1EF0DD6CF8D60A5
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 1a 66 25 0d 10 cc f3 2a-f4 0c 83 03 99 cf 9a 7f   .f%....*........
    0010 - 67 94 b0 4c 9e fa a7 b3-a6 d1 1f 33 4e e4 fc 6c   g..L.......3N..l
    0020 - 41 b3 4f 47 cf f6 9a 15-04 fe fe 91 58 5c c6 11   A.OG........X\..
    0030 - eb c8 1a 62 c0 cb f4 db-bb 52 c0 15 6a d2 2f 56   ...b.....R..j./V
    0040 - 72 e7 33 ec a2 2a cc 9c-79 59 88 37 3c f3 c2 2f   r.3..*..yY.7<../
    0050 - ed 15 1d b7 7d 4c 0e 16-cf 8a cb 46 e2 54 1a 65   ....}L.....F.T.e
    0060 - dc 2b 82 87 c9 1b 92 a2-21 ec 42 22 0d e7 49 69   .+......!.B"..Ii
    0070 - 02 09 0e d4 06 df b5 8d-1e 1c b8 e0 cb 19 65 ed   ..............e.
    0080 - bb 24 d3 6e 89 f1 55 f0-1f a3 33 07 3d 1a 97 bf   .$.n..U...3.=...
    0090 - 10 9e e6 09 da b6 31 4a-e4 26 e8 f4 fc 1a fd 6f   ......1J.&.....o
    00a0 - a2 45 c2 85 a4 ea 1e f1-b4 ed c0 17 db f8 e8 2a   .E.............*
    00b0 - a7 48 f7 b0 8c b6 fd b9-88 be ce bf 1a a7 08 2f   .H............./
    00c0 - 8d 1a 45 fb 4c 81 d8 e8-fc c1 72 c2 2a 33 9d e2   ..E.L.....r.*3..
    00d0 - 25 2f c5 73 05 16 2b 0e-e7 52 b5 38 d0 61 65 dc   %/.s..+..R.8.ae.

    Start Time: 1752587798
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

closed

```
---
[← Level 15](./level15.md) | [Level 17 →](./level17.md)
