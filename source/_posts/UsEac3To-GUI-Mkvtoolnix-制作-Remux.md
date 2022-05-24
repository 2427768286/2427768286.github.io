---
title: UsEac3To GUI + Mkvtoolnix 制作 Remux
tags:
  - Encode
  - 压制
  - Remux
categories: 压制
description: 使用 UsEac3To GUI + Mkvtoolnix 快速制作 Remux
top_img: 'https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/1mwr37.png'
cover: 'https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/1mwr37.png'
toc: true
copyright_author: TFboys
copyright_info: 此文章版权归 TFboys@GPW 所有，如有转载，请注明来自原作者
abbrlink: '4301'
date: 2021-09-05 07:05:23
copyright_author_href:
copyright_url:
---
<!-- wp:paragraph -->
<p>eac3to GUI 下载链接：</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><li>网盘链接：<a href="https://pan.baidu.com/s/1epmRnpmiepH_cT3JNJFEGQ" target="_blank" rel="noreferrer noopener">https://pan.baidu.com/s/1epmRnpmiepH_cT3JNJFEGQ</a> <strong>提取码</strong>: {% hideInline k2px %}</li><li>最新版本：<a rel="noreferrer noopener" target="_blank" href="https://www.videohelp.com/software/eac3to#download">https://www.videohelp.com/software/eac3to#download</a></li></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Mkvtoolnix-GUI 下载链接：</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><li>网盘链接：<a rel="noreferrer noopener" target="_blank" href="https://pan.baidu.com/s/1LiugV3iNf9ZwdBad1Mi7sg">https://pan.baidu.com/s/1LiugV3iNf9ZwdBad1Mi7sg</a> <strong>提取码</strong>: {% hideInline k4e7 %}</li><li>最新版本：<a rel="noreferrer noopener" target="_blank" href="https://mkvtoolnix.download/downloads.html">https://mkvtoolnix.download/downloads.html</a></li></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>对于一个看到各种命令行就头晕目眩的我实在是不太愿意去输入各种命令，所以 GUI 这个版本正是我这种手残党的救星，废话不多说下面就开始进入正式的教程了。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><li>首先把压缩文件解压至指定目录，这里要注意：文件路径中<strong>不要带中文</strong>，以及后面的教程中所使用的文件路径一律<strong>不要带中文</strong>，不然会出现各种奇奇怪怪的问题。</li><li>准备好 Remux 所需的原盘文件，IOS 格式原盘建议解压后操作。</li><li>打开 UsEac3To.exe ，把准备好的原盘文件夹夹拖入 UsEac3To 界面打开。</li>
{% hideToggle %}

<img alt="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/k00k5z.png" src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/k00k5z.png">

{% endhideToggle %}

<li>查看软件读取原盘个轨道的信息，结合站点的规则选择相应的轨道进行后续操作。（这是一部粤语电影，下面是所需要的轨道。）</li>

{% hideToggle %}

<li><img alt="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/1mwr37.png" src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/1mwr37.png">

{% endhideToggle %}

<ul><li>章节信息</li><li>视频轨道</li><li>TrueHD 格式音频 (粤语)</li><li>DTS HD MA 2.0 音频 (普通话)</li><li>PGS 格式字幕 (繁、简、英)</li></ul></li><li>在 Track Input and Output format 选项中选择需要的轨道添加代码进行输出，涉及到转码会用到 Frequent parameters / More parameters 参数选项。<ul><li>Chap → txt → Add #输出 txt 章节文件</li><li>h264 → h264 → Add #输出 h264 格式视频轨道</li><li>True → thd+ac3 → Add #输出一条原始 True 格式音轨和一条兼容性比较好的 AC3 音轨</li><li>DTS → flac → Add #当 DTS HD MA 音频为 1.0 / 2.0 声道时，转码为 FLAC 格式音频（后面继续添加 down16 可输出 16bit 音轨）</li>

{% hideToggle %}

<li><img alt="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/2wf649.png" src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/2wf649.png"></li>

{% endhideToggle %}

<li>DTS → dtshd → Add #输出原始 DTS HD MA 格式音轨</li><li>DTS → ac3 → Add #输出 640kbps AC3 格式音轨 （后面继续添加 448 可输出 448kbps 音轨）</li>

{% hideToggle %}

<img alt="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/26hq80.png" src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/26hq80.png">

{% endhideToggle %}

<li>DTS → m4a → Add #输出 aac 格式音轨 （后面继续添加 quality=0.35 可输出更小的aac音轨）</li>

{% hideToggle %}

<img alt="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/464dx1.png" src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/464dx1.png">

{% endhideToggle %}

<li>SUP → sup → Add #输出字幕</li><li>后面 gif 截图就是这部粤语电影使用 eac3to GUI 完整的操作过程</li>

{% hideToggle %}

<img alt="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/2o2g6v.gif" src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/2o2g6v.gif">

{% endhideToggle %}

<li>轨道提取完成后在 eac3to GUI 软件根目录下会生成 <strong>UsEac3To.log </strong>文件，打开 log 并备份信息（发布 Remux 附带 log 信息才可勾选「<strong>自制</strong>」标签）。</li></ul></li><li>使用 Mkvtoolnix-gui 进行打包，轨道封装顺序为（从上到下）：视频→主音轨→次音轨→中文字幕→英语字幕→小语种字幕，最后<a href="https://greatposterwall.com/wiki.php?action=article&amp;name=%E5%8F%91%E7%A7%8D%E5%91%BD%E5%90%8D%E8%A7%84%E5%88%99">《发种命名规则》</a>进行命名，这样就能获得一部自己制作的 Remux 啦（轨道名称 和 章节名称 建议用英文，这我偷懒了）</li><li><strong>阴间Gif</strong>: </li></ol>

{% hideToggle %}

<img alt="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/00k9i1.gif" src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/00k9i1.gif">

{% endhideToggle %}
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>教程中制作的 Remux</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://cdn.jsdelivr.net/gh/2427768286/STDM-imgs/images/20210905072044.png" alt=""/></figure>
<!-- /wp:image -->

{% hideToggle %}

```
General
Unique ID                                : 211290822955338703775330097723656826796 (0x9EF521DDC87663E3F05C29011AD6EFAC)
Complete name                            : xxx.mkv
Format                                   : Matroska
Format version                           : Version 4
File size                                : 21.4 GiB
Duration                                 : 1 h 43 min
Overall bit rate mode                    : Variable
Overall bit rate                         : 29.6 Mb/s
Encoded date                             : UTC 2021-08-17 17:28:05
Writing application                      : mkvmerge v60.0.0 ('Are We Copies?') 64-bit
Writing library                          : libebml v1.4.2 + libmatroska v1.6.4

Video
ID                                       : 1
Format                                   : AVC
Format/Info                              : Advanced Video Codec
Format profile                           : High@L4.1
Format settings                          : CABAC / 4 Ref Frames
Format settings, CABAC                   : Yes
Format settings, Reference frames        : 4 frames
Codec ID                                 : V_MPEG4/ISO/AVC
Duration                                 : 1 h 43 min
Bit rate mode                            : Variable
Bit rate                                 : 23.9 Mb/s
Maximum bit rate                         : 30.0 Mb/s
Width                                    : 1 920 pixels
Height                                   : 1 080 pixels
Display aspect ratio                     : 16:9
Frame rate mode                          : Constant
Frame rate                               : 24.000 FPS
Standard                                 : NTSC
Color space                              : YUV
Chroma subsampling                       : 4:2:0
Bit depth                                : 8 bits
Scan type                                : Progressive
Bits/(Pixel*Frame)                       : 0.480
Stream size                              : 17.2 GiB (81%)
Language                                 : Chinese
Default                                  : Yes
Forced                                   : No
Color range                              : Limited
Color primaries                          : BT.709
Transfer characteristics                 : BT.709
Matrix coefficients                      : BT.709

Audio #1
ID                                       : 2
Format                                   : MLP FBA
Format/Info                              : Meridian Lossless Packing FBA
Commercial name                          : Dolby TrueHD
Codec ID                                 : A_TRUEHD
Duration                                 : 1 h 43 min
Bit rate mode                            : Variable
Bit rate                                 : 4 036 kb/s
Maximum bit rate                         : 5 610 kb/s
Channel(s)                               : 6 channels
Channel layout                           : L R C LFE Ls Rs
Sampling rate                            : 96.0 kHz
Frame rate                               : 1 200.000 FPS (80 SPF)
Compression mode                         : Lossless
Stream size                              : 2.91 GiB (14%)
Title                                    : 粤语
Language                                 : Chinese
Default                                  : Yes
Forced                                   : No

Audio #2
ID                                       : 3
Format                                   : AC-3
Format/Info                              : Audio Coding 3
Commercial name                          : Dolby Digital
Codec ID                                 : A_AC3
Duration                                 : 1 h 43 min
Bit rate mode                            : Constant
Bit rate                                 : 640 kb/s
Channel(s)                               : 6 channels
Channel layout                           : L R C LFE Ls Rs
Sampling rate                            : 48.0 kHz
Frame rate                               : 31.250 FPS (1536 SPF)
Compression mode                         : Lossy
Stream size                              : 473 MiB (2%)
Title                                    : 粤语
Language                                 : Chinese
Service kind                             : Complete Main
Default                                  : No
Forced                                   : No

Audio #3
ID                                       : 4
Format                                   : FLAC
Format/Info                              : Free Lossless Audio Codec
Codec ID                                 : A_FLAC
Duration                                 : 1 h 43 min
Bit rate mode                            : Variable
Bit rate                                 : 905 kb/s
Channel(s)                               : 2 channels
Channel layout                           : L R
Sampling rate                            : 48.0 kHz
Frame rate                               : 11.719 FPS (4096 SPF)
Bit depth                                : 24 bits
Compression mode                         : Lossless
Stream size                              : 669 MiB (3%)
Title                                    : 普通话
Writing library                          : libFLAC 1.2.1 (UTC 2007-09-17)
Language                                 : Chinese
Default                                  : No
Forced                                   : No

Text #1
ID                                       : 5
Format                                   : PGS
Muxing mode                              : zlib
Codec ID                                 : S_HDMV/PGS
Codec ID/Info                            : Picture based subtitle format used on BDs/HD-DVDs
Duration                                 : 1 h 41 min
Bit rate                                 : 33.6 kb/s
Count of elements                        : 3182
Stream size                              : 24.4 MiB (0%)
Title                                    : 简体中文
Language                                 : Chinese
Default                                  : Yes
Forced                                   : No

Text #2
ID                                       : 6
Format                                   : PGS
Muxing mode                              : zlib
Codec ID                                 : S_HDMV/PGS
Codec ID/Info                            : Picture based subtitle format used on BDs/HD-DVDs
Duration                                 : 1 h 41 min
Bit rate                                 : 33.0 kb/s
Count of elements                        : 3182
Stream size                              : 23.9 MiB (0%)
Title                                    : 繁体中文
Language                                 : Chinese
Default                                  : No
Forced                                   : No

Text #3
ID                                       : 7
Format                                   : PGS
Muxing mode                              : zlib
Codec ID                                 : S_HDMV/PGS
Codec ID/Info                            : Picture based subtitle format used on BDs/HD-DVDs
Duration                                 : 1 h 41 min
Bit rate                                 : 50.5 kb/s
Count of elements                        : 2636
Stream size                              : 36.5 MiB (0%)
Language                                 : English
Default                                  : No
Forced                                   : No

Menu
00:00:00.000                             : 第 01 章
00:08:25.792                             : 第 02 章
00:15:58.083                             : 第 03 章
00:26:08.375                             : 第 04 章
00:36:02.667                             : 第 05 章
00:44:12.417                             : 第 06 章
00:49:21.667                             : 第 07 章
00:56:50.583                             : 第 08 章
01:03:13.250                             : 第 09 章
01:13:42.417                             : 第 10 章
01:25:43.750                             : 第 11 章
01:35:41.417                             : 第 12 章
```

{% endhideToggle %}

<!-- wp:paragraph -->
<p><strong>eac3to log</strong>:</p>
<!-- /wp:paragraph -->

{% hideToggle %}
```
eac3to v3.34
command line: "C:\Users\***\UsEac3to131\eac3to.exe" "D:\BD\Kung Fu Cult Master\" 1) 1: "D:\BD\Kung Fu Cult Master\_1eng.txt" 2: "D:\BD\Kung Fu Cult Master\_2eng.h264" 3: "D:\BD\Kung Fu Cult Master\_3chi.thd+ac3" 4: "D:\BD\Kung Fu Cult Master\_4chi.flac" 7: "D:\BD\Kung Fu Cult Master\_7chi.sup" 8: "D:\BD\Kung Fu Cult Master\_8chi.sup" 9: "D:\BD\Kung Fu Cult Master\_9eng.sup" -progressnumbers -log="C:\Users\***\UsEac3to131\UsEac3To.log"
------------------------------------------------------------------------------
M2TS, 1 video track, 4 audio tracks, 5 subtitle tracks, 1:43:22, 24p
1: Chapters, 12 chapters
2: h264/AVC, 1080p24 (16:9)
3: TrueHD/AC3, Chinese, 5.1 channels, 96kHz
(embedded: AC3, 5.1 channels, 640kbps, 48kHz)
4: DTS Master Audio, Chinese, 2.0 channels, 24 bits, 48kHz
(core: DTS, 2.0 channels, 1509kbps, 48kHz)
5: AC3, Chinese, 2.0 channels, 192kbps, 48kHz
6: AC3, Chinese, 2.0 channels, 192kbps, 48kHz
7: Subtitle (PGS), Chinese
8: Subtitle (PGS), Chinese
9: Subtitle (PGS), English
10: Subtitle (PGS), Chinese
11: Subtitle (PGS), Chinese
[v02] The video framerate is correct, but rather unusual. <WARNING>
Creating file "D:\BD\Kung Fu Cult Master\_1eng.txt"...
[s08] Extracting subtitle track number 8...
[v02] Extracting video track number 2...
[s07] Extracting subtitle track number 7...
[s09] Extracting subtitle track number 9...
[a04] Extracting audio track number 4...
[a04] Decoding with libDcaDec DTS Decoder...
[a04] libDcaDec reported the warning "XLL output not lossless". <WARNING>
[a04] Encoding FLAC with libFlac...
[a03] Extracting audio track number 3...
[v02] Creating file "D:\BD\Kung Fu Cult Master\_2eng.h264"...
[a03] Creating file "D:\BD\Kung Fu Cult Master\_3chi.thd+ac3"...
[a04] Creating file "D:\BD\Kung Fu Cult Master\_4chi.flac"...
[s09] Creating file "D:\BD\Kung Fu Cult Master\_9eng.sup"...
[s07] Creating file "D:\BD\Kung Fu Cult Master\_7chi.sup"...
[s08] Creating file "D:\BD\Kung Fu Cult Master\_8chi.sup"...
[a04] Original audio track: max 24 bits, average 21 bits, most common 24 bits.
Video track 2 contains 148849 frames.
Subtitle track 7 contains 1591 captions.
Subtitle track 8 contains 1591 captions.
Subtitle track 9 contains 1544 captions.
eac3to processing took 3 minutes, 37 seconds.
Done.
```
{% endhideToggle %}