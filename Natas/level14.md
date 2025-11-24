# Natas Level 14

## 🧪 Credentials

- **URL**: `http://natas14.natas.labs.overthewire.org`
- **Username**: `natas14`
- **Password**: `z3UYcr4v4uBpeX8f7EZbMHlzK4UR2XtQ`

---

## 🖥️ Steps

1. Login to the website.
2. ok by looking at it you realize it's sql injection. let's look at the source. here you can see we can perform an injection at the `$query` line. in the login page at the username section i'll type `" OR 1=1 #`. this will do. if you have zero knowledge of what injection means go watch sql injection by NetworkChuck. 
```
if(array_key_exists("username", $_REQUEST)) {
    $link = mysqli_connect('localhost', 'natas14', '<censored>');
    mysqli_select_db($link, 'natas14');

    $query = "SELECT * from users where username=\"".$_REQUEST["username"]."\" and password=\"".$_REQUEST["password"]."\"";
    if(array_key_exists("debug", $_GET)) {
        echo "Executing query: $query<br>";
    }

    if(mysqli_num_rows(mysqli_query($link, $query)) > 0) {
            echo "Successful login! The password for natas15 is <censored><br>";
    } else {
            echo "Access denied!<br>";
    }
    mysqli_close($link);
} else {
?>
```
3. click login and you'll get the pass:
```
SdqIqBsFcz3yotlNYErZSZwblkm0lrvx
```
---
