# Natas Level 5

## 🧪 Credentials

- **URL**: `http://natas5.natas.labs.overthewire.org`
- **Username**: `natas5`
- **Password**: `0n35PkggAPm2zbEpOU802c0x0Msn1ToK`

---

## 🖥️ Steps

1. Login to the website.
2. it says `Access disallowed. You are not logged in`. well how can it be? it has to do something with the cookies.
3. go into `inspect elements > storage > cookies` there is a cookie named `loggedin` it's value is `0` change it to `1` and refresh the page
4. after refreshing the password is there:
```
 Access granted. The password for natas6 is 0RoJwHdSKWFTYR5WuiAewauSuNaBXned
```
---
[← Level 04](./level04.md) | [Level 06 →](./level06.md)
