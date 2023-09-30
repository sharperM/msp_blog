---
title: "LINUX下使用TOP命令查看系统运行状态和进程运行状态 – 快乐编程"
date: 2016-03-23T20:11:04+08:00
lastmod: 2023-03-06T20:10:57+08:00
draft: true
tags: ["Linux"]
categories: ["Notes"]
authors:
- "sharperM"
---



在linux下可以通过top命令来查系统运行状态和进程运行状态，通过man查看top手册，top的解释是display Linux tasks，以前看到过一个另外的解释display top CPU processes，这个我觉得挺贴切的，因为top这个命令会自动把消耗高的进程排到前面，真的很形象。 1、命令说明 top 参数 -h：help表示显示帮助的意思 -v：version显示版本的意思，和-h的功能一样 -u：use