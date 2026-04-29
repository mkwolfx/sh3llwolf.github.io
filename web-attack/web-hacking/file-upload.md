---
description: >-
  File upload vul are when a web server allows users to upload files to its 
  filesystems without sufficiently validating things like their
  (name,type,contents or size )
---

# File upload

{% embed url="https://portswigger.net/web-security/information-disclosure/exploiting#source-code-disclosure-via-backup-files" %}



How to find file upload vulnerabilities:

```
# identify the backend technology that the application is built on
php , java ...

# identify all the instances in the application that allow you to upload files
entry points: Profile pictures, CV uploads, Contact Us" attachments. 

# uplode a regualr file & determine if u can call /execute the file.

```

attempt to upload a web shell(ex: php web shell)

* check for flawed file type validation (content-type)
* check the insufficient blacklisting of danger ous file types (.php , .php2, php3, ..etc)
* bypass the file extension restriction using obfuscation techniques(url-encoding, null byte etc..)
* check the flawed validation of the file's content
