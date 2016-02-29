---
layout: post
title: AWK Program
date: 2016-02-27 02:41
author: yanweiqi
comments: true
categories: [linux,awk]
tags: [awk,linux]
---
## AWK编程

   awk是最难掌握的一种shell脚本处理工具，因为awk语法复杂，并包含了太多的程序细节。

### 为什么使用AWK

   awk是一种程序语言，它具有一般程序语言的功能，但又有其它程序语言无法比拟的便捷性和特点。

* 不需要编译
* 没有类型之分  

### 调用方法

* 命令行调用
  awk [-F 域分割符] 'awk程序段' 输入文件
* 脚本方式调用
  awk -f 脚本文件 输入文件
* 另一种脚本方式调用
  ./脚本文件 输入文件

### 记录和域

  awk以每行作为一条'记录'，行中每个字符串之间的间隔[空格]、[tab]、[:]等其它符号进行分割作为'域'。

* 域 awk定义'$'为域操作符，每条记录的域从1开始，'$0'代表整行记录，空格为默认分割符。

* '-F'改变分割符，还有一种方式是通过AWK的环境变量FS

例如1 打印所有记录

``` shell
   [root@localhost ywq]# awk '{print $0}' awktest.log
   MMAN started with pid=9, OS id=22862
   DBW0 started with pid=10, OS id=22866
   LGWR started with pid=11, OS id=22870
   CKPT started with pid=12, OS id=22874
   SMON:started with pid=13, OS id=22878
   RECO:started with pid=14, OS id=22882
```
例如2 打印指定的','分隔符,并输出$1

``` shell
    [root@localhost ywq]# awk -F"," '{print $1}' awktest.log
    MMAN started with pid=9
    DBW0 started with pid=10
    LGWR started with pid=11
    CKPT started with pid=12
    SMON:started with pid=13
    RECO:started with pid=14
```

### 关系运算符
