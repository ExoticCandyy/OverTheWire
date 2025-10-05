# Natas Level 6

## 🧪 Credentials

- **URL**: `http://natas6.natas.labs.overthewire.org`
- **Username**: `natas6`
- **Password**: `0RoJwHdSKWFTYR5WuiAewauSuNaBXned`

---

## 🖥️ Steps

1. Login to the website.
2. well there is a input secret section. let's view the source to figure out what's it saying. here it's the important part. it requires some basic php knowledge. we put a secret then it makes a post request and checks with an another secret. i think the secret is in the `includes/secret.inc` path.
```
<?

include "includes/secret.inc";

    if(array_key_exists("submit", $_POST)) {
        if($secret == $_POST['secret']) {
        print "Access granted. The password for natas7 is <censored>";
    } else {
        print "Wrong secret";
    }
    }
?>
```
3. add the path to the end of the url and go for the page's source code. and there is the secret. go to the main page and submit this secret.
```
?
$secret = "FOEIUWGHFEEUHOFUOIU";
?
```
4. after submiting you'll get the natas7's pass.
```
Access granted. The password for natas7 is bmg8SvU1LizuWjx3y7xkNERkHxGre0GS
```
---
