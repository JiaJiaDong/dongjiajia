---
title: Redis
date: 2021-08-11 21:13:07
tags: Redis
categories: 写作
img: https://i.loli.net/2021/07/18/M9o7msKrbJpaIfV.png
---
<img src="https://i.loli.net/2021/07/18/M9o7msKrbJpaIfV.png" width="100%">

## redis启动
```
# 1.指定配置文件启动
/usr/local/bin/redis-server /home/redis-3.2.5/redis.conf
或redis-server /home/redis-3.2.5/redis.conf
# 2.验证是否启动成功
使用redis-cli验证redis是否启动成功
若redis可以登录但是oam连接失败就bind 0.0.0.0
# 3.redis下的src目录中执行进入redis命令行
./redis-cli
# 4.输入redis账号密码后，执行info命令若结果有版本号等信息表示启动成功
127.0.0.1:6379> info
```

## redis常用命令
```
# 使用密码登陆
./redis-cli -h 127.0.0.1 -p 6379 -a 密码
# 密码忘记进入redis的安装目录（是安装目录的），查看redis.config文件
搜索 requirepass foobared
# 切换某个redis库
127.0.0.1:6379> select 3
# 获取库下所有key
127.0.0.1:6379> keys *
# 获取key中的value（不同类型的value获取方式不一样）
# 获取hash类型key的值 
127.0.0.1:6379[3]> hgetall key值
# 获取String类型key的值：
127.0.0.1:6379[3]> get key值
# 清空所有库的值
flushall
```

## redis修改密码
-----
1、`redis.conf`中搜索`requirepass`则看到密码...

2、重启redis


