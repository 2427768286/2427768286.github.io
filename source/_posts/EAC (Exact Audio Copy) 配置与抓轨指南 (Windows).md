---
title: EAC (Exact Audio Copy) 配置与抓轨指南 (Windows)
tags:
  - EAC
  - CD
  - WIN
  - FLAC
  - 抓轨
categories: 技术教程
description: 教你快速学会使用EAC抓取分轨FLAC
top_img: 'https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/1v6dfo.jpg'
cover: 'https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/1v6dfo.jpg'
toc: true
copyright_author: DICMusic
copyright_author_href:
copyright_url:
copyright_info: 此文章版权归 DICMusic 所有，如有转载，请注明来自原作者
abbrlink: 5a9
date: 2021-08-06 04:09:31
updated:
keywords:
comments:
toc_number:
copyright:
mathjax:
katex:
aplayer:
highlight_shrink:
aside:
---
<!-- wp:paragraph -->
<p>本教程旨在让你成为一名优秀的抓轨者，让你抓出 100% Log 的音轨。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>绿色方框表示必须按图设置；橙色方框表示必须按光驱的具体型号设置。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
## 安装与设置
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
### 1. 下载并安装 EAC
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>本教程基于 1.6 版本，此处附上&nbsp;<a rel="noreferrer noopener" target="_blank" href="https://www.fosshub.com/Exact-Audio-Copy.html?dwl=eac-1.6.exe">EAC 1.6</a>&nbsp;的下载链接。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在开始安装前有这样一个界面，方框中是可选组件，你至少要勾选 freedb Metadata Plugin、CDRDAO、AccurateRip、CTDB Plugin。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/ct26x9.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>如果你没单独装过 FLAC 那么就请勾上它。但建议不要安装 GD3 Metadata Plugin，因为这个服务只能供你免费查询 10 张专辑，此后要付费 $7.99。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>注意：该版本 EAC 所整合的 FLAC 组件是 1.3.2 版本，而最新版本是 1.3.3（<a href="https://pan.baidu.com/s/1f4FKpBweeayQnrUuNhhbyw" target="_blank" rel="noreferrer noopener">海豚工具箱</a>（提取码：pif4 / 解压码：STDM）&nbsp;提供了由&nbsp;<a href="https://dicmusic.club/user.php?action=search&amp;search=Aoba_xu">Aoba_xu</a>&nbsp;编译完成的 1.3.3 的 .exe 程序），在算法上有一定提升。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 2. 设置读取采样偏移校正值
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>读取采样偏移校正值在后文中会简称为「偏移值」。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>首次启动 EAC 时，你会看到如下界面，请直接点「取消」。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/26h5vg.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>接着，将一张流行的原版 CD 放进光驱中。然后可能出现两种情况。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
#### 2.1. 你的光驱在 AccurateRip 中有记录
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>你会看到以下界面。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/h05z51.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>注意：</strong>如果上图没有出现，就更换光碟直至出现为止。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>点击「Configure」按钮，然后过大概一分钟，这段时间里你的光驱会比较吵闹，而后会弹出这个窗口：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/94y4br.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>点「确定」即可。但如果你已经安装了旧的 EAC，那么 AccurateRip会已经配置好，上图便不会出现。<br> <br><strong>2.2. 你的光驱在 AccurateRip 中无记录</strong>:&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
#### 2.2. 你的光驱在 AccurateRip 中无记录
<!-- /wp:heading -->

{% hideToggle %}

<!-- wp:paragraph -->
<p>（以下提及的 CD 都须是流行的原版 CD，亦即软件所提的「Key Disc」）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在你放入第一张 CD 之后，CD 的信息会从数据库回传并自动填充。此时 EAC 会弹出一个窗口（如果没有弹出，就换一张 CD，一直换到弹出下图为止），其内容如下：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/75w07x.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>点击「Configure」。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/m3m4q8.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>好，换了一张 CD（也有可能是两三张，如果没反应就多换几张），这次它弹出的窗口是这样：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/7c2s12.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>再次「Configure」，然后弹出下图：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/m3m4q8.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>它一共需要三张「Key Disc」来确认光驱偏移值，我们已经放了两张，而且都得到了相同的光驱偏移值结果，再放一张，只要测算的偏移值和前两张相同，就可以了。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/7c2s12.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>「Configure」。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/09u0ly.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>这表明你已经成功完成了设置。</p>
<!-- /wp:paragraph -->

{% endhideToggle %}

<!-- wp:heading {"level":4} -->
### 3. 下载并读取配置文件
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>访问&nbsp;<a href="https://pan.baidu.com/s/1G2VppAUBJUnF5IJX_F_KsQ" target="_blank" rel="noreferrer noopener">百度网盘</a>（提取码：485i）以下载配置文件。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>随后「读取配置文件」：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/2zmxp8.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>在弹出的对话框中找到你下载的「EACProfile.cfg」文件并打开之，绝大部分设置就会配置完成。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
#### 3.1. 外部压缩程序
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>将「压缩程序及路径」定位到 EAC 目录下「flac」文件夹内的 flac.exe 文件，或是你自己在其他路径下存放的 flac.exe。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/734f44.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>最后单击「测试编码器」按钮，确保「没有错误发生」：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/2711b5.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":5} -->
#### 3.2. 额外的外部压缩程序（可选）
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如有<strong>同时</strong>抓取另一格式的需求，勾选「使用额外的外部压缩机」选项，并按与 3.1 相同的流程设置并验证即可：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/y5rxs8.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
### 4. EAC 选项
<!-- /wp:heading -->

<!-- wp:heading {"level":5} -->
#### 4.1. 目录
<!-- /wp:heading -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/o7n7by.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>作为良好的抓轨实践，「使用指定目录」，将所有专辑有序放置在同一个主文件夹内显然是个不错的管理措施，当然，也许你会有自己的其他设计，只需要在这里简单修改即可。但如果你的电脑存储环境变动非常频繁，「每次询问」也许更合适。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
#### 4.2. 文件名
<!-- /wp:heading -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/031j5k.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>勾选「使用多艺术家命名方案」后，在不同音轨之间艺术家有区别时会激活这里的预设命名格式。是否勾选「使用多艺术家命名方案」完全是你的自由。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>文件夹命名方式请阅读&nbsp;<a href="https://dicmusic.club/wiki.php?action=article&amp;id=6#_286252953">发种命名规则</a>（重要），一般而言，使用前文列举的格式已经足够，在特定情形下，还可以往尖括号内加入特定发行年份（注意与原始发行年份的区别）、特定发行类型（包括但不限于豪华版、周年纪念版、初回限定盘、日版、引进版等）。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>注意：</strong>请务必保证「文件名」和「附加文件名」选项卡中的「命名方案」存在差异，否则，同时生成的两种格式的两份 Log 文件会合并在一起影响 Logchecker 评分。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此外，如果你是一位胆敢挑战古典音乐的勇士，请务必<strong>认真阅读</strong><a href="https://dicmusic.club/wiki.php?action=article&amp;id=75">古典音乐上传指南</a>&nbsp;和&nbsp;<a href="https://dicmusic.club/wiki.php?action=article&amp;id=78">古典音乐元数据标签添加指南</a>。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
#### 4.3. 附加文件名
<!-- /wp:heading -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/580jn9.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>它和「额外的外部压缩程序」选项卡是 EAC 1.5 与 1.3 最大的差别所在。简而言之，通过额外的压缩程序和文件名设置，EAC 能够同时输出两种格式的抓轨结果，通常我们只需要 FLAC，当然，你也可以按需开启额外项并使用其他不同的格式。该选项卡的作用，是设置额外压缩程序输出文件的文件和文件夹名。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 5. 驱动器选项
<!-- /wp:heading -->

<!-- wp:heading {"level":5} -->
#### 5.1. 抓取模式
<!-- /wp:heading -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/55a60o.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>如图勾选即可。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
#### 5.2. 驱动器
<!-- /wp:heading -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/38l74c.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>点击「现在自动检测读取指令」即可。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>勾选「驱动器支持 CD-Text 读取」，如果你的光驱支持该功能，可能会在 Cue 文件中多一些有效信息：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/i758st.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>如果你的光驱抓取缓慢，可以尝试勾选「抓取之前先转动驱动器」，有可能加快抓取速度（仅仅是可能，同时会令光驱发出较大的噪声）。一般来说新购买的光驱不会需要这个选项。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
#### 5.3. 偏移/速度
<!-- /wp:heading -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/71060g.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>如果你按教程步骤进行，一开始就配置好了 AccurateRip 与偏移值，那么上半部分就会如图一样灰掉。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>关于「通读到 Lead-In 和 Lead-Out」的详细分析，请见&nbsp;<a href="https://dicmusic.club/forums.php?action=viewthread&amp;threadid=1363">本文</a>。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
#### 5.4. 间隙检测
<!-- /wp:heading -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/95xs4k.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>这样的选项对大部分光驱都适用，但如果你在后面的「检测间隙」步骤或者在检查明显有问题的间隙时卡住了，那就试试「检测方法 B」或「检测方法 C」吧。如果还是不行就换个光驱；如果怎么整都不行，那就只能跳过这一步了。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
### 详细步骤，一般用于排查问题
<!-- /wp:paragraph -->

{% hideToggle %}

<!-- wp:heading {"level":4} -->
<p><strong>3. EAC 选项</strong></p>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>该章节所有需要进行的设置都可以在左上方的「EAC」栏目下找到。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>先打开「EAC选项」，所有没在截图中提及的项目都是可选项或对抓轨结果无影响，但请确保提及的内容按照绿色方框进行勾选。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/7mt3l0.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>如图设置即可。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/hw2pod.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>如图设置即可。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/25vib5.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>勾选「创建 Cue 文件时寻找 UPC/ISRC 代码」和「创建 Cue 文件时使用 CD-Text 信息」对抓轨速度和最终结果没有影响，如果你的光驱支持这两个功能，就会在 Cue 中添加它们的信息，如果不能，也不会有任何损失。不过勾选这两项后，所生成的 Cue 文件中有可能会附带 cataLog 和 ISRC 等信息（有没有还得看 CD 本身是否附带）。下图是勾选和未勾选在 Cue 文件中差异的体现：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/i758st.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>勾选「使用 UTF8 编码写入 m3u 播放列表文件」对于抓取非本国语言、非英文专辑时非常有用。就我的实践经历来看，默认的 GBK 编码在遇到韩文专辑时会无能为力，韩文字符会在 .m3u 文件中以「.」呈现，导致无法正确读取。而勾选后，它们就能够正常显示而无需任何额外的操作。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>另外，建议勾选「抓取时，在后台启动外挂压缩队列」这一选项，因为我们采用的压缩参数需要消耗较多的时间，如果光驱本身的抓轨速度又比较慢，同时进行可以节省一些时间。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/5g3y38.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>如图设置即可。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/3pgj4n.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>上图是命名音轨文件的方式。「使用多艺术家命名方案」可以勾选，因为有些「群星 (Various Artists / V.A.)」的 CD 里面会用到这种命名规范，不勾选也是可以的，也许还更加好看一些。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>请一定<strong>不要</strong>用下划线替换空格，那看起来真的糟糕透了。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<p><strong>4. 驱动器选项</strong></p>
<!-- /wp:heading -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/55a60o.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>勾选「[精确流]特性」，绝大多数现代光驱都有此功能。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>即使你的光驱不能缓冲音频数据，也请勾选「驱动器可以缓冲音频数据」。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>即使检测结果显示驱动器具备纠正 C2 错误报告能力也请不要勾选该选项，因为大多数光驱的这项功能很糟糕。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/38l74c.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>点击「现在自动检测读取指令」即可，别的都不用点。如果你想试一下你的光驱是否能够读取 CD-Text，那就勾选「驱动器支持 CD-Text 读取」，如果能，那最好，不能，就别选。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果你的光驱抓取缓慢，可以尝试勾选「抓去之前先转动驱动器」，有可能加快抓取速度（仅仅是可能，同时会令光驱发出较大的噪声）。一般来说新购买的光驱不会需要这个选项。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/71060g.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>如果你按教程所说一开始就配置了 AccurateRip，那么上半部分就会如图一样灰掉。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/95xs4k.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>这样的选项对大部分光驱都适用，但如果你在后面的「检测间隙」这一步或者在检查明显是有问题的间隙的时候停住了，那就试试「检测方法 B」或者「检测方法 C」吧。如果还是不行就换个光驱；如果都不行，那就只能把碟子换掉了。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<p><strong>5. 压缩选项</strong></p>
<!-- /wp:heading -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/734f44.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>如果你自己已经安装了 FLAC，那么自己找到 flac.exe 的路径。如果你是随着 EAC 安装的 FLAC，那么它就在 EAC 目录中的 FLAC 文件夹内。此处设置的比特率高低不影响抓轨质量。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>不同版本的 EAC 的「附加命令行选项」不同，要按版本设计其参数，否则会提示出错。该命令行适用于自 EAC 1.0 beta 2 至最新版，内容如下：<br><code>-8 -e -p -V -T "ARTIST=%artist%" -T "TITLE=%title%" -T "ALBUM=%albumtitle%" -T "DATE=%year%" -T "TRACKNUMBER=%tracknr%" -T "GENRE=%genre%" -T "COMMENT=%comment%" -T "BAND=%albuminterpret%" -T "ALBUMARTIST=%albuminterpret%" -T "COMPOSER=%composer%" %haslyrics%--tag-from-file=LYRICS="%lyricsfile%"%haslyrics% -T "DISCNUMBER=%cdnumber%" -T "TOTALDISCS=%totalcds%" -T "TOTALTRACKS=%numtracks%" %hascover%--picture="%coverfile%"%hascover% %source% -o %dest%<br></code><br>直接复制粘贴即可，注意命令行前后不要留有空格。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>「-8」后面加上的「-e」，其作用是开启穷举模型搜索，压制会需要更长时间（并不会长多少），压缩率也可能会略有提高（仅仅只是可能）。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/4uet6e.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>推荐命名方案是「%albumartist% - %albumtitle%」。具体怎么设置看你的个人需要了，并不影响抓轨质量。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<p><strong>6. 元数据选项</strong></p>
<!-- /wp:heading -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/306h5r.jpgjpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>先在「选择源数据源」选择「CueTools DB Metadata Plugin V2.1.6」，再点击「显示所选元数据源的选项」。在下图点选「Extensive」，然后「OK」。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/3h3q5p.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>然后在「选择源数据源」选择「freedb 元数据插件」，点击「显示所选元数据源的选项」，确定其中内容与下图保持一致。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/w6xbva.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/29i9w7.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>如图设置。邮箱填符合格式的（甚至不必确实存在），「确定」即可。</p>
<!-- /wp:paragraph -->

{% endhideToggle %}

<!-- wp:heading {"level":3} -->
## 抓轨
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>初始设置完成，以后抓轨只要从此开始即可。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 1. 获取 CD 的标签信息
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>EAC 自带多个数据源：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/f853z5.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>但往往不及 Gracenote 数据库全面准确，所以我们建议不使用自带的数据源，而是采用下面的第一种方式。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
#### 1.1. 通过 CD 播放软件 player 获取（推荐）
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>首先，前往&nbsp;<a rel="noreferrer noopener" target="_blank" href="http://vuplayer.com/files/playersetup.exe">官网</a>&nbsp;下载 player 这款软件并安装之。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/zx5q97.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>安装完成后，以<strong>管理员</strong>身份运行之。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>首先注册 Gracenote。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/ym1oq3.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>只需要下一步和同意就可以完成注册。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/07hqln.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>随后你就可以选择「Retrieve Disc Info」来获取 CD 信息了。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/13zqst.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>而后输出 CD 信息。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/93o2vr.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>点击之后没有任何提示，但 CD 信息已经成功导出，接下来切换到 EAC 界面，从 CDPLAYER.INI 获取 CD 信息即可完成导入：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/bbsy35.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>这里会跳出一个警告：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/z9800p.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>这里的翻译并不准确，删除的只是与 CD 相关的元数据，而不是 CD 本身存储的音频数据，元数据是可以随意改变的，所以放心大胆点「是」就可以。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Gracenote 提供的专辑信息不带有发行年，还请自行查阅填写上。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>有时，Gracenote 提供的信息会将艺术家信息也写在「音轨标题」字段内，这往往发生在多艺术家专辑的情况下，<strong>建议</strong>将艺术家信息正确拆分到「艺术家」字段中。<strong>快捷操作</strong>:&nbsp;</p>
<!-- /wp:paragraph -->

{% hideToggle %}

<!-- wp:paragraph -->
<p>面对如下图所示的情况：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/z55i35.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>点击「数据库」→「转换当前 CD 信息」→「分割音轨信息为艺术家/标题」，然后检查元数据是否正确拆分，如出现艺术家与音轨标题信息填反的情况：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/8ow6n3.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>则需点击「数据库」→「转换当前 CD 信息」→「交换艺术家 &lt;-&gt; 标题」：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/7h6waw.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>如此即可方便快捷地正确拆分艺术家与音轨标题信息。</p>
<!-- /wp:paragraph -->

{% endhideToggle %}

<!-- wp:paragraph -->
#### 1.2. 其他获取方式:&nbsp;
<!-- /wp:paragraph -->

<p>其他获取方式:&nbsp;</p>

{% hideToggle %}

<p><strong>1.2. 通过内建 FreeDB 引擎获取</strong></p>

<!-- wp:paragraph -->
<p>要选择最精确的版本。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/3r1e69.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>随后便会自动填充完成。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
<p><strong>1.3. 通过 CueTools DB Metadata Plugin V2.1.6 获取</strong></p>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>方法与前者大同小异，依旧要选择最接近你的 CD 的版本。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/g1zv4w.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>确认之后，它就会自动填充，之后你再裨补缺漏即可。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>个人认为这个匹配系统更为优秀，因为它提供了 CD 的目录号，这个可以在 CD 的封底找到。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
<p><strong>1.4. 通过 MusicBrainz 元数据插件获取</strong></p>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>点击后会弹窗询问你是否要现在搜索封面图片：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/stwp97.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>你完全可以选「是」来体验一下 EAC 自带的封面搜索引擎：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/umdn4g.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>确实有和我们的专辑相关的封面图，但品质实在是乏善可陈，所以我并不很推荐这个，你完全可以在浏览器上自行搜索高清封面。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>之后就会自动填充专辑信息。</p>
<!-- /wp:paragraph -->

{% endhideToggle %}

<!-- wp:heading {"level":4} -->
### 2. 正确设置抓轨文件夹名
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>打开「EAC」→「EAC 选项」→「文件名」选项卡，你看到的界面应如下图所示：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/031j5k.png" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>配置文件中已经提供好的<br><code>%albumartist% - %albumtitle% (%year%) {Record Label, Catalog Number, CD} [FLAC]\%tracknr2%. %artist% - %title%</code><br>提供了一种非常详实的命名格式，所得到的结果用中文表达出来就是<br><code>专辑艺术家 - 专辑标题 (发行年) {唱片厂牌, 目录编号, CD} [FLAC]\音轨序号. 音轨艺术家 - 音轨标题</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>当你收藏了某一专辑的多种不同媒介、版本、格式时，如此详实的命名格式就能方便你快速找到自己想要的特定文件夹。每次抓轨前，你都需要根据实际情况手动输入<strong>唱片厂牌</strong>和<strong>目录编号</strong>去替代「Record Label」和「Catalog Number」部分，因为它们不是变量。如下例：<br><code>%albumartist% - %albumtitle% (%year%) {ShrineLot, SLCD-0002, CD} [FLAC]\%tracknr2%. %artist% - %title%</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>如果你根本不知道唱片厂牌（Record Label）和目录编号（Catalog Number）是什么，<strong>你可以将尖括号部分整个删掉不填</strong>，这同样符合站点的发布规则</strong>，形如：<br><code>%albumartist% - %albumtitle% (%year%) [FLAC]\%tracknr2%. %artist% - %title%</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>认真填写该部分的好处在于，能够方便地分清不同的专辑发行，而且这个信息会被写入 Log 文件，即使文件夹名被人改得面目全非，只要 Log 未经改动，了解相关知识的用户就能获取到这个原始信息，用以确认具体发行，还有就是显得你很专业。请阅读&nbsp;<a href="https://dicmusic.club/wiki.php?action=article&amp;id=27#_2145676585">本文</a>&nbsp;简单了解唱片厂牌和目录编号的含义。当然，确实有些专辑不提供这两项信息，如确实没有，请省略。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>温馨提示：在你了解含义且确认唱片厂牌和目录编号准确无误再填写，如填写的信息有误（如将一串无关字符当做目录编号填入）会导致种子被标记为「可替代」，因为文件夹名有问题。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 3. 检测间隙、检测静音间隙和创建 Cue 目录文件
<!-- /wp:heading -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/ztrfwb.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>确保按图勾选。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>首先「检测间隙」，然后「检测静音间隙」（这关系到抓轨质量，必点），再然后创建「多个带间隙的 WAV 文件…（非规则）」Cue 文件（会出现在步骤 4.1 指定的目录里），放到专辑文件夹中（马上移进去或是抓完再移进去都可以）。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果你没有检测间隙，间隙处理的选项就会灰掉：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/8ledmb.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
### 4. 开始抓轨
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>真正的抓轨终于开始了，我们可以选择抓取方式，具体如下：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/wj72w1.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>确保所有音轨都已经选中且勾选了「追加间隙到上一轨（缺省）」，点击「测试并抓取所选音轨」→「已压缩…」。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>注意不要放在含有你名字或透露你个人信息的路径里面，因为这个路径信息会同时出现在 Log 文件里，Log 文件是<strong>绝对不允许</strong>更改的。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>根据电脑配置的不同和音轨时长的差异，抓轨有快有慢，通常需要约一小时。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>至此，EAC 的设置以及初次抓轨完成。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在抓轨文件夹中会可能生成 GBK 编码的 Cue 和 M3u8 文件（日文和中文曲目名的专辑会生成 GBK 编码的它们，如果是纯英文名的专辑，就直接会生成 UTF-8 的 Cue 和 M3u8）。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>有时，在抓轨完成后，AccurateRip 数据库会请你上传一些相关的信息：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/yxakxx.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>「Submit Now」就可以。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 5. 抓轨后的处理
<!-- /wp:heading -->

<!-- wp:heading {"level":5} -->
#### 5.1. Cue 文件
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>按指南生成的 Cue 的主要用途是刻录，而不是播放列表（M3u8 文件才是播放列表）。Cue 文件在保存时应注意其命名，可采用「艺术家 - 专辑名.cue」的形式，有如「GARNiDELiA - Violet Cry.cue」，如此可与 Log 和 M3u 文件名统一，保持美观；也可以「Noncompliant.cue」为名，描述其实际类型。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
#### 5.2. 专辑封面
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>专辑封面能直观地给人以这张专辑的第一印象，有时，也影响着听众的实际体验。在发布时，我们要求只要能找到封面，就应当填写，所以，现在就找一张高清封面显然是明智之选，推荐的获取途径有：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>虾米音乐：封面一般质量相对较好且容易获取</li><li>亚马逊：封面以高清大图居多，如果是日本亚马逊，需要挂梯子才能访问</li><li>iTunes：封面非常高清，也许你还要自己缩小处理，通过&nbsp;<a rel="noreferrer noopener" target="_blank" href="https://i.oppsu.cn/">这个网站</a>&nbsp;即可快速搜索、下载</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>获取之后，如果比例和 1:1 差不离，你可以手动切成 1:1，当然，不切也完全没问题，命名为「Cover」或「Folder」即可。如果想要将封面内嵌进音频文件（这样做的好处在于，能够使存入移动播放器的音频文件显示封面图），需注意其大小不能超过 1024 KB，具体操作方法见&nbsp;<a href="https://dicmusic.club/wiki.php?action=article&amp;id=66">本文</a>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>但是整个教程如此繁琐，你在第一次尝试时可能会有一些小失误，那要如何知道自己是否有缺漏的步骤呢？下面提供自检方法。</p>
<!-- /wp:paragraph -->

<!-- wp:nextpage -->
<!--nextpage-->
<!-- /wp:nextpage -->

<!-- wp:heading {"level":4} -->
### 6. 自检
<!-- /wp:heading -->

{% hideToggle %}

<!-- wp:paragraph -->
<p>如果以上所有内容你都完全相同地设置了，那么你的 Log 文件将会包含以下信息（分值表示其重要性）：</p>
<!-- /wp:paragraph -->
```
<pre class="wp-block-preformatted">Exact Audio Copy V1.3 from 2. September 2016
——EAC 的版本号。
EAC extraction Logfile from 27. August 2017, 15:05
——抓轨时间，若与文件的最终修改时间相同，则基本可确认是原始 Log。
RADWIMPS / 君の名は。
——专辑艺术家和标题。
Used drive  : hp      CDDVDW GP70N   Adapter: 1  ID: 0
——光驱品牌型号，因人而异。但如果是虚拟光驱载入镜像抓轨，则会显示 Virtual Drive，请牢记：用虚拟光驱抓轨是不被允许的。

Read mode               : Secure（请务必保证相同）
——读取模式：可靠，说白了就是安全模式，这个是必须的。
Utilize accurate stream : Yes（请务必保证相同）
——使用精确流：是（20 分），光驱的一种提高抓轨精确度的功能。
Defeat audio cache      : Yes（请务必保证相同）
——清空音频缓存：是（10 分）
Make use of C2 pointers : No（请务必保证相同）
——使用 C2 指示器：否（20 分）
Read offset correction                      : 6（偏移值因人而异）
——读取偏移校正：6（5 分），因光驱型号而异，是开启 AccurateRip 的基本要求。
Overread into Lead-In and Lead-Out          : No（请务必保证相同）
——读取 Lead-In 和 Lead-Out：否
Fill up missing offset samples with silence : Yes（请务必保证相同）
——用静音填充抓取中丢失偏移的采样：是（5 分）
Delete leading and trailing silent blocks   : No（请务必保证相同）
——去除首尾静音块：否（5 分），即不删除开头和结尾处的静音部分。
Null samples used in CRC calculations       : Yes（请务必保证相同）
——在 CRC 计算中使用了空样本：是（1 分）
Used interface                : Native Win32 interface for Win NT &amp; 2000
——已用接口：Win NT 及 2000 本地 Win32 接口
Gap handling                     : Appended to previous track（请务必保证相同）
——间隙处理：追加到上一曲目（仅分轨抓取显示该设置），这是为了原样保留各音轨的前后静音。

Used output format              : User Defined Encoder
——所用输出模式：用户定义的编码器
Selected bitrate                : 1024 kBit/s
——已选比特率：1024 kBit/s
Quality                         : High
——质量：高
Add ID3 tag：No（请务必保证相同）
——添加 ID3 标签：否（1 分）
Command line compressor   : D:\Exact Audio Copy\Flac\flac.exe
——命令行压缩器：D:\Exact Audio Copy\Flac\flac.exe
Additional command line options （附加命令行参数）: -8 -e -p -V -T "ARTIST=%artist%" -T "TITLE=%title%" -T "ALBUM=%albumtitle%" -T "DATE=%year%" -T "TRACKNUMBER=%tracknr%" -T "GENRE=%genre%" -T "COMMENT=%comment%" -T "BAND=%albuminterpret%" -T "ALBUMARTIST=%albuminterpret%" -T "COMPOSER=%composer%" %haslyrics%--tag-from-file=LYRICS="%lyricsfile%"%haslyrics% -T "DISCNUMBER=%cdnumber%" -T "TOTALDISCS=%totalcds%" -T "TOTALTRACKS=%numtracks%" %hascover%--picture="%coverfile%"%hascover% %source% -o %dest%

Track  1
    Filename E:\音乐\你的名字。\01 - 夢灯籠.wav
    Pre-gap length  0:00:02.00
    Peak level 100.0 %
——峰值电平，这与音频内容本身有关，不影响抓轨质量。
    Extraction speed 2.5 X
——抓轨速度。
    Track quality 100.0 %
——音轨质量，每多读取一次这个值就会减小 0.1%，但是最终读取出来的数据一定是准确的，即便不是 100% 也无妨。
    Test CRC 777FB55E
    Copy CRC 777FB55E（测试与抓取 10 分）
——测试 CRC 值和抓取 CRC 值，同一曲目的两个 CRC 值应当完全相同。
    Accurately ripped (confidence 142)  [D47291F0]  (AR v2) （5 分）
——说明开启了 AccurateRip，而且有相应的匹配数据。
    Copy OK
……
Track 27
    Filename E:\音乐\你的名字。\27 - なんでもないや (movie ver.).wav
    Pre-gap length  0:00:01.41
    Peak level 100.0 %
    Extraction speed 6.1 X
    Track quality 100.0 %
    Test CRC 269D3AAB
    Copy CRC 269D3AAB
    Accurately ripped (confidence 138)  [98D346A9]  (AR v2)
    Copy OK

All tracks accurately ripped
No errors occurred
End of status report

---- CueTools DB Plugin V2.1.6
[CTDB TOCID: c4iyYrxODAOFzESTkKujjx5tJss-] found
Submit result: c4iyYrxODAOFzESTkKujjx5tJss- has been confirmed
Track | CTDB Status
 1   | (2911/2922) Accurately ripped
……
27   | (2720/2922) Accurately ripped, or (19/2922) differs in 2976 samples @05:43:64-05:43:68, or (35/2922) differs in 4308 samples @05:43:62-05:43:68, or (28/2922) differs in 4302 samples @05:43:62-05:43:68, or (5/2922) differs in 2838 samples @05:43:64-05:43:68, or (15/2922) differs in 4404 samples @05:43:62-05:43:68, or (10/2922) differs in 2946 samples @05:43:64-05:43:68, or (2/2922) differs in 3530 samples @05:43:63-05:43:68, or (30/2922) differs in 2858 samples @05:43:65-05:43:69, or (11/2922) differs in 4310 samples @05:43:62-05:43:68, or (2/2922) differs in 4284 samples @05:43:61-05:43:67
——该示例统计数字表示安装了 CTDB 插件的人中有 2922 人抓了这张碟，其中曲目 1 有 2911 人和你的抓轨结果相同；在曲目 27 产生了较多分歧。产生不同的原因可能有：① 相异的人抓轨出了错误；② 同一专辑在不同地区发行的版本乃至同一地区的再版所造成的差异。

======Logchecksum59D417F4A5CC5B0628FB81D8CFAC2FF9C0FEA15675272611E91B48ABCF744489 ======（15 分）
——Log 文件自身的校验值，如果 Log 文件中的内容被改动过，所计算出的校验值和最后附的校验值就对不上了，所以不要改动 Log 文件！不要改动 Log 文件！不要改动 Log 文件！
</pre>
```
{% endhideToggle %}

<!-- wp:paragraph -->
<p><strong>常见问题解答</strong>:&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
## 常见问题解答
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
### 1. 到底什么是 Key Disc？为什么要使用流行的原版 CD 作为 Key Disc？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>流行是为了保证网络上已经有该 CD 的数据能够进行比对；原版是为了保证来源的准确性。在翻录过程中，很有可能会因为不同的光驱偏移值不同而造成 CD 信息与原版 CD 不完全一致导致偏移值结果不准确。因此请不要放入小众的、新出的以及引进版的 CD。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Key Disc 名单：<a rel="noreferrer noopener" target="_blank" href="http://www.accuraterip.com/keydiscs.htm">http://www.accuraterip.com/keydiscs.htm</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 2. 为什么要正确设置偏移值？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>偏移值的设置是一项至关重要的设置，它能影响到能否无损抓轨，但是很多人忽略这一点，他们的 Log 中该项数值为0，这导致他们的抓轨结果并不准确。差不多每个驱动器都不能将读取头准确地定位在所要的扇区。对数据 CD 光盘来说这不是一个大问题，因为每个扇区都含有定位信息，所以驱动器可以很容易地找到正确的扇区。与之相反，音乐 CD 不含有扇区的位置信息，也就是说对音乐 CD 来说定位一个扇区是非常困难的。这就是驱动器在读取音乐 CD 时会产生偏移的原因。对多数现代光驱来说这个偏移是个定值，因此一旦你知道了这个值就可以纠正偏移产生的误差。<a rel="noreferrer noopener" target="_blank" href="https://www.accuraterip.com/driveoffsets">这个网站</a>&nbsp;可以查到市面上绝大多数光驱的偏移值。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>设置正确的偏移值不需要理由，不设置才需要，显然除了懒和无知以外没有别的解释。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 3. 光驱无记录时跳出来的一长段英文窗口是什么意思？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>此 CD 可用于配置 AccurateRip。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>AccurateRip 包含来自世界各地的人的抓轨结果，从而可以用以指出你的抓轨结果是否 100% 准确无误（错误来源于 CD 表面的划痕）。但在你的抓轨结果加入数据库前，必须确定你的光驱偏移值。详情请访问官网。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>光驱类型：示例光驱；预期偏移量：未知</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>注意事项：如果要求放入额外的「Key CD」，请不要放入含有两张 CD 的专辑中的另一张。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>是否立即配置 AccurateRip？ [需要 5 秒]</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 4. 偏移值对抓轨所得音乐文件本身有何影响？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>不同的光驱，偏移也可能会有不同，在读取偏移设置不正确的情况下，抓出来的文件也会有不同的，只有设置了正确的偏移，抓取出来的文件才会是相同且是正确的。（但也有一种情况，就是两个光驱的偏移都是同样的，即使偏移都是 0，抓取出来的文件是同样的，但不代表抓取出来的文件是正确的。）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>不过这个偏移设置对虚拟光驱无效。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 5. 为什么要「总是使用英语创建日志文件」？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>这可以保证 EAC 的界面是简体中文或者是别的你所需要的语言，但是能够生成英文的 Log 文件（如果不采用英文，可能在外国朋友的电脑上显示一堆乱码，这往往会带来诸多不便）。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/8qb342.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>日本朋友提供的日语 Log 往往会像上图那样让人觉得不知所云，修复的办法也是有的，用 UniCue 这个小工具就能做到。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>现在版本的 EAC 生成的 Log 都是 UTF-16 编码，因此能够准确显示各种语言，但英文总归方便一些。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 6. 为什么不勾选「标准化」？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>原因是我们期望的结果是精确的 CD 抓取，而不是经过任何修改后的版本（即使你觉得修改过的版本更好）。何况即使需要标准化或者增益，也可以由播放器实时完成，没必要对抓取的音轨进行不可逆的修改（破坏）。想都别想，不要勾选！</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 7. 为什么一定要勾选「驱动器可以缓冲音频数据」？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>你的光驱也许能缓冲，也许不能缓冲。不能缓冲，这个选项是无所谓的，但如果能缓冲且没有勾选，那么它的缓冲功能就会产生作用。在使用安全模式抓取的情况下，对于每一段音频数据光驱会读取至少两次，若不同，则继续读取直到有 50% 以上的采样完全相同为止，不过最多不超过 82 次，以求得到尽可能精确的结果，当光驱支持精确流特性时可以确保这一点。如果光驱对音频数据进行缓冲，那么之后的每一次读取都是在和第一次的结果进行比对，如果第一次就错了，那后面读取的参照标准就不对，自然不可能得出正确结果。如果你勾选了「驱动器可以缓冲音频数据」，那么 EAC 就会通过初始化光驱来避免这种情况发生。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 8. 为什么不开启 C2 纠错功能？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在所有的只读光盘中有至少两个等级的纠错方式，名为 C1 和 C2。如果两者都失败了，那么输出就很可能不正确。大部分光驱并不能报告读取正确与否，所以每一个块需要被读取两遍并且相互比较来确保没有错误。但是有些更新的光驱在读取时能够报告 C1/C2 错误的具体位置，使得只读取一遍且找出读取错误成为可能。但是这仍然有一个问题，由于一些光驱不能正确地报告这些错误，所以你应该在相信报告结果之前先认真确认一下该功能。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 9. 为什么在压缩时不使用 CRC 校验？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>因为 FLAC 自带 MD5 校验。因此在将 WAV 文件转码为 FLAC 文件时务必不要用格式工厂等杂七杂八的软件，因为它们调用的并不是 FLAC.exe。这很可能会导致差错。而通过 foobar2000 调用 FLAC 来进行压缩则没有这方面的担忧。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 10. 为什么要检测间隙？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>正确的间隙检测所带来的正确曲目分割点以及正确曲目长度都是你所需要的结果，追加间隙到上一轨的意义在于这样做对聆听影响最小，但又不会改变音轨的总时长。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此外，有一些 CD 很特殊，它们可能在间隙中藏匿了特典曲目，如果不检测间隙，那么这些隐藏的好东西会被直接抛弃，这与我们获取可靠抓轨结果的理念背道而驰。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 11. 为什么生成的 Cue 文件不能在一些播放软件中打开使用？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>因为所生成的非规则 Cue 文件在 CD 有间隙时是不应当作播放列表用的，M3U8 才是，而且绝对不能修改，因为非规则 Cue 是用来刻录 CD 而非播放的。如果需要兼容播放软件的 Cue，可以选择生成「单个的 WAV 文件…」。「多个已去除间隙的 WAV 文件…」和「多个带已校正间隙的 WAV 文件…」也不能用以播放。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 12. FLAC 格式的优势主要在哪里？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>FLAC 内建 MD5 校验机制，WAV 则无此特性。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>校验用批处理文件的代码如下：<br><code>attrib /s /d -r *.flac<br>"D:\Exact Audio Copy\FLAC\flac" -t *.flac<br>pause</code><br>只需要将引号内的路径更改为你存储 flac.exe 文件的路径，用 .txt 编写完代码以后保存，更改文件名的后缀「.txt」为「*.bat」即可。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>特别注意：FLAC 的 MD5 校验只能检查在生成该文件后数据是否有变化，不能检测真假无损。检测专辑的可靠性可以使用&nbsp;<a href="https://dicmusic.club/wiki.php?action=article&amp;id=28">CueTools</a>&nbsp;这款软件。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 13. 这样复杂冗长的设置真的能获取到无损的抓轨结果吗？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>能。EAC 开发出来的初衷便是为了无损的抓轨。CD 以二进制形式存储数据，我们要做的是将之丝毫不差地复制到电脑上，因此我们通过种种看似复杂实则必要的设置保证复制的准确性。在明白了原理之后，我们可以说，在教程的每项设置都达成的情况下，无论你用的是 200 元的普通光驱，还是 3000 元的昂贵光驱，所得的抓轨结果是<strong>没有任何区别</strong>的。所以如果有人告诉你，抓轨需要某高端设备（对，我就是在说艾利和牌抓轨机），会受到电源影响，需要这个，需要那个，等等……你知道实际上怎么回事的，对吧。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>不过，当碟面状况非常糟糕时，使用不同的光驱多次尝试或许是个解决之道，另外，不同型号的光驱抓轨的速度会有所差异。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 14. 为什么抓取整轨的时候 Log 中没有关于间隙处理方式的状态显示？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>因为 EAC 1.3 抓取整轨时会自动检测间隙并把间隙信息写到 Cue，每个音轨的 INDEX00 和 INDEX01 之间的时间差就是间隙。你也可以先手动检测间隙再抓取，都是可以的。在 EAC 的「操作」菜单下选择「去除间隙」或「追加间隙到上一轨」或「追加间隙到下一轨」对抓整轨时如何在 Cue 中记录间隙没有影响。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 15. 偏移值已经变灰，但是因为特殊需求想要更改，该怎么办？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>偏移值设定存储在注册表中，路径：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>计算机\HKEY_CURRENT_USER\Software\Illustrate\dBpowerAMP</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>文件夹下的 CD-DriveSampleOffset-盘符:\[光驱型号] 中，其存储的数值即为读取采样偏移校正值，不过没有特殊需要请不要去动它。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/k5543a.jpg" alt=""/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
### 16. 我要怎么知道 Log 文件是否被篡改？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>请参阅&nbsp;<a href="https://dicmusic.club/wiki.php?action=article&amp;id=287">EAC / XLD Log 可信度检测指南</a>&nbsp;一文。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
### 17. 切换「外部压缩程序」选项卡时遭遇「错误的路径或程序！」报错，该怎么办？
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>取消「使用额外的外部压缩机」选项的勾选，然后点击「确定」试试。</p>
<!-- /wp:paragraph -->