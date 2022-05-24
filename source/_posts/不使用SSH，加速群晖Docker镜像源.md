---
title: 不使用SSH，加速群晖Docker镜像源
tags:
  - 群晖
  - synology
  - docker
  - 阿里云
categories: 技术教程
top_img: >-
  https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/不使用SSH，加速群晖Docker镜像源/yi9299.png
cover: >-
  https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/不使用SSH，加速群晖Docker镜像源/yi9299.png
toc: true
copyright_author: 承世
copyright_info: 此文章版权归 承世 所有，如有转载，请注明来自原作者
abbrlink: d71a
copyright_author_href: 'https://blog.shi.wiki/author/1/'
copyright_url: 'https://blog.shi.wiki/archives/5.html'
date: 2021-11-19 21:43:23
description:
---
> 这两天群晖docker一直下载不了，后来经了解，可以通过修改docker镜像来解决，然后百度如何修改docker镜像源，结果都是进入SSH什么的，经常尝试作用不大，后来发现，可以通过群晖本身窗口桌面来进行修改，经常修改，之前下载docker一直失败，现在可以正常下载。
> 
> 
> **就是我们使用阿里云镜像加速来解决这个问题**
> 

首先，我们先获取阿里云docker加速链接，我们[点击这里](https://cr.console.aliyun.com/cn-hangzhou/instances/mirrors)，来获取阿里云加速链接。点击链接后，我们登陆注册后，是这个页面

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/不使用SSH，加速群晖Docker镜像源/20211119214904.png)

然后我们打开docker

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/不使用SSH，加速群晖Docker镜像源/20211119215039.png)

点击注册表里，然后打开设置

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/不使用SSH，加速群晖Docker镜像源/20211119215117.png)

选择第一个源，然后打开编辑

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/不使用SSH，加速群晖Docker镜像源/20211119215127.png)

点击启动注册镜像，然后将我们获得的阿里云的注册链接填进去，保存，就可以了