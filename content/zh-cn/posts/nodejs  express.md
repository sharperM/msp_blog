---
title: "nodejs  express"
date: 2023-07-29T10:25:31+08:00
draft: true

---
# nodejs  express

    https://developer.mozilla.org/zh-CN/docs/Learn/Server-side/Express_Nodejs


环境搭建

安装nodejs

    https://nodejs.org/en/download/

安装express
    
    npm install express-generator -g


创建项目 hello express

    express hello-express


了解概念
    本地图书馆项目
        书籍、作者、用户、评论

    网站框架
        路由、模板/视图、数据库
    
    使用数据库
        mongoose
        安装 MongoDB
            ubuntu https://www.myfreax.com/how-to-install-mongodb-on-ubuntu-20-04/  
                    https://mongodb.net.cn/manual/tutorial/install-mongodb-on-ubuntu/
                    
        安装 mongoose
            npm install mongoose --save
    
    路由 和 控制器
        路由： 一个URL（或者叫路径）和一个特定的HTTP方法（GET、POST等）的结合
        控制器： 路由匹配到之后执行的函数
    在html 展示 图书数据
        使用模板引擎，将数据和模板结合，生成html

    使用表单提交数据
        表单提交数据，保存到数据库

    部署到服务器
        部署到服务器，让其他人也能访问

