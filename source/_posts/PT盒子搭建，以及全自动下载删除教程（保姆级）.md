---
title: PT盒子搭建，以及全自动下载删除教程（保姆级）
tags:
  - PT
  - Linux
  - Flexget
  - Deluge
  - AutoRemove
  - seedbox
  - 刷流
categories: seedbox
description: 如何成为一名优秀的刷子（
top_img: 'https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT盒子搭建，以及全自动下载删除教程/c4ca4238a0b9.png'
cover: 'https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT盒子搭建，以及全自动下载删除教程/c4ca4238a0b9.png'
toc: true
copyright_author: mouzhai
copyright_info: 此文章版权归 mouzhai 所有，如有转载，请注明来自原作者
abbrlink: f07b
copyright_author_href: 'https://zhaiblog.cn/author/1'
copyright_url: 'https://zhaiblog.cn/76.html'
date: 2021-10-25 21:10:32
---
## **前言：**

Hello 大家好，这里是一名折腾党，从入坑NAS七天，从I3 3220T 更换 J3455 再更换到I3 8100T，总算是硬解够用，硬解够用了就要找电影，然后就找到了PT站点，但是我家的小水管上传这么慢，该怎么解决呢！！！网上一顿查资料，查到了很多盒子教程啊，但是都不怎么全，有人说用星大的一键就行了，也有人说用Quickbox-lite，于是我去HZ买了一台服务器（{% span red, 这篇主要是讲解如何搭建，就不讲解如何购买，如何挑选服务器了 %}），试了quickbox-lite，试了星大的脚本，也试过swizzin的脚本，总结了几个点，quickbox-lite安装后很吃CPU资源，我24欧元的服务器（E3，具体什么型号忘记了，已经换37欧的服务器了），安装后CPU负载一直在10以上(后来发现是硬盘问题，速度太慢了)，我当时就想，这个web监控页面，也没什么具体的用，又吃资源，对于我来说没什么用，还有安装的flexget配置文件一直搞不对！！重装系统，装软件浪费了我三天的时间，后来我就放弃了用quickbox-lite，完全不会用。。。。废话不多说开始我们的教程

本次教程使用以下软件：

1. 星大脚本
2. Deluge（PT下载软件）
3. Flexget（RSS自动更新软件）
4. AutoRemove（自动删除软件）
5. PT站点我以馒头为示例

实现以下功能：

1. 下载（废话）
2. 自动添加最新种子
3. 根据条件删除已下载完，或者未下载完的种子

解放双手，解放大脑，让我们做一个全自动刷子！

## **重装系统，做raid0 ，安装bbr加速**

### **进入救援模式**

HZ拿到手后，他会发送给你root密码，但是！！我一次都没有通过它给的密码进去过！！重装系统也是，所以这次我们不用他面板提供的重装系统，采用的是quickbox-lite的脚本一键重装系统和安装bbr，首先进入hz的robot界面

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT盒子搭建，以及全自动下载删除教程/c4ca4238a0b9.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT盒子搭建，以及全自动下载删除教程/c4ca4238a0b9.png)

找到左边的Server，就会显示你购买的服务器，点一下你购买的服务器，然后选择Rescue，这个Rescue是**{% span red, 下一次重启 %}**后进入救援页面，我们选择Linux 64bit，然后点击Activate rescue system

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c81e728d9d4c.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c81e728d9d4c.png)

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/eccbc87e4b5c.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/eccbc87e4b5c.png)

接下来，他会给你一个救援密码，这个密码复制到笔记本上面记好，后面要用

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/a87ff679a2f3.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/a87ff679a2f3.png)

选择救援模式后，我们重启服务器，进入救援模式

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/e4da3b7fbbce.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/e4da3b7fbbce.png)

### **1.2. 重装系统，安装BBR加速**

到这里，我们的服务器就已经进入了救援模式，然后通过FinalShell远程连接至服务器，用户名为root，密码是当时出现的救援密码，进入系统后，什么都不要输入，直接输入一键重装系统脚本

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/1679091c5a88.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/1679091c5a88.png)

重装为Debian 10命令（二选一即可）：

```
echo x | installimage -p /boot:ext3:1G,/:ext4:all -l 0 -r yes -i images/Debian-1010-buster-64-minimal.tar.gz  -a -n Hz && reboot
```

Ubuntu 18.04命令：

```
echo x | installimage -p /boot:ext3:1G,/:ext4:all -l 0 -r yes -i images/Ubuntu-1804-bionic-64-minimal.tar.gz -a -n Hz && reboot
```

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/8f14e45fceea.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/8f14e45fceea.png)

重装完成后，会自动重启，我重新链接，进入Debian系统，用户名是root，密码也是救援密码，进去后第一件事情就是修改密码！！  输入passwd，然后输入两次新密码即可

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c9f0f895fb98.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c9f0f895fb98.png)

接下来我们安装魔改版bbr加速

```
bash <(wget -qO- https://git.io/AccTCP -o /dev/null)

```

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/45c48cce2e2d.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/45c48cce2e2d.png)

输入3，选择南琴浪版本，然后系统会自动安装内核等一系列依赖，等待即可

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/d3d9446802a4.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/d3d9446802a4.png)

到这一步，我们的魔改版BBR就已经安装完了，接下来就是安装星大的Deluge和flexget的一键安装脚本即可

星大github地址：https://github.com/Aniverse/inexistence

原版一键命令：

```
bash <(wget --no-check-certificate -qO- https://github.com/Aniverse/inexistence/raw/master/inexistence.sh) \
-y --tweaks --bbr --rclone --no-system-upgrade --flexget --tr-deb --filebrowser \
--de 1.3.15 --rt 0.9.8 --qb 4.1.9 -u 这十二个字换成你的用户名 -p 这十个字换成你的密码
```

我们要去掉一些不要的东西啊，比如说qbittorrent,fileborser,tr, rclone, bbr  等一系列东西，最后精简出下面这条命令，将汉字替换成自己的用户名和密码

```
bash <(wget --no-check-certificate -qO- https://github.com/Aniverse/inexistence/raw/master/inexistence.sh) \
-y --tweaks --no-system-upgrade --flexget \
--de 1.3.15 -u 用户名 -p 密码
```

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c6bff625bdb0.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c6bff625bdb0.png)

回车之后，他会问你是否安装Qbittorrent，rTorrent，Transmission，我们不需要这些，所以全部输入99，然后就问你需不需安装FileBrowser，我们也不需要 选择no，回车过后，系统就进入了一键配置状态，等待安装完毕，他会告诉你后台地址，把后台地址复制下来，避免忘记了。

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c20ad4d76fe9.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c20ad4d76fe9.png)

安装完毕后的界面

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c51ce410c124.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c51ce410c124.png)

到此为止，Deluge安装好了，Flexget也安装好了，我们进入下一步 配置Deluge和Flexget进行自动下载

## **配置Deluge**

我们通过   你服务器IP:8112  进入Deluge后台，一定要先配置好Deluge，因为一旦你开始下载后，你就会发现你的Deluge Web总是断开，就没办法配置了！  我们点击preferences 进入设置

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/aab3238922bc.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/aab3238922bc.png)

选择Itconfig ，然后右边选择High Performance Seed，点击Load Preset  加载配置，然后我们进行一个逐步优化

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/9bf31c7ff062.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/9bf31c7ff062.png)

优化参数（部分参数找不到，这个我也不知道怎么搞，目前我是一条一条搜索 然后替换值，如果大家有更好的办法，可以告诉我），取自于 https://blog.stomtian.com/index.php/pt/28/

```
active_limit = 2000;
active_seeds = 2000;
allow_multiple_connections_per_ip: true
auto_upload_slots = false;
cache_buffer_chunk_size = 128;
cache_expiry: 120
cache_size: 512000;
choking_algorithm: 1;
close_redundant_connections = true;
enable_incoming_utp:false;
enable_outgoing_utp:false;
file_pool_size = 500;
inactivity_timeout = 20;
low_prio_disk: false;
max_failcount = 1;
max_rejects = 10;
max_queued_disk_bytes: 262144000;
max_queued_disk_bytes_low_watermark: 131072000;
optimize_hashing_for_speed = true;
read_cache_line_size = 512;
request_timeout = 10;
peer_timeout = 20;
seed_choking_algorithm: 1;
send_buffer_low_watermark: 13107200;
send_buffer_watermark: 26214400;
send_buffer_watermark_factor: 250;
strict_end_game_mode: false;
use_parole_mode: false;
use_read_cache = true;
write_cache_line_size = 512;
```

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c74d97b01eae.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c74d97b01eae.png)

Ctrl+F  一个个查找 并且修改值，前面要打对勾，最后选择Apply 保存应用，Deluge就已经配置完了，接下来我们配置Flexget

## **配置Flexget**

网址：IP:9566   进入后台，用户名为：flexget   密码为自己设置的，进入后，直接点击左边的Config配置文件

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/70efdf2ec9b0.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/70efdf2ec9b0.png)

进入config后，Deluge模板 星大已经帮我们配置好了，我们只需要设置下载规则，以及定时规则即可，进去后往下拉，把我用红框框勾选的区域，全部删掉

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/6f4922f45568.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/6f4922f45568.png)

删除后呢，将配置改成我这个样子，【】的地方填写你们的信息

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/1f0e3dad9990.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/1f0e3dad9990.png)

接下来逐个讲解一下这几个参数的含义

- tasks 这个是任务的标记 任务从在此标记后填写，一般不用改动
- ManTou 这个是一个任务的名字，可以随意更改，但是后面要对应上，我只用来刷馒头，所以就只写了个拼音
- rss rss相关信息在此标签后
- url rss的url链接 请务必把【你的RSS链接】 这一句话删除掉，然后再填写你的链接，如何提取rss链接，请参考**底部常见事项**
- ascii 编码 不用管
- headers 请求头部 不用动
- Cookie 站点的cookie 一般用来模拟你的操作，如何抓取cookie请参考**底部常见事项**
- accept_all 表示下载所有新种子，不做任何拦截
- template 用什么下载器模板 这里我们装的是deluge，所以我们填上de
- deluge 关于deluge的相关操作在此标签后
- label 所有添加的任务都打上auto标签，这个可有可无，你改成其他的也行 不写也行 都无所谓
- schedules 定时任务标签，默认是no
- tasks 执行的任务名称，对应上面的任务名字
- interval 执行周期标签
- minutes 这里我填写的1 是指每1分钟执行一次，能够快速的抓取新种子，但是对于有些站点来说 频率太快就类似于CC攻击，所以这里适量调整5-15分钟即可

schedules是自动执行任务的标签，这里我们可以用crontab代替，但是我安装的debian  用crontab好像出了点问题，就用这个代替了，用crontab的时候，可以把这里填写no，然后添加flexget的命令，网上有，我这里就不说了

好了 以上就是这个模板的配置说明了，因为这是简单配置，我们追求的是能跑 ， 能快速上手，所以配置都比较简单，如果有多个站点，就多添加tasks即可，更加复杂的参数这里就不多说了，说了很多人都不想看下去了，先跑起来 然后以后再考虑，这样 我们的配置文件就写完了。 点击上面的Save Config   当你点击完之后，Flexget就已经开始运行了，他会一分钟执行一次抓取任务，并且添加到Deluge

### **可选项**

如果你不想下载已有的种子，只想下载新种子，那么你可以选择左边菜单栏的Tasks,按照以下几个步骤执行，他会将已经抓取的种子记录下来，然后不下载，等到新种子来了就会下载新种子，执行完毕后，也可以在该页面查看日志，添加了多少个种子 等

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/98f137082101.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/98f137082101.png)

## **配置AutoRemove-torrents**

我们回到FinalShell对服务器进行安装AutoRemove-torrents

AutoRemove-torrents GitHub网址：https://github.com/jerrymakesjelly/autoremove-torrents

文档提供了两种方式供我们安装，我选择最简单的一种 pip安装

```
pip install autoremove-torrents
```

一顿操作之后，系统就已经自动安装好了

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/37693cfc7480.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/37693cfc7480.png)

然后我们查找一下这个目录在哪里，后面要用到的

```
find / -name 'autoremove-torrents'
```

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/1ff1de774005.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/1ff1de774005.png)

可以看到有一个是flexget里的 这个我们不要，我们要第一个，把路径记录下来 我们后面要用到

然后去写配置文件

执行以下命令

```
cd
mkdir AutoRemove
cd AutoRemove
touch config.yml
```

接下来我们用FinalShell对config.yml进行写入

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/8e296a067a37.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/8e296a067a37.png)

如果root目录下没有AutoRemove这个文件夹 点击刷新一下就会出来了，然后我们右键config.yml，选择以文本编辑器打开，并把一下代码粘贴进去

```
My_AutoRemove:
client: Deluge
host: 127.0.0.1:58846
username: 【用户名】
password: 【密码】
strategies:
My_strategy:
remove: (seeding_time > 3600 and ratio < 0.02) or (seeding_time > 18000 and ratio < 0.3) or (seeding_time > 36000 and ratio < 0.5) or (seeding_time > 259200 and ratio < 3) or (seeding_time > 604800)
free_space:
min: 100
path: 【下载路径】
action: remove-big-seeds
delete_data:true
```

里面有三个参数需要大家自己填写，分别是用户名，密码，和deluge的下载路径，下载路径可以在deluge的设置里看到，粘贴进去就行了

我对该配置文件讲解一下，

- My_AutoRemove 这个是任务名称 随便起
- client 下载器，我们这里用的Deluge
- host 不用动，这是默认的
- stratagies 开始条件 固定写法
- My_strategy 名称 随便改
- remove 删除条件，该条件为 时间大于1小时**且**分享率低于0.2 **或者** 时间大于5小时且分享率低于0.3 或者 时间大于10小时**且**分享率低于0.5 **或者** 时间大于72小时（三天）**且**分享率小于3 **或者** 时间大于168小时（七天）的种子和文件都会被**删除 这里条件可以自己改，具体怎么改请参考作者github**
- free_space 剩余空间
- min 最小剩余空间 单位为GB
- path 监控路径
- action 首先删除什么类型的种子 我这里填写的是时间比较久的，大家可以自行更改
- delete_data 删除种子的时候删除数据

OK这个就是AutoRemove的删除配置了，我自己写的，写的不是怎么好，而且不是很严谨，如果大家有更好的配置文件，可以在评论区评论出来，我们一起讨论，优秀的配置文件将会被重新开贴存档！！

我们把配置文件写完 保存后，百分之99的工作已经做完了，然后执行以下命令

```
cd /root/AutoRemove
autoremove-torrents --view
```

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/4e732ced3463.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/4e732ced3463.png)

当我们看到这个提示信息的时候，说明Autoremove配置文件没有出问题，可以正常运行，然后进行最后一步，定时任务

```
crontab -e
```

然后再敲一次回车，默认是nano编辑器编辑

将以下代码粘贴进去

```
 */15 * * * * 【上面找到的autoremove-torrents的路径】 --conf=/root/AutoRemove/config.yml --log=/root/AutoRemove
#我找到的在/usr/local/bin目录下，所以这么填，你们请填自己找到路径（按照我这个步骤装的，应该也是在当前目录，可以参考我的）
 */15 * * * * /usr/local/bin/autoremove-torrents --conf=/root/AutoRemove/config.yml --log=/root/AutoRemove
```

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/02e74f10e032.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/02e74f10e032.png)

然后Ctrl+X  ，输入Y  回车，保存crontab文件

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/33e75ff09dd6.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/33e75ff09dd6.png)

显示这个就代表已经更新了定时任务，这个任务是每隔15分钟执行一次删除任务，配置文件在root下的AutoRemove下的config配置文件，日志在AutoRemove文件夹下，大家可以把15改成1，然后看看有没有日志产生，如果有日志产生说明定时没有问题，再把1改成15就可以了

## **结尾**

该教程到这里就已经结束了，按道理来说你的Deluge+Flexget+AutoRemove已经可以正常运行了，实现了自动添加最新种子，删除没有上传的种子，空间不足删除旧种子等一系列功能

馒头刷流，一定要开会员，否则流量超了号被ban，别找我！！

别问我为什么底下rss订阅只订阅了大姐姐，因为大姐姐流量大！

这里呢是个技术宅，没有什么本事，只喜欢瞎折腾，敲敲代码，祝大家早日毕业馒头站点~    **底下的常见事项一定要多看几遍！！！  很多问题都会在里面写清楚，并且会持续更新！！大家有什么问题可以在评论区留言！**

## **常见事项**

1. **如何生成Rss链接？**

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/6ea9ab1baa0e.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/6ea9ab1baa0e.png)

点击右上角这个符号，然后把相关板块勾上，数量根据你的服务器配置选择，选择在20-50之间，然后选择生成链接

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/3c59dc048e88.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/3c59dc048e88.png)

获取的链接我们只要底下一个，不要第一个

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/b6d767d2f8ed.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/b6d767d2f8ed.png)

这样 我们就获取到了我们想要的rss链接了~

### **如何获取Cookie**

按F12，或者右键审查元素，检查等，进入控制面板，然后找到NetWork（又叫网络）这个选项，然后把数据包都清空掉，我图片有

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/34173cb38f07.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/34173cb38f07.png)

然后我们**刷新页面**，选择第一个数据包，往下拖，就可以看到cookie了，把双引号里面的所有内容全部复制下来就是cookie了

![https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c16a5320fa47.png](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/PT%E7%9B%92%E5%AD%90%E6%90%AD%E5%BB%BA%EF%BC%8C%E4%BB%A5%E5%8F%8A%E5%85%A8%E8%87%AA%E5%8A%A8%E4%B8%8B%E8%BD%BD%E5%88%A0%E9%99%A4%E6%95%99%E7%A8%8B/c16a5320fa47.png)

### **常见问题**

1.为什么我的服务器这么卡？ 照你这个操作一套下来，连SSH都连不上去了！！你是不是在我服务器里中病毒了！！挖矿了！！

> 答： 因为你的带宽都跑满了，CPU都跑满了，HZ服务器又是德国的，线路很差，所以连不上去，你可以在服务器上面挂个探针来监控服务器信息，比如我这样 点我
> 

2.你这个Flexget，AutoRemove配置太辣鸡了！！来点高级的行不行！！

> 兄弟萌，评论区来点高级的配置行不行！
> 

3.为什么带宽跑不满？

> 带宽跑不满是因为连不上人家，主要是跑大包，几台盒子互刷产生的流量，所以说刷的流量基本上都是盒子互刷的，对国内帮助不是很大！如果想跑满带宽，请发种！
>