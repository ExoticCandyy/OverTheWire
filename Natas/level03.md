# Natas Level 3

## 🧪 Credentials

- **URL**: `http://natas3.natas.labs.overthewire.org`
- **Username**: `natas3`
- **Password**: `3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH`

---

## 🖥️ Steps

1. Login to the website.
2. it says `There is nothing on this page`. there is nothing here we'll check the source code.
3. press `Fn + F12`. Here is the source code:
```bash
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css">
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src="http://natas.labs.overthewire.org/js/wechall-data.js"></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas3", "pass": "3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH" };</script></head>
<body>
<h1>natas3</h1>
<div id="content">
There is nothing on this page
<!-- No more information leaks!! Not even Google will find it this time... -->
</div>

<div id="wechallform" style="display: block;" class="ui-draggable"><p>Submit token</p>
<form id="realwechallform" action="https://www.wechall.net/10-levels-on-Natas.html" enctype="application/x-www-form-urlencoded" method="post"><input type="hidden" name="wfid" value="4">
<input type="hidden" name="password_solution" value="3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH">
<input type="hidden" name="igotitnow" value="Register">
</form>
</div>
</body>
</html>
```
4. `<!-- No more information leaks!! Not even Google will find it this time... -->`. not even google will find it? how google finds it? well google and other browsers use `crawlers` to find a website. and this level is referring us to the `robots.txt` file in a nutshell it tells the crawlers how to behave. search the `robots.txt`:
```
http://natas3.natas.labs.overthewire.org/robots.txt
```
5. you'll see this info. it says don't let crawlers to go into this directory. let's go into it.

```
User-agent: *
Disallow: /s3cr3t/
```
6. search `http://natas3.natas.labs.overthewire.org/s3cr3t/`. after going into this dir you'll see `users.txt` file, click on that and there is the password.
```
natas4:QryZXc2e0zahULdHrtHxzyYkj59kUxLQ
```
---
