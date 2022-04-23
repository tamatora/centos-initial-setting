# CentOSの初期設定

1. 一般ユーザの作成
```
[root@test-server01 ~]# useradd setupuser
[root@test-server01 ~]# passwd setupuser
Changing password for user setupuser.
New password:
Retype new password:
passwd: all authentication tokens updated successfully.
[root@test-server01 ~]#
```

2. sudo権限を付与
```
[root@test-server01 ~]# visudo
```
```
## Allow root to run any commands anywhere
root    ALL=(ALL)       ALL
setupuser    ALL=(ALL)       ALL
```

3. SELinux無効化
```
[setupuser@test-server01 ~]$ getenforce
Enforcing
[setupuser@test-server01 ~]$ sudo setenforce 0
[setupuser@test-server01 ~]$ getenforce
Permissive

[setupuser@test-server01 ~]$ sudo vi /etc/sysconfig/selinux
```
```
# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=disable
# SELINUXTYPE= can take one of three values:
#     targeted - Targeted processes are protected,
#     minimum - Modification of targeted policy. Only selected processes are protected.
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted
```

