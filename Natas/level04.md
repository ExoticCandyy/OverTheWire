# Natas Level 4

## 🧪 Credentials

- **URL**: `http://natas4.natas.labs.overthewire.org`
- **Username**: `natas4`
- **Password**: `QryZXc2e0zahULdHrtHxzyYkj59kUxLQ`

---

## 🖥️ Steps

1. Login to the website.
2. it says `Access disallowed. You are visiting from "" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/"
`. if you click the `Refresh page` button it will change to `Access disallowed. You are visiting from "http://natas4.natas.labs.overthewire.org/index.php" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/" ` so it means it uses a referral link. in the first time there wasn't any referral link but in the second time there was.
3. there are two tricks we can do, i'll go with the funny one. i will go into `http://natas5.natas.labs.overthewire.org` and yes i don't know the pass right but i don't need one. after going into that page i will click sign in with no pass and username, the `Unauthorized` page will come up. then i will add the `http://natas4.natas.labs.overthewire.org` link via inspect elemnts and click on it. it will do the job.
```bash
<html><head>
<title>401 Unauthorized</title>
</head><body>
<h1>Unauthorized</h1>
<p>This server could not verify that you
are authorized to access the document
requested.  Either you supplied the wrong
credentials (e.g., bad password), or your
browser doesn't understand how to supply
the credentials required.</p>
<hr>
<address>Apache/2.4.58 (Ubuntu) Server at natas5.natas.labs.overthewire.org Port 80</address>
<a href="http://natas4.natas.labs.overthewire.org">click here</a>
</body></html>
```
4. i have added the `<a href="http://natas4.natas.labs.overthewire.org">click here</a>` line. after clicking that we'll go to the natas4 page and the pass is there. here is the pass:
```
 Access granted. The password for natas5 is 0n35PkggAPm2zbEpOU802c0x0Msn1ToK
```
---
