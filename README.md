# HorizontCMS-1.0.0-beta-shell-upload (CVE-2020-28693)

Author: jkana
----

The vulnerable is in Theme upload function.

1.Login as administrator or any users could change themes.

2.Create a zip file which have php shell inside. For example **shell.zip** with **shell.php** inside

![](https://github.com/jkana/HorizontCMS-1.0.0-beta-shell-upload/raw/main/Images/1.JPG)

2.Access to **http://IP/admin/theme/index** . For example:
```http://192.168.10.67:81/hcms/admin/theme/index```

![](https://github.com/jkana/HorizontCMS-1.0.0-beta-shell-upload/raw/main/Images/2.JPG)

3.Upload **shell.zip**

![](https://github.com/jkana/HorizontCMS-1.0.0-beta-shell-upload/raw/main/Images/4.JPG)

4.Access to shell **http://IP/themes/shell.php**. For example:
```http://192.168.10.67:81/hcms/themes/shell.php```

![](https://github.com/jkana/HorizontCMS-1.0.0-beta-shell-upload/raw/main/Images/3.JPG)

