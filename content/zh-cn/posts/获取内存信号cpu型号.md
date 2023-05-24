
win+r
cmd

输入命令
 wmic
 memorychip
 cpu get *





1.查看磁盘信息：freedisk 可以查看每一个盘的剩余空间

wmic diskdrive

可以看出来牌子和大小.

Wmic logicaldisk

可以看到有几个盘，每一个盘的文件系统和剩余空间

wmic volume

每个盘的剩余空间量，其实上一个命令也可以查看的

fsutil volume diskfree c:

这个命令查看每一个卷的容量信息是很方便

2.CPU信息

wmic cpu

上面显示的有位宽，最大始终频率， 生产厂商，二级缓存等信息

3.内存信息

    wmic memorychip

可以显示出来三条内存，两条256，一条1G的，速度400MHz

4.BIOS信息

    wmic bios

————————————————
版权声明：本文为CSDN博主「如今，」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/weixin_48103302/article/details/119824297