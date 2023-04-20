---
title: "Memery Pool"
date: 2023-03-29T10:25:31+08:00
draft: true
---


## 什么适用?
针对小内存分配才使用的。小于128byes的情况


## 为什么需要memery pool ?
因为 new 分配内存，
delete 释放内存 带来性能消耗。
new 就是 malloc() 然后调用类的构造函数
delete 就是 调类的析沟函数，再调用free()
new
delete 
关键字

还有
操作符的 new， delete

gcc的alloc::allocate()
alloc::deallocate()

system heap （系统堆）（不连续的内存，通过链表的数据结构存储），通过一段连续内存的首部（32bit）记录，连续的内存大小，
链表表记录这些连续内存的大小和，首地址。

系统分配内存时，要查找，分配越大就越慢。


内存分配自定义
allocator 

new

allocator 的实现

就是 按8 的倍数
8，16，24，32，40，48，56，64，72，80，88，96，104，112，120，128
一共16种的内存大小









通过在类中重载 new 运算符。


注意 new 分配内存失败的情况， effect c++
