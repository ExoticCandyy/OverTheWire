# Natas Level 7

## 🧪 Credentials

- **URL**: `http://natas7.natas.labs.overthewire.org`
- **Username**: `natas7`
- **Password**: `bmg8SvU1LizuWjx3y7xkNERkHxGre0GS`

---

## 🖥️ Steps

1. Login to the website.
2. there are two sections named `Home` and `About`. i looked into the source and there is a dir path named `/etc/natas_webpass/natas8`.
3. by swutching between `Home` and `About` pages i realized that the url changes between `index.php?page=home` and `index.php?page=about`. so these are in the `index.php` page. so i'll search this `http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8` and there is the pass.
```
 xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q
```
---
