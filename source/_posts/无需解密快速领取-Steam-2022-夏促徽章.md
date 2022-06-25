---
title: 无需解谜快速领取 Steam 2022 夏促徽章
tags:
  - Steam
  - F12
  - 2022
  - 夏促
categories: Steam
top_img: >-
  https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/无需解密快速领取-Steam-2022-夏促徽章/3J8_B{N5_H`KLI17OZP[O~M.png
cover: >-
  https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/无需解密快速领取-Steam-2022-夏促徽章/3J8_B{N5_H`KLI17OZP[O~M.png
toc: true
abbrlink: f51d
copyright_author_href: ''
copyright_url: ''
date: 2022-06-25 14:43:07
copyright_author:
copyright_info:
---
https://store.steampowered.com/sale/clorthax_quest

F12 打开控制台填入以下代码后 Enter 即可

```
let delay=(ms)=>new Promise((res)=>setTimeout(res,ms));await jQuery.post("/saleaction/ajaxopendoor",{"sessionid":g_sessionID,"authwgtoken":jQuery("#application_config").data("userinfo").authwgtoken,"door_index":0,"clan_accountid":41316928,});var i=1;for(let link of["/category/arcade_rhythm/?snr=1_614_615_clorthaxquest_1601","/category/strategy_cities_settlements/?snr=1_614_615_clorthaxquest_1601","/category/sports/?snr=1_614_615_clorthaxquest_1601","/category/simulation/?snr=1_614_615_clorthaxquest_1601","/category/multiplayer_coop/?snr=1_614_615_clorthaxquest_1601","/category/casual/?snr=1_614_615_clorthaxquest_1601","/category/rpg/?snr=1_614_615_clorthaxquest_1601","/category/horror/?snr=1_614_615_clorthaxquest_1601","/vr/?snr=1_614_615_clorthaxquest_1601","/category/strategy/?snr=1_614_615_clorthaxquest_1601",]){try{let html=await jQuery.get(link);await jQuery.post("/saleaction/ajaxopendoor",{"sessionid":g_sessionID,"authwgtoken":jQuery("#application_config",html).data("userinfo").authwgtoken,"door_index":jQuery("#application_config",html).data("capsuleinsert").payload,"clan_accountid":41316928,"datarecord":jQuery("#application_config",html).data("capsuleinsert").datarecord,});console.log('成功获取夏促悖论派对徽章：'+i);i++}catch(e){console.log('徽章获取失败了：'+i);i++}finally{await delay(1500)}}
```

{% folding green, 实际操作 %}
![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/无需解密快速领取-Steam-2022-夏促徽章/3J8_B{N5_H`KLI17OZP[O~M.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/无需解密快速领取-Steam-2022-夏促徽章/Q_C5VLTQ[}DJE7VOVU18ZRM.png)

![](https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/post/无需解密快速领取-Steam-2022-夏促徽章/E5JLLSGDATVE6ZYECV0${0I.png)
{% endfolding %}