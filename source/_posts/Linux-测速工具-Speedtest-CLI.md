---
title: Linux 测速工具 Speedtest-CLI
tags:
  - Linux
  - Speedtest
categories: Linux
description: Linux内安装&使用Speedtest-CLI
top_img: 'https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/Linux测速工具Speedtest-CLI20220525093647.png'
cover: 'https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/Linux测速工具Speedtest-CLI20220525093752.png'
toc: true
copyright_author: kysdm
copyright_info: 此文章版权归 kysdm 所有，如有转载，请注明来自原作者
abbrlink: '204'
copyright_author_href: 'https://blog.kysdm.com/'
copyright_url: >-
  https://blog.kysdm.com/2020/11/04/Linux%E6%B5%8B%E9%80%9F%E5%B7%A5%E5%85%B7-Speedtest-CLI/
date: 2022-05-24 18:26:46
---
# 安装

### pip

```bash
pip install speedtest-cli
```

### easy_install

```bash
easy_install speedtest-cli
```

### GitHub

```bash
pip install git+https://github.com/sivel/speedtest-cli.git
```

或者

```bash
git clone https://github.com/sivel/speedtest-cli.git
cd speedtest-cli
python setup.py install
```

### 从 GitHub 下載

```bash
wget -O speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py
chd +x speedtest-cli
```

或者

```bash
curl -Lo speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py
chmod +x speedtest-cli
```

# 使用

### 直接运行

```bash
speedtest-cli
```

### 输出截图

```bash
speedtest-cli --share
```

### 查询可用的测速服务器

```bash
speedtest-cli --lis
```

### 指定测速服务器

```bash
speedtest-cli --server <服务器ID>
```

# 开源项目地址

[https://github.com/sivel/speedtest-cli](https://github.com/sivel/speedtest-cli)
