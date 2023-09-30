---
title: "工作日记-任务 cocos creator 游戏 上架 ios"
date: 2023-07-30T20:11:04+08:00
lastmod: 2023-07-30T20:10:57+08:00
draft: true
tags: ["cocos creator"]
categories: ["Notes"]
authors:
- "sharperM"
---

任务 cocos creator 游戏 上架 ios

1 需要提供 微信登录

遇到问题：
1.Xcode 12: building for iOS Simulator, but linking in object file built fo... for architecture arm64
xcode 编译 开发平台示例 会报错
解决：https://blog.csdn.net/ws1836300/article/details/108755295

实测在 macmini m2 可行

在 游戏工程添加微信sdk库。添加拉起微信的代码

方法1：
cocos creator 要增加 jsbingding 代码 提供游戏调用

方法2：
用 creator 的 native.reflection.callStaticMethod 调用微信sdk的方法
调用