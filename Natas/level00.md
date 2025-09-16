# Natas Level 0

## 🧩 Objective

> In every level we'll get a hint and try to figure it out and crack it.

---

## 🧪 Credentials

- **URL**: `http://natas0.natas.labs.overthewire.org`
- **Username**: `natas0`
- **Password**: `natas0`

---

## 🖥️ Steps

1. Login to the website.
2. it says `You can find the password for the next level on this page.` so there has to be something in the source code.
3. Here is the source code:
```bash
<html><head>

<!-- This stuff in the header has nothing to do with the level --><link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css">
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src="http://natas.labs.overthewire.org/js/wechall-data.js"></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas0", "pass": "natas0" };</script></head>
<body>
<h1>natas0</h1>
<div id="content">
You can find the password for the next level on this page.

<!--The password for natas1 is 0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq -->
</div>
<div id="wechallform" style="display: block;" class="ui-draggable"><p>Submit token</p>
<form id="realwechallform" action="https://www.wechall.net/10-levels-on-Natas.html" enctype="application/x-www-form-urlencoded" method="post">
<input type="hidden" name="wfid" value="1"><input type="hidden" name="password_solution" value="natas0"><input type="hidden" name="igotitnow" value="Register">
</form>
</div>
</body>
</html>
```
4. As you see we have found the pass:
```
<!--The password for natas1 is 0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq -->
```
---
[Level 01 →](./level01.md)
