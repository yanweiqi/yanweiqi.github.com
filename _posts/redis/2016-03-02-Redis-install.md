---
layout: post
title: Redis install
date: 2016-02-27 02:41
author: yanweiqi
comments: true
categories: [redis]
tags: [redis]
---

---------------------------

* 目录
{:toc}

--------------------------

### 下载

* 进入Redis官网获取Redis最新稳定版下载地址:官网下载[redis.io](http://redis.io/download)
* 通过wget命令下载 Redis 源代码

``` shell
$ wget http://download.redis.io/releases/redis-3.0.7.tar.gz
$ tar xzf redis-3.0.7.tar.gz
$ cd redis-3.0.7
$ make
```
**注意** make命令执行完成编译后，会在src目录下生成6个可执行文件，分别是redis-server、redis-cli、redis-benchmark、redis-check-aof、redis-check-dump、redis-sentinel。
![Alt text](/images/redis/1.png)

### 执行安装

```shell
$ make install
```

**注意** make instll 编译生成的可执行文件拷贝到/usr/local/bin目录下

### 执行基本配置

* 进入解压目录redis-2.8.24/utils，执行install_server.sh配置Redis

![Alt text](/images/redis/2.jpg)

**注意**

>EXEC=/usr/local/bin/redis-server        *`#make install后默认存放与/usr/local/bin/redis-server`* <br/>
CLIEXEC=/usr/local/bin/redis-cli         *`#客户端位置`*   <br/>
PIDFILE=/var/run/redis_${REDISPORT}.pid  *`#Redis的PID文件位置`* <br/>

### 启动&关闭

* 开启Redis服务操作通过/etc/init.d/redis_6379 start，也可通过（service redis_6379 start）

* 关闭Redis服务操作通过/etc/init.d/redis_6379 stop，也可通过（service redis_6379 stop）

* ./redis-server & *`#redis以后台程序方式运行`*

* 通过配置文件启动 ./redis-server redis.conf

vim 修改配置文件redis.conf

``` shell
daemonize no                          #修改daemonize为yes，即默认以后台程序方式运行。
port 6379                             #可修改默认监听端口
logfile "/home/futeng/logs/redis.log" #修改生成默认日志文件位置
dir /home/futeng/data/redisData       #配置持久化文件存放位置
```

### 验证启动

``` shell
ps aux|grep redis          #检测后台进程是否存在
netstat -lntp | grep 6379  #检测端口是否在监听
```
