---
title: "升级 ubantu 20 后 mysql 8.0 内存 swap cpu 高"
date: 2016-03-23T20:11:04+08:00
lastmod: 2023-03-06T20:10:57+08:00
draft: true
tags: ["notes"]
categories: ["Notes"]
authors:
- "sharperM"
---

升级 ubantu 20 后 mysql 8.0 内存 swap cpu 高


service mysql stop


apt list --installed|grep sql


卸載mysql
https://www.cnblogs.com/zhangxuel1ang/p/13456116.html

安裝mysql

https://askubuntu.com/questions/1232558/install-mysql-5-7-on-ubuntu-20-04