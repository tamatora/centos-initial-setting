# CentOSの初期設定

1. 一般ユーザの作成
```
[root@centos7 ~]# useradd admin
[root@centos7 ~]# passwd admin
Changing password for user admin.
New password:
Retype new password:
passwd: all authentication tokens updated successfully.
[root@centos7 ~]#
```

2. sudo権限を付与
```
[root@centos7 ~]# visudo
```

***

```
a
```
