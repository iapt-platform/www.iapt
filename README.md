# IAPT 官方网站

![homepage](static/images/readme/example.jpg)

## 概述

这个库是IAPT官方网站的数据。使用[hugo](https://gohugo.io/)作为cms。库中包括所有图片，UI文字，博客文章。以及主题模版。[hugo中文文档](https://www.gohugo.org/doc/).

网站使用了名为meghna-hugo的模板。模板地址：https://github.com/themefisher/meghna-hugo。
原来的模板有较多的栏目。有些用不到的已经在主页删除。此模板支持多语言

## 安装

### 依赖软件

- hugo
- git
- vscode

### hugo
hugo的安装请参见官网[安装说明](https://gohugo.io/getting-started/installing/)。这里只是一个简要介绍。

1. 在[程序包下载页面](https://github.com/gohugoio/hugo/releases)找到对应你的操作系统的安装包。例如：windows 10 请下载`hugo_0.91.2_Windows-64bit.zip`(你看到的版本号可能与这个不同)最高版本有可能没有windows版。请查找低版本。
2. 将压缩包里的文件hugo.exe解压缩到你的硬盘上的某个目录。例如： `c:/` 。
3. 测试hugo 是否正常安装。在命令行(windows输入cmd)里运行`c:/hugo.exe version`。能够显示版本号就是安装成功了。

### 克隆git仓库

fork `https://github.com/iapt-platform/www.iapt`到你自己的仓库。
在www.iapt目录下运行
```
git clone https://github.com/<your repo>/www.iapt.git
cd www.iapt
git pull
git submodule update --init --recursive
```
git 会生成www.iapt目录



### 运行

在`www.iapt`目录下运行命令 `c:/hugo.exe server -D`

打开浏览器 输入：`http://localhost:1313/`。应该显示网站页面。

## 目录结构

> 温馨提示：模板支持多语言。所以有些目录中包含不同语言的子目录。

- www.iapt
	- content `文章内容`
		- chinese `中文文章内容`
		- english `英文文章内容`
	- data `页面文字`
	- i18n `页面文字`
	- sttic `图片等资源`
		- images `网站UI图片`
			- about 
			- backgrounds `背景图`
			- blog `博客图片`
			- clint `专家照片`
			- team `项目图片`
	- config.toml `首页标题，按钮文字设置`
	- layouts `版面设计`
  	  - index.html `首页布局`

## 网站设置

config.toml

- 默认语言：`defaultContentLanguage = 'zh'`
- 顶部导航：`[[Languages.en.menu.main]]`
- 语言选择: `[Languages.zh]`
- web icon: `static\images\favicon.png`
- logo: `static\images\logo.png`

## 栏目维护

### 题头

data\zh\banner.yml

sttic/images/backgrounds/hero-area.jpg

### 关于我们

data\zh\about.yml

### 工作涵盖

data\zh\feature.yml

### 项目

data\zh\team.yml

项目链接的文章：`content\chinese\project`

### 专家

content\chinese\author

### 博文

content\chinese\blog

在该目录中添加的markdown文件会自动显示在博文列表中。

在该目录中添加的markdown文件会在浏览器中的相应的路径中显示。
比如 content\chinese\blog\simple-blog-post-1.md 文件，在浏览器中显示路径为 http://localhost:1313/blog/simple-blog-post-1/
文章中可以带有跳转到其他文章的链接。

应正确填写每篇文章开头的摘要信息 

```
---
title: "Simple Blog Post"
date: 2018-09-12T12:52:36+06:00
image_webp: images/blog/blog-post-3.webp
image: images/blog/blog-post-3.jpg
author: John Doe
description : "This is meta description"
---
```

>温馨提示:所有文章使用markdown格式。
>参考资料：markdown 语法 https://markdown.com.cn/basic-syntax/

### 联系方式

data\zh\contact.yml

# 工作流程

- fork `https://github.com/iapt-platform/www.iapt`到你自己的仓库。
- clone `https://github.com/<你的账号>/www.iapt`到你自己的本地硬盘。
- 修改
- 提交到你的仓库
- 提交 pull request 到`https://github.com/iapt-platform/www.iapt`
- 管理员审核后merge到main