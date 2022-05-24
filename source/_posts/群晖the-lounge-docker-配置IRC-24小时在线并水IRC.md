---
title: 群晖the lounge docker-配置IRC 24小时在线并水IRC
tags:
  - 群晖
  - synology
  - Linux
  - docker
  - irc
categories: 群晖
description: 氵氵更健康
top_img: >-
  https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC20211124122237.png
cover: >-
  https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC20211124122237.png
toc: true
copyright_author: 承世
copyright_info: 此文章版权归 承世 所有，如有转载，请注明来自原作者
abbrlink: 28c8
copyright_author_href: 'https://blog.shi.wiki/author/1/'
copyright_url: 'https://blog.shi.wiki/archives/3.html'
date: 2021-11-19 20:32:25
---
> the lounge 是一个irc聊天客户端，我们通过把the lounge配置到nas上，7*24小时运行，然后如果想水irc的话，直接连接the lounge的webui水irc，因为是是用webui进行水irc的，可以直接右键网页翻译
> 

之前本来是用的nas配置znc,znc挂载irc 7*24小时在线，然后是用 kiwiirc.com/web 客户端连接znc水irc，但是这两天kiwiirc连接znc不是很稳定，经常掉线。然后用hexchat客户端连接znc很稳定，但是hexchat使用体验我不是很满意，最主要的是他不是web,不可以使用浏览器的一键翻译。

经大佬们推荐，使用the lounge

本教程是在群晖系统，使用docker系统来实现的

# 安装docker

1、首先，我们要打开套件中心，安装docker，如图，如果已经安装的，直接看第3步

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119210731.png)

2、点击安装docker就可以了

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119210901.png)

3、打开我们安装的docker，点击注册表，搜索thelounge，双击安装（如果下载或者搜索太慢，请参考此文-[不使用SSH，加速群晖Docker镜像源](https://blog.stardream.online/posts/d71a/)）

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119210922.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119210944.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119210956.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211006.png)

# 安装 thelounge 镜像

我们先新建一个文件夹，我们先打开file station，然后进入docker文件夹，新建一个名为thelounge的文件夹，然后再点击进入thelounge文件夹，新建一个config的文件夹

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211047.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211117.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211131.png)

然后我们接着打开docker程序，点击影响，双击刚才下好的thelounge，点击安装

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211138.png)

接着我们点击高级设置，然后点击卷，设置文件映射，文件路径就是我们刚才新建的文件夹，装载路径填写/config

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211153.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211200.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211209.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211216.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211223.png)

文件映射之后，我们设置下端口，容器端口不用动，本地端口设置成9000，然后点击应用就可以了，如果需要外网访问，我们还需要路由器设置端口转发，

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211232.png)

![路由器端口转发](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211241.png)

不过我们还没有搭建完好，现在是容器搭建好了，但是我们在里面连接上IRC服务器，并不会自动保存，等我们关闭浏览器进入web，还需要重新设置，

# 修改配置文件

这里，我们需要修改配置文件

我们进入/docker/thelounge/config文件夹，右键点击文件config.js的属性，修改权限，我们增加写入权限

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211250.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211322.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211337.png)

我们右击config文件的属性，查看config文件的位置，然后我们复制下载

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211345.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119211356.png)

接着我们打开putty，进入ssh,首先登陆自己的nas账号

然后输入sudo -i

接着输入密码，密码输入后看不到，密码就是自己的用户名的密码

然后cd /volume2/docker/thelounge/config（这个路径，就是自己刚才复制的路径）

输入ls

输入vim config.js

此时会进入一个文档，然后按键盘i键可以进入编辑

然后把public:true改成public:false

改好之后点击键盘Esc键，然后在输入：wq 就会完成保存并退出文档界面

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119213757.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119213808.png)

接着，我们输入docker ps

复制下我勾选的id

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119213815.png)

然后输入docker exec -it ea420165b82c s6-setuidgid abc thelounge add shi

ea420165b82c就是我们刚才复制的id,shi就是自己的用户名，我们可以根据喜好设置，然后会出现命令，让我们设置密码，我们设置自己的密码就可以，然后问是否写入磁盘，我们输入yes就可以

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119213821.png)

到这里，我们的配置就完成了，然后我们进入docker打开我们的容器，接着我们在浏览器输入ip:9000 ip+端口，就可以成功进入webui，然后我们登录上我们刚才新建的用户密码，进去自行配置自己的irc就可以了

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119213829.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/群晖the-lounge-docker-配置IRC-24小时在线并水IRC/20211119213839.png)

完结，撒花