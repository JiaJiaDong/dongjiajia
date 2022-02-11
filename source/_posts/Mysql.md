---
title: Mysql
date: 2021-08-11 22:08:46
tags: Mysql
categories: 写作
img: https://i.loli.net/2021/08/11/5BScspZ243ID9Xq.jpg
---


<a href="https://sm.ms/image/5BScspZ243ID9Xq" target="_blank"><img src="https://i.loli.net/2021/08/11/5BScspZ243ID9Xq.jpg" alt="" width="100%"></a>


## Mysql修改密码
----
### 知道密码的情况下
1、mysql -uroot -p

2、Enter password: 【输入原来的密码】

3、mysql>use mysql;

4、mysql> update user set password=passworD("新密码") where user='root';`（5.7版本以上是没有password字段）`

5、mysql> flush privileges;  #立即生效

6、mysql> exit;

**注意：如果Mysql的版本是5.7及以上的话update语句更换如下：**

>update mysql.user set authentication_string=password('新密码') where user='root（用户名）';

### 忘记密码情况下（无用到待补充....）
----