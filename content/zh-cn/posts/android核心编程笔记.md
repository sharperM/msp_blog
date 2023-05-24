---
title: "android 核心编程笔记"
date: 2023-05-18T20:11:04+08:00
lastmod: 2023-05-18T20:10:57+08:00
draft: true
tags: ["notes"]
categories: ["Notes"]
authors:
- "sharperM"
---



## Activty 的生命周期
onCreate
onStart
onRestart
onResume
onPause
onStop
onDestory

## 使用viewmodel处理数据

## 使用 onSaveInstanceState 保存临时的数据, 
    暂存的数据会在 使用回退键退出程序后销毁，或者重启系统后销毁

## 在调用onStop 时保存数据
    （写到磁盘，或者上传网络）  
    持久化保存数据
    shared preference
    数据库

# start 第二个 activity

##  intent extra：activity间的通信与数据传递
    Intent.putExtra(EXTRA_ANSWER_IS_TRUE, answerIsTrue)
## 从子 activity 获取运行结果
    Activity.startActivityForResult(Intent, Int)
### 子activity 返回结果 
    Activity.setResult(Int, Intent)

# 不同sdk版本的兼容性

```kotlin
    Build.VERSION.SDK_INT >= Build.VERSION_CODES.M
```

# fragment


## 创建Crime数据类

    data

```kotlin
    data class Crime(val id: UUID = UUID.randomUUID(),
    var title: String = "",
    var date: Date = Date(),
    var isSolved: Boolean = false)
```

## fragment 生命周期
    
    onAttach
    onCreate
    onCreateView
    onViewCreated
    onStart


# RecyclerView

## viewmodel

```kotlin
    private val crimeListViewModel: CrimeListViewModel by lazy {
        ViewModelProviders.of(this).get(CrimeListViewModel::class.java)
    }
```


# 第11章 数据库 Room库
    RoomDatabase
## DAO 数据对象
## LiveData 
    可以在线程传递数据
