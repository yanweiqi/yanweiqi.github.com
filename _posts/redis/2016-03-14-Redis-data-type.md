---
layout: post
title: Redis data type
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

### String - 字符串

Redis的字符串是字节序列，在Redis中字符串是二进制安全的，这意味着它们有一个已知的长度，是没有任何特殊字符终止决定的，所以可以存储任何东西，最大可存512兆。

例子

``` shell

redis 127.0.0.1:6379> SET name "ywq"
OK
redis 127.0.0.1:6379> GET name
"ywq"

```

### Hashes - 哈希值

Redis的哈希键值对集合，Redis的哈希值是字符串和字符串之间映射，所以它们被用来表示对象。

例子

``` shell
redis 127.0.0.1:6379> HMSET user:1 username ywq password 123 points 200
OK
redis 127.0.0.1:6379> HGETALL user:1

1) "username"
2) "ywq"
3) "password"
4) "123"
5) "points"
6) "200"

```
以上是哈希数据类型，用于存储包含用户基本信息用的对象

### List -列表
