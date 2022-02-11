---
title: Linux命令
date: 2021-07-24 16:19:41
tags: Linux
categories: 写作
img: https://i.loli.net/2021/08/11/HLUVe2p7dmCrSgl.jpg
#password: af89b3b3afc476d87401059ae58ce2e0d1f93567e4a07ccc19233571c5b44977 #设置密码（yml中开启相应功能）

---
## CentOS系统常用Linux命令整理
---
### 系统层面常用操作
```
## 查看系统IP等信息
ifconfig
## 查看Linux版本信息
cat /etc/redhat-release
# 查看内存大小
df -h
```
### 权限设置常用操作（待补充....）
```

```

### 网络以及进程层面常用操作

```
# 查看进程
ps -ef|grep 进程名 
# 杀进程
kill -9 进程号
# 查看某个端口的进程有哪些
netstat -anp|grep 端口号
```

### 文件方面常用操作
```
# 创建一个文件
touch 文件名
# 创建一个文件夹
mkdir 文件夹名
# 写入空值，如实现一个清空logs/catalina.out日志的作用
echo "" >  需要清空的目标文件名
```

### 文件传输相关命令
```
# 上传本地目录到远程机器的指定目录
scp -r 本地需要发的文件 root@192.168.120.204:目标服务器路径
```

## linux防火墙开放和禁用指定端口
---
### linux防火墙开放和禁用指定端口
#### 一、例如：开放8080端口

`firewall-cmd --permanent --add-port=8080/tcp`

#### 二、重启使设置生效

`systemctl restart firewalld.service`

#### 三、查看设置

`firewall-cmd --list-all`

#### 四、例如：禁用8080端口

`firewall-cmd --permanent --remove-port=8080/tcp`

#### 五、重启使之生效



## 关闭防火墙
----
CentOS/RedHat 6和CentOS/RedHat 7的防火墙关闭命令有所不同。
CentOS/RedHat 6：

`[root@localhost ~]# service iptables stop`

上述命令只是临时关闭了防火墙，重启后又会启动，故还需执行以下命令，使其服务器重启后不自启动防火墙。

`[root@localhost ~]# chkconfig --level 345 iptables off`

CentOS/RedHat 7：

`[root@localhost ~]# systemctl stop firewalld`

上述命令只是临时关闭了防火墙，重启后又会启动，故还需执行以下命令，使其服务器重启后不自启动防火墙。

`[root@localhost ~]# systemctl disable firewalld`





