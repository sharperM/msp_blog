---
title: "CENTOS 部署 WORDPRESS 的步骤"
date: 2016-03-23T20:11:04+08:00
lastmod: 2023-03-06T20:10:57+08:00
draft: true
tags: ["notes"]
categories: ["Notes"]
authors:
- "sharperM"
---

安装 Apache , PHP , MySql, vsftpd
1.安装Apache

sudo yum install httpd mod_ssl
sudo /usr/sbin/apachectl start
sudo nano /etc/httpd/conf/httpd.conf
修改防火墙

sudo iptables -I INPUT -p tcp --dport 80 -j ACCEPT
sudo service iptables save
设置开机启动

sudo /sbin/chkconfig httpd on
2.安装PHP

sudo yum install php-mysql php-devel php-gd php-pecl-memcache php-pspell php-snmp php-xmlrpc php-xml
sudo /usr/sbin/apachectl restart
 

3.MySql

 

4.vsftpd

参考这里

http://www.cnblogs.com/xiongpq/p/3384759.html