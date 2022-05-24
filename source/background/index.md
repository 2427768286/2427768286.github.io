---
title: butterfly 主题背景更换
date: 2021-08-07 04:57:01
updated:
type:
comments: false
description:
keywords:
top_img: https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/78og7w.jpg
mathjax:
katex:
aside:
aplayer:
highlight_shrink:
---

<style>@keyframes gradientBG{0%{background-position: 0% 50%;}50%{background-position: 100% 50%;}100% {background-position: 0% 50%;}}#rightside{display:none;}</style>

> 这个页面是用来测试渐变背景的效果，以及不同透明度的效果。如果你有能力可以直接看 css 样式。否则请返回[Hexo 博客之 butterfly 主题优化更换背景](https://www.antmoe.com/posts/7198453/index.html#附录)复制代码。
> 阅读体验及个标签样式请自己进行调整。

## 透明度调节

<center style='margin-bottom:20px' id = 'opt'><a style="color: #FFF;margin-bottom: 10px;"  style="color: #FFF;" href="#" class="button button-primary button-rounded button-small" data-opacity="0">透明度0</a><a style="color: #FFF;margin-bottom: 10px;"  style="color: #FFF;" href="#" class="button button-primary button-rounded button-small" data-opacity="0.1">透明度0.1</a><a style="color: #FFF;margin-bottom: 10px;"  style="color: #FFF;" href="#" class="button button-primary button-rounded button-small" data-opacity="0.2">透明度0.2</a><a style="color: #FFF;margin-bottom: 10px;"  style="color: #FFF;" href="#" class="button button-primary button-rounded button-small" data-opacity="0.3">透明度0.3</a><a style="color: #FFF;margin-bottom: 10px;"  style="color: #FFF;" href="#" class="button button-primary button-rounded button-small" data-opacity="0.4">透明度0.4</a><a style="color: #FFF;margin-bottom: 10px;"  style="color: #FFF;" href="#" class="button button-primary button-rounded button-small" data-opacity="0.5">透明度0.5</a><a style="color: #FFF;margin-bottom: 10px;"  style="color: #FFF;" href="#" class="button button-primary button-rounded button-small" data-opacity="0.6">透明度0.6</a><a style="color: #FFF;margin-bottom: 10px;"  style="color: #FFF;" href="#" class="button button-primary button-rounded button-small" data-opacity="0.7">透明度0.7</a><a style="color: #FFF;margin-bottom: 10px;"  style="color: #FFF;" href="#" class="button button-primary button-rounded button-small" data-opacity="0.8">透明度0.8</a><a style="color: #FFF;margin-bottom: 10px;"  style="color: #FFF;" href="#" class="button button-primary button-rounded button-small" data-opacity="0.9">透明度0.9</a><a style="color: #FFF;margin-bottom: 10px;"  style="color: #FFF;" href="#" class="button button-primary button-rounded button-small" data-opacity="1">透明度1</a></center>

## 背景调节

<div id='demo_style' style='text-align:center;margin:0 auto;'>


### 渐变类

<div data-type="photo" class='bg_test' style="display:inline-block;width: 200px;height:200px;background: url(&quot;https://ae01.alicdn.com/kf/H5662031fbf344418aa2c8bf74c68826eV.png&quot;),linear-gradient(45deg, #6dd0f2 15%, #f59abe 85%);text-align: center;line-height: 200px;margin-bottom:5px;cursor: pointer;">粉蓝色有图片</div>

<div data-type="photo" class='bg_test' style="display:inline-block;width: 200px;height:200px;background: linear-gradient(45deg, #6dd0f2 15%, #f59abe 85%);text-align: center;line-height: 200px;cursor: pointer;">粉蓝色无图片</div>

<div data-type="photo" class='bg_test' style="display:inline-block;width: 200px;height:200px;background: linear-gradient(102.7deg,#fddaff 8.2%,#dfadfc 19.6%,#adcdfc 36.8%,#adfcf4 73.2%,#caf8d0 90.9%);text-align: center;line-height: 200px;cursor: pointer;">美美哒渐变</div>

<div data-type="color" class='bg_test' style="display:inline-block;width: 200px;height:200px; background: linear-gradient(90deg,rgba(247,149,51,.1) 0,rgba(243,112,85,.1) 15%,rgba(239,78,123,.1) 30%,rgba(161,102,171,.1) 44%,rgba(80,115,184,.1) 58%,rgba(16,152,173,.1) 72%,rgba(7,179,155,.1) 86%,rgba(109,186,130,.1) 100%);text-align: center;line-height: 200px;cursor: pointer;">博主同款</div>

<div data-type="photo" class='bg_test' style="display:inline-block;width: 200px;height:200px; background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);    background-size: 400% 400%;animation: gradientBG 15s ease infinite;text-align: center;line-height: 200px;cursor: pointer;">动态渐变</div>

<div data-type="photo" class='bg_test' style="display:inline-block;width: 200px;height:200px; background: linear-gradient(to right bottom, rgb(0, 255, 240), rgb(92, 159, 247) 40%, rgb(211, 34, 255) 80%);text-align: center;line-height: 200px;cursor: pointer;">紫蓝色渐变</div>

### 渐变加图片类

<div data-type="photo" class='bg_test' style="display:inline-block;width: 200px;height:200px; background: linear-gradient(60deg, rgba(255, 165, 150, 0.5) 5%, rgba(0, 228, 255, 0.35)), url(https://ae01.alicdn.com/kf/H18a4b998752a4ae68b8e85d432a5aef0l.png),url(https://ae01.alicdn.com/kf/H21b5f6b8496141a1979a33666e1074d9x.jpg)0% 0% / cover;text-align: center;line-height: 200px;cursor: pointer; background-size: cover;">紫蓝色渐变</div>

### 图片类

<div data-type="photo" class='bg_test' style="display:inline-block;width: 200px;height:200px; background: url(https://api.abcyun.co/api/tool/bing/token/5d8f31cf6a8ab);text-align: center;line-height: 200px;cursor: pointer; background-size: cover;">必应壁纸</div>

<div data-type="photo" class='bg_test' style="display:inline-block;width: 200px;height:200px; background: url(https://api.abcyun.co/api/others/randacgimage/token/5d8f31cf6a8ab);text-align: center;line-height: 200px;cursor: pointer; background-size: cover;">随机二次元图</div>

<div data-type="photo" class='bg_test' style="display:inline-block;width: 200px;height:200px; background: url(https://api.abcyun.co/api/others/randacgblogbg/token/5d8f31cf6a8ab);text-align: center;line-height: 200px;cursor: pointer; background-size: cover;">随机二次元背景图</div>

</div>

## 测试文章

### 春

盼望着，盼望着，东风来了，春天的脚步近了。

一切都像刚睡醒的样子，欣欣然张开了眼。山朗润起来了，水长起来了，太阳的脸红起来了。

小草偷偷地从土里钻出来，嫩嫩的，绿绿的。园子里，田野里，瞧去，一大片一大片满是的。坐着，躺着，打两个滚，踢几脚球，赛几趟跑，捉几回迷藏。风轻悄悄的，草绵软软的。

桃树、杏树、梨树，你不让我，我不让你，都开满了花赶趟儿。红的像火，粉的像霞，白的像雪。花里带着甜味，闭了眼，树上仿佛已经满是桃儿、杏儿、梨儿。花下成千成百的蜜蜂嗡嗡地闹着，大小的蝴蝶飞来飞去。野花遍地是：杂样儿，有名字的，没名字的，散在花丛里，像眼睛，像星星，还眨呀眨的。

“吹面不寒杨柳风”，不错的，像母亲的手抚摸着你。风里带来些新翻的泥土的气息，混着青草味，还有各种花的香，都在微微润湿的空气里酝酿。鸟儿将窠巢安在繁花嫩叶当中，高兴起来了，呼朋引伴地卖弄清脆的喉咙，唱出宛转的曲子，与轻风流水应和着。牛背上牧童的短笛，这时候也成天在嘹亮地响。

雨是最寻常的，一下就是三两天。可别恼。看，像牛毛，像花针，像细丝，密密地斜织着，人家屋顶上全笼着一层薄烟。树叶子却绿得发亮，小草也青得逼你的眼。傍晚时候，上灯了，一点点黄晕的光，烘托出一片这安静而和平的夜。乡下去，小路上，石桥边，撑起伞慢慢走着的人;还有地里工作的农夫，披着蓑，戴着笠的。他们的草屋，稀稀疏疏的在雨里静默着。

天上风筝渐渐多了，地上孩子也多了。城里乡下，家家户户，老老小小，他们也赶趟儿似的，一个个都出来了。舒活舒活筋骨，抖擞抖擞精神，各做各的一份事去，“一年之计在于春”;刚起头儿，有的是工夫，有的是希望。

春天像刚落地的娃娃，从头到脚都是新的，它生长着。

春天像小姑娘，花枝招展的，笑着，走着。

春天像健壮的青年，有铁一般的胳膊和腰脚，他领着我们上前去。

{% note default icon %}
default
{% endnote %}

{% note primary icon %}
primary
{% endnote %}

{% note success icon %}
success
{% endnote %}

{% note info icon %}
info
{% endnote %}

{% note warning icon %}
warning
{% endnote %}

{% note danger icon %}
danger
{% endnote %}

{% note primary no-icon%}

#### Primary Header**Welcome** to [Hexo!](https://hexo.io)

{% endnote %}


<script>var article_container=document.getElementById("demo_style"),opt=document.getElementById("opt");article_container.addEventListener("click",function(e){var t=e.target;"DIV"===t.nodeName&&"bg_test"===t.className&&(web_bg.style.background=t.style.background,web_bg.style.animation=t.style.animation),Cookies.set("bg",t.style.background,{expires:1}),Cookies.set("animation",t.style.animation,{expires:1}),Cookies.set("type",t.getAttribute("data-type"),{expires:1})}),opt.addEventListener("click",function(e){var t=e.target;if("A"===t.nodeName){var a=t.getAttribute("data-opacity");if(a){Cookies.set("opacity",a,{expires:1});var n="--light_bg_color: rgb(255, 255, 255,"+a+");",i="--dark_bg_color: rgba(18,18,18,"+a+");";document.getElementById("content-inner").setAttribute("style",n+i)}}e.preventDefault()});</script>