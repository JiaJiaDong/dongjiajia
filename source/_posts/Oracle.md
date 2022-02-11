---
title: Oracle常用文档
tags: Oracle
categories: 写作
###password: af89b3b3afc476d87401059ae58ce2e0d1f93567e4a07ccc19233571c5b44977

---
![Damn it. Hard to  die ...](https://i.loli.net/2021/07/18/Zz6EYgQrNj5ItAw.jpg)

## Oracle创建用户需要做的事情（待完善...）
```
#### 进入oarcle用户
su - oracle 
#### 以sysdba用户进入sql语句
sqlplus / as sysdba
#### 创建Oracle用户并设置密码
create user 用户名 identified by 密码;
#### 赋予用户登陆权限
grant create session to 用户名;
#### 赋予用户创建表的权限
grant create table to 用户名;
#### 给用户赋予表空间操作的权限
grant unlimited tablespace to 用户名;
#### 授权连接和操作表权限
grant resource,connect to 用户名;
#### 授权视图查询权限
grant CREATE VIEW,select any dictionary to 用户名;
```

## 修改用户名密码...有时候会过期...
```
# 切换用户
conn 用户名;
# 查询所有用户
SELECT * FROM ALL_USERS;
# 修改用户密码
alter user 用户名 identified by 新密码;
# 如果密码中含有特殊字符(@这个字符不能用在密码里面)
alter user 用户名 identified by "pws1&";
```

## 重启数据库
```
（1） 以oracle身份登录数据库，命令：su -oracle

（2） 系统管理员登录，命令：sqlplus / as sysdba

（5） 关闭数据库，命令：shutdown immediate

（4） 启动数据库，命令：startup

（6） 退出sqlplus控制台，命令：exit
```

## 启动监听（提供外界连接数据库的桥梁）
```
查看监听状态：[oracle@localhost ~]$ lsnrctl status

停止监听服务：[oracle@localhost ~]$ lsnrctl stop

启动监听服务：[oracle@localhost ~]$ lsnrctl start

当看到提示信息"The command completed successfully"，则表示启动成功。
```


## 遇到的一些问题...
### 一、Oracle数据库是从一台服务器克隆至另一台需要改的配置？
----------
此时主机名与IP与克隆一致

首先查看`/etc/hosts`文件的主机名和ip，修改后并重启。

`uname -a` 可以查看`hostname`是多少，就可以知道是否修改生效了。

>**修改listener.ora 和 tnsnames.ora文件的IP**
>- 首先切换到oracle用户下,env命令查看数据库配置文件信息
>- 然后找到LD_LIBRARY_PATH=/home/opt/oracle/product/11.2.0.4/db_1 （配置文件后面的 路径）
>- 进入到以上对应目录下 cd /home/opt/oracle/product/11.2.0.4/db_1
>- 切换到network/admin目录下可看到

### 二、数据库中用了drop删除表，后面没有加上purge的话，会出现在oracle的回收机制中
----------
### 1、查询你删除了哪些表

>时间倒序查看删除的表：select * from dba_recyclebin order by DROPTIME desc
>
>查看删除表的表数据：select * from OWNER的列值."OBJECT_NAME的列值"



### 2.如果想恢复数据的话，使用比较快捷的闪回工作

>flashback table "表名" to before drop
>
>或
>
>flashback table "表名" to before drop rename to 新表名;

#### 如果上面两种方法都不行的话...
![](https://img.soogif.com/1fKxg0zqatKK5ys9iXRdlidn3S4TGAGT.gif?scope=mdnice)

#### 可以用老方法，将数据都复制出去...

>create table 新表名 as select * from OWNER的列值."OBJECT_NAME的列值"


这样的话，数据就恢复了...



![](https://img.soogif.com/UAEzbzX1DYieADeV8XOFqmXBIYs6OpfN.gif?scope=mdnice)




### 三、oracle中查找某用户执行某张表的操作记录(待完善...)
----------
1、首先查找表的操作记录：

`select * from v$sqlarea a where a.SQL_TEXT like '%表名%';`

2、从上面的记录中找到对应的sql_id：

`select * from v$sqltext a,v$sqlarea b where a.SQL_ID=b.SQL_ID and b.SQL_ID in('sql_id','sql_id') order by b.LAST_ACTIVE_TIME desc;`

3、从上面的记录中找到最新的sql操作记录，然后找到用户名和主机：

`select * from sys.v_$session l,sys.v_$sql s where s.SQL_ID='cq53826tk4u3c' and l.USERNAME is not null;`