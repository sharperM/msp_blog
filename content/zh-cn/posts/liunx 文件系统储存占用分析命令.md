---
title: "Liunx 文件系统储存占用分析命令"
date: 2023-03-30T19:54:51+08:00
draft: true
---
    1.查看当前目录
    df -h
    2.查看指定目录
    df -h /usr/

    1.查看当前目录每个文件夹的情况。
    du --max-depth=1 -h 
    2.指定目录
    du --max-depth=1 -h  /usr/
    计算文件夹大小
    du -sh /usr/


其中df -h和du -sh使用的比较多，一个统计整体磁盘情况，一个看单独目录点用情况，而命令du --max-depth=1 -h查看了目录下文件夹占用情况，使用比较少，可以用du -sh代替，而且命令较长，当然并不是说它没用。


    1.4G	/lib
    318M	/mysql-temp
    3.1G	/var
    1.6G	/usr
    767M	/root
