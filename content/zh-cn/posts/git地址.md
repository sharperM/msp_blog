---
title: "地址"
date: 2023-03-29T10:25:31+08:00
draft: true
tags: ["youmieyou"]
categories: ["Notes"]
authors:
- "sharperM"
---



## 消消乐

    git@codeup_2:64089bfe56067d3aad3e0e4c/cocos_creator_project/xiaoxiaole.git

## 假页面2

	git@codeup_2:64089bfe56067d3aad3e0e4c/FakeHotelIndex.git

## 假页面地址

git

    git@codeup_2:64089bfe56067d3aad3e0e4c/FakePage-Sample.git



https

    https://codeup.aliyun.com/64089bfe56067d3aad3e0e4c/FakePage-Sample.git


## 我的blog
    
    git@github.com:sharperM/msp_blog.git


## 常用命令

### 1.添加远程仓库
    git remote add origin https://codeup.aliyun.com/64089bfe56067d3aad3e0e4c/FakeHotelIndex.git

    消消乐git地址
    git remote add origin git@codeup_2:64089bfe56067d3aad3e0e4c/cocos_creator_project/xiaoxiaole.git


我的账号
maishaopei@youmieyou.onaliyun.com



搜索多仓库 ssh 配置

编辑~/.ssh/config 文件

增加
```ini
		#工作账号
		Host codeup_1
		HostName codeup.aliyun.com
		IdentityFile ~/.ssh/id_rsa
		
		#我的码云账号
		Host codeup_2
		HostName codeup.aliyun.com
		IdentityFile ~/.ssh/id_maishaopei_youmieyou
```

### 2.打包 archive

git archive 

    git archive --output=111.zip --format=zip HEAD




git remote add origin https://codeup.aliyun.com/64089bfe56067d3aad3e0e4c/FakeHotelIndex.git

git@codeup_2:64089bfe56067d3aad3e0e4c/cocos_creator_project/xiaoxiaole.git

假页面2
	git@codeup_2:64089bfe56067d3aad3e0e4c/FakeHotelIndex.git


git clone git@codeup_2:64089bfe56067d3aad3e0e4c/FakePage-Sample.git

假页面地址
git clone https://codeup.aliyun.com/64089bfe56067d3aad3e0e4c/FakePage-Sample.git


我的blog
git@github.com:sharperM/msp_blog.git



消消乐git地址
git remote add origin git@codeup_2:64089bfe56067d3aad3e0e4c/cocos_creator_project/xiaoxiaole.git

maishaopei@youmieyou.onaliyun.com

搜索多仓库 ssh 配置

编辑~/.ssh/config 文件

增加
```ini
		#工作账号
		Host codeup_1
		HostName codeup.aliyun.com
		IdentityFile ~/.ssh/id_rsa
		
		#我的码云账号
		Host codeup_2
		HostName codeup.aliyun.com
		IdentityFile ~/.ssh/id_maishaopei_youmieyou
```



ssh 使用证书和 特定的端口

修改 config 文件

```ini

		#工作账号
		Host gitlab3
		HostName 192.168.0.197
		Port 12022
		IdentityFile ~/.ssh/gitlab_key3

```


clone 命令用 

```cmd
	git clone git@gitlab3:maishaopoei/oasis.git oasis3



	//Existing Git repository
	cd existing_repo
	git remote rename origin old-origin
	git remote add origin ssh://git@localhost:12022/maishaopoei/lkddz_creator.git
	git push -u origin --all
	git push -u origin --tags
	
	git remote rename origin old-origin

git remote add gitlab  git@gitlab3:maishaopoei/lkddz_creator.git
git remote add gitlab  git@gitlab3:maishaopoei/svr_pxq.git
git remote add gitlab  git@gitlab3:maishaopoei/svr_xxl.git
git remote add gitlab  git@gitlab3:maishaopoei/svr_tn.git
git remote add gitlab  git@gitlab3:maishaopoei/svr_fpj.git
git remote add gitlab  git@gitlab3:maishaopoei/svr_ddz.git
git remote add gitlab  git@gitlab3:maishaopoei/lksql.git
git remote add gitlab  git@gitlab3:maishaopoei/lkgamecore.git



	git push -u gitlab --all
	git push -u gitlab --tags
```