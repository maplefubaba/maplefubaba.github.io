---
title: "10分钟在github上创建一个博客"
date: 2024-04-14
description: "这是怎么回事"
summary: "测试"
tags: ["git"]
---

## 准备

说是10分钟，但是还是需要一点基础的。

- 需要在github上有一个账号，这个博客用的是github的静态页面服务，创建账号是很容易的，大概5分钟。
- 需要对git有一个基本的了解，应该对所有的程序员都不是问题，如果要不是程序员就需要花点时间学习一下了，估计要几个小时了解一下概念和实践一下。
- 下载安装[hugo](https://gohugo.io)。hugo是一个可以动态生成和管理网页的工具，它是用google出品的golang编写的，所以速度比类似工具jekyll快一个数量级。点[这里](https://github.com/gohugoio/hugo/releases/latest)下载最新的执行文件hugo_extended_xxxxxxxx_windows-amd64.zip。解压这个文件在windows下就得到hugo.exe。

hugo是一个命令行的工具，你可以把它下载以后在本地建立一个blog的目录，然后把hugo可执行文件hugo.exe拷到这个目录下运行就可以了。

OK，假设现在你已经具备一下条件。
- 你在github上已经创建账户myblog，github上空间网址www.github.com/myblog。
- 选好一个hugo的主题congo。选择这个主题的原因是congo很简洁，而且直接支持双语。
- 

## 创建博客
你在E:\blog目录下。

```shell
hugo new site myblog.github.io
cd myblog.github.io
git init
git submodule add https://github.com/jpanther/congo themes/congo

```
然后修改在myblog.github.io目录下的hugo.toml文件，在里面加上一行指定主题
```
theme='congo'
```

### .gitignore文件
```
### Hugo ###
# Generated files by hugo
/public/
/resources/_gen/
/assets/jsconfig.json
hugo_stats.json

# Executable may be added to repository
hugo.exe
hugo.darwin
hugo.linux

# Temporary lock file while building
/.hugo_build.lock

```
到这一步可以用git status看看。
![git status](vfuwNks2l0.png)

### 本地测试
执行
```
hugo server
```
在浏览器里面打开https://localhost:1313就可以访问了。

### commit&push到github
在github里创建代码库maplefubaba.github.io，这个名字的格式是固定的，以后也是可以直接访问的域名。
![Create new repo](create.new.repo.png)
![Steps to push](steps.to.push.png)

### github上设定
接着可以设定github上的actions，相当于自动在github的服务器上运行hugo来生成网页并且把他们放到github pages里面。

下面是在github里面设置actions：
![Actions S1](actions.s1.png)
搜索hugo
![Actions S2](actions.s2.png)
设置hugo的action
![Actions S3](actions.s3.png)
保存commit
![Actions S4](actions.s4.png)
![Actions S5](actions.s5.png)
可以直接在github上看到在根目录下创建了.github/workflows/hugo.yml文件
![Actions S6](actions.s6.png)

## 直接访问域名
图片

## 开始

从example site里面把文件拷贝出来。

### 中英双语
- 删除文件
- 设置

### 其他设置变更
- 主菜单
- 目录

[References]