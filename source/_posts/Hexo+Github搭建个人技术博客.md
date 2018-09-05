---
title: Hexo + Github 搭建个人技术博客
tags: [hexo]
---
这是我的第一篇文章，主要用来记录Hexo + Github 搭建个人技术博客过程

## Hexo + Github 搭建个人技术博客过程

### 背景
作为一个程序员，一直想搞一个个人的技术博客，虽然有很多技术博客网站（CSDN、简书等）都很好用，但本人主要想用记录博客的方式记录一些技术细节，方便以后好查找。本着免费的原则，网上找了很久，终于发现了Hexo，它可以很简单的使用GitHub托管的方式快速搭建一个博客，下面我记录下本人搭建的过程。

### 前提

准备工作

+ 拥有一个GitHub账号
+ 安装Node.js、npm，并了解相关基础
+ 安装Git客户端

本人使用的环境

+ mac
+ node -v `v8.8.1`
+ git --version `2.12.2`


### 新建仓库

在GitHub新建一个名为`{username}.github.io`的仓库，比如你的GitHub用户名是pig，就新建一个pig.github.io的仓库。将来博客搭建好了之后，就可以通过，`https://pig.github.io`来访问了。


### 配置SSH key

要想提交代码到GitHub，必须有GitHub权限才行。GitHub可以通过配置SSH Key来解决本地跟GitHub服务器的连接安全问题。

1. 配置全局name和email
``` bash
git config --global user.name "name"  
  
git config --global user.email "email"
```
name和email是注册github的昵称和邮箱

2. 生成Key
```
test
```

More info: [Deployment](https://hexo.io/docs/deployment.html)
