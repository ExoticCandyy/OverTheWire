# Natas Level 11

## 🧪 Credentials

- **URL**: `http://natas11.natas.labs.overthewire.org`
- **Username**: `natas11`
- **Password**: `UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk`

---

## 🖥️ Steps

1. Login to the website.
2. here is the source code. i'll briefly tell what does it to. we have a `defaultdata` that's an array and the arguments are `showpassword` and `bgcolor`. in the web server it uses the `defaultdata` and a `key` to create a cooky and sends it to us. you need to know how XOR encryption works just google it. now how we are going to solve this? we have the cooky `data` and the `defaultdata` if we can XOR encrypt these two we can get the `key` then we will change the `defaultdata`'s `showpassword` argument to yes and then XOR encrypt this with the key and create the new cooky and change the cooky to the new one and refresh the page. 
```
$defaultdata = array( "showpassword"=>"no", "bgcolor"=>"#ffffff");

function xor_encrypt($in) {
    $key = '<censored>';
    $text = $in;
    $outText = '';

    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
    $outText .= $text[$i] ^ $key[$i % strlen($key)];
    }

    return $outText;
}

function loadData($def) {
    global $_COOKIE;
    $mydata = $def;
    if(array_key_exists("data", $_COOKIE)) {
    $tempdata = json_decode(xor_encrypt(base64_decode($_COOKIE["data"])), true);
    if(is_array($tempdata) && array_key_exists("showpassword", $tempdata) && array_key_exists("bgcolor", $tempdata)) {
        if (preg_match('/^#(?:[a-f\d]{6})$/i', $tempdata['bgcolor'])) {
        $mydata['showpassword'] = $tempdata['showpassword'];
        $mydata['bgcolor'] = $tempdata['bgcolor'];
        }
    }
    }
    return $mydata;
}

function saveData($d) {
    setcookie("data", base64_encode(xor_encrypt(json_encode($d))));
}

$data = loadData($defaultdata);

if(array_key_exists("bgcolor",$_REQUEST)) {
    if (preg_match('/^#(?:[a-f\d]{6})$/i', $_REQUEST['bgcolor'])) {
        $data['bgcolor'] = $_REQUEST['bgcolor'];
    }
}

saveData($data);



?>

<h1>natas11</h1>
<div id="content">
<body style="background: <?=$data['bgcolor']?>;">
Cookies are protected with XOR encryption<br/><br/>

<?
if($data["showpassword"] == "yes") {
    print "The password for natas12 is <censored><br>";
}

?>
```
3. i have written some php files i will explain them. and  this is the `natas11.php` file. here i basically use the `xor_encrypt()` function in the source code and changed it a bit. you might ask why did you used `base64_decode` or `json_encode`. look at the source code there are two functions named `saveData()` and `loadData()` there we used `base64_decode` and `json_encode` before using the `xor_encrypt()`. after running the script you'll get the `eDWoeDWoeDWoeDWoeDWoeDWoeDWoeDWoeDWoeDWoeL`. the `key` is `eDWo`. why did it printed many times? because there is a loop in the code.
```
<?php
$data = base64_decode("HmYkBwozJw4WNyAAFyB1VUcqOE1JZjUIBis7ABdmbU1GIjEJAyIxTRg%3D");
function xor_encrypt($in) {
    $key = json_encode(array( "showpassword"=>"no", "bgcolor"=>"#ffffff"));
    $text = $in;
    $outText = '';

    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
    $outText .= $text[$i] ^ $key[$i % strlen($key)];
    }

    return $outText;
}
echo xor_encrypt($data);

?>
```
4. here is the `natas11_2.php` file. i have added the `key`. the rest is obvious. now after running you'll get `HmYkBwozJw4WNyAAFyB1VUc9MhxHaHUNAic4Awo2dVVHZzEJAyIxCUc5`. change the cooky's value to this, then refresh the page. after that we'll get the pass `The password for natas12 is yZdkjAYZRd3R7tq7T5kXMjMJlOIkzDeB`.
```
<?php
function xor_encrypt($in) {
    $key = 'eDWo';
    $text = $in;
    $outText = '';

    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
    $outText .= $text[$i] ^ $key[$i % strlen($key)];
    }

    return $outText;
}
$defaultdata = array( "showpassword"=>"yes", "bgcolor"=>"#ffffff");
echo base64_encode(xor_encrypt(json_encode($defaultdata)));
?>
```
---
