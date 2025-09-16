# Natas Level 2

## 🧪 Credentials

- **URL**: `http://natas2.natas.labs.overthewire.org`
- **Username**: `natas2`
- **Password**: `TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI`

---

## 🖥️ Steps

1. Login to the website.
2. it says `There is nothing on this page`. there is nothing here we'll check the source code.
3. press `Fn + F12`. Here is the source code:
```bash
<html><head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css">
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src="http://natas.labs.overthewire.org/js/wechall-data.js"></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas2", "pass": "TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI" };</script></head>
<body>
<h1>natas2</h1>
<div id="content">
There is nothing on this page
<img src="files/pixel.png">
</div>

<div id="wechallform" style="display: block;" class="ui-draggable"><p>Submit token</p><form id="realwechallform" action="https://www.wechall.net/10-levels-on-Natas.html" enctype="application/x-www-form-urlencoded" method="post">
<input type="hidden" name="wfid" value="3"><input type="hidden" name="password_solution" value="TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI">
<input type="hidden" name="igotitnow" value="Register">
</form>
</div>
</body>
</html>
```
4. after the `There is nothing on this page` there is a pixel image `<img src="files/pixel.png">`. it doesn't make sense that we put the pixel image here right? so we'll check the `/files` dir. search this:
```
http://natas2.natas.labs.overthewire.org/files/
```
5. there is a `pixel.png` and a `users.txt`. go for the `users.txt`. here is it's content:
```
# username:password
alice:BYNdCesZqW
bob:jw2ueICLvT
charlie:G5vCxkVV3m
natas3:3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH
eve:zo4mJWyNj2
mallory:9urtcpzBmH
```
6. here is the pass:
```
3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH
```
---
[← Level 01](./level01.md) | [Level 03 →](./level03.md)
