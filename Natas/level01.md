# Natas Level 1

## 🧪 Credentials

- **URL**: `http://natas1.natas.labs.overthewire.org`
- **Username**: `natas1`
- **Password**: `0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq `

---

## 🖥️ Steps

1. Login to the website.
2. it says `You can find the password for the next level on this page, but rightclicking has been blocked! ` so again there is something in the source code. the problem is how we get there?
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
<script>var wechallinfo = { "level": "natas1", "pass": "0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq" };</script></head>
<body oncontextmenu="javascript:alert('right clicking has been blocked!');return false;">
<h1>natas1</h1>
<div id="content">
You can find the password for the
next level on this page, but rightclicking has been blocked!

<!--The password for natas2 is TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI -->
</div>

<div id="wechallform" style="display: block;" class="ui-draggable">
<p>Submit token</p><form id="realwechallform" action="https://www.wechall.net/10-levels-on-Natas.html" enctype="application/x-www-form-urlencoded" method="post"><input type="hidden" name="wfid" value="2">
<input type="hidden" name="password_solution" value="0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq">
<input type="hidden" name="igotitnow" value="Register">
</form>
</div>
</body>
</html>
```
4. As you see we have found the pass:
```
<!--The password for natas2 is TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI -->
```
---
[← Level 00](./level00.md) | [Level 02 →](./level02.md)
