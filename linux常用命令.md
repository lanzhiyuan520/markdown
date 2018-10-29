#### linux常用命令

创建用户

```linux
useradd testuser  创建用户testuser
```

给创建用户设置密码

```linux
passwd testuser
```

删除用户

```
userdel testuser
```

删除用户所在目录

```
rm -rf testuser
```

查看当前用户

```
w
```

查看主机上的用户

```
who
```

查看当前用户登录是谁

```
whoami
```

切换用户

```
su 用户名
```

从本地拷贝文件到服务器命令

```linux
scp -P 端口号 本地文件路径 用户名@ip:拷贝到服务器路径
```

