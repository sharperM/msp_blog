---
title: "qnap威联通部署gitlab"
date: 2023-08-05T10:25:31+08:00
draft: false
tags: ["gitlab","qnap","威联通",'docker']
categories: ["Notes"]
authors:
- "sharperM"
---
# 前言

没有选择在container station 搜索gitlab的镜像，
因为版本太旧有不安全的问题，所以选择了通过docker命令安装。

## 0.准备工作


## 1.安装docker
    qnap 安装 container station

## 2.ssh连接NAS的
window 推荐使用“mobaxterm”

linux 直接使用ssh命令

    ssh username@<nas's ip address>

    输入密码
    登录nas
## 3.安装gitlab
通过ssh
```shell
    export GITLAB_HOME=/share/homes/admin/git_repo

    docker run --detach \
    --hostname www.example.com \
    --publish 11443:443 --publish 11080:80 --publish 11022:22 \
    --name gitlab \
    --restart always \
    --volume $GITLAB_HOME/config:/etc/gitlab \
    --volume $GITLAB_HOME/logs:/var/log/gitlab \
    --volume $GITLAB_HOME/data:/var/opt/gitlab \
    --shm-size 256m \
    gitlab/gitlab-ce:latest
```

## 4.配置说明

    GITLAB_HOME 
    为gitlab的数据存储目录

可以通过
``` shell
    df -h
``` 
查看磁盘挂载情况
    判断哪些是挂载的硬盘

    --hostname www.example.com \ #域名
    --publish 11443:443 --publish 11080:80 --publish 11022:22 \ #端口映射
    --name gitlab \ #容器名
    --restart always \ #重启策略
    --volume $GITLAB_HOME/config:/etc/gitlab \ #配置文件
    --volume $GITLAB_HOME/logs:/var/log/gitlab \ #日志文件
    --volume $GITLAB_HOME/data:/var/opt/gitlab \ #数据文件
    --shm-size 256m \ #共享内存大小
    gitlab/gitlab-ce:latest #镜像名

# 5.配置gitlab

获取root密码
```shell
sudo docker exec -it gitlab grep 'Password:' /etc/gitlab/initial_root_password

```
运行上面的命令后，会返回一个密码，复制下来，然后在浏览器中输入你的NAS的IP地址，然后输入用户名root，密码就是上面复制的密码，登录后会提示你修改密码，修改完毕后，就可以使用了。


