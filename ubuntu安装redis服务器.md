安装redis服务器端

```
sudo apt-get install redis-server
```

检查redis服务器系统进程

```
 ps -aux|grep redis
 redis     7186  0.0  0.1  39144  3216 ?        Ssl  10:04   0:01 /usr/bin/redis-server *:6379
ubuntu    9164  0.0  0.0  13204   940 pts/0    S+   10:27   0:00 grep --color=auto redis
```

通过启动命令检查redis服务器状态

```
netstat -nlt|grep 6379
tcp        0      0 0.0.0.0:6379            0.0.0.0:*               LISTEN
tcp6       0      0 :::6379                 :::*                    LISTEN
```

检查redis服务器状态

```
sudo /etc/init.d/redis-server status
```

访问redis

```
redis-cli
```

redis配置

```
sudo vi /etc/redis/redis.conf
1.设置密码(默认没有密码)
#取消注释requirepass
requirepaa test    //将密码设置为test
----------------------------
2.让Redis服务器被远程访问(默认只能被本机访问)
#注释bind
#bind 127.0.0.1
----------------------------
3.重启redis服务器
sudo /etc/init.d/redis-server restart
注意：redis-cli如果没有用密码登录的话是可以登录，但是不可以操作，使用密码登录加 -a 密码
redis-cli -a pass

```

