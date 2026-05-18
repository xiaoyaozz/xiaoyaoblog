---
title: "给HUGO主题增加背景音乐"
slug: "给HUGO主题增加背景音乐"
date: 2024-03-21
tags: ['分享']
categories:  ['分享']
summary: 主题中添加背景音乐。
---


*实践过程发现有BUG，可以在左下角正常播放使用，但文章内的锚点失效，所以暂时弃用（只是针对我用的主题，其它主题还要自己测试）*


用到了APlayer & MetingJS 文件

引用三个文件APlayer.min.js  APlayer.min.css  Meting.min.js

可以使用CDN加速



```
<link href="https://cdn.bootcss.com/aplayer/1.10.1/APlayer.min.css" rel="stylesheet">
<script src="https://cdn.bootcss.com/aplayer/1.10.1/APlayer.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/meting@2.0.1/dist/Meting.min.js"></script>
```





当然也可以打开这三个链接，将其中内容拉下来放到自己服务器上，这样可以避免那天链接失效，


在 partials 文件夹内新建 music.html 文件，然后填写：



```<head>
    <link rel="stylesheet" href="https://lf9-cdn-tos.bytecdntp.com/cdn/expire-1-M/aplayer/1.10.1/APlayer.min.css">
    <script src="https://lf6-cdn-tos.bytecdntp.com/cdn/expire-1-M/aplayer/1.10.1/APlayer.min.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/meting/2.0.1/Meting.min.js"></script>
</head>
<body>
    <meting-js server="netease" type="playlist" id="129627424" mini="ture" fixed="ture"></meting-js>
</body>
```


之后在 custom.html 文件中添加 {{ partial "music.html"}} 然后保存。

如果想要修改播放器的各项设置可以在文档中查看各项参数的配置。

|参数|	默认值|	描述|
|-|-|-|
|id	|require|	歌曲ID / 歌单ID / 专辑ID / 搜索关键词|
|server	|require|	platform: netease, tencent, kugou, xiami, baidu 音乐平台: 网易云, QQ音乐, 酷狗, 虾米, 百度|
|type	|require|	song, playlist, album, search, artist|
|auto	|options|	music link, support: netease, tencent, xiami|
|fixed	|false|	enable fixed mode|
|mini	|false|	enable mini mode|
|autoplay	|false|	audio autoplay|
|theme	|#2980b9|	main color|
|loop	|all|	player loop play, values: 'all', 'one', 'none'|
|order	|list|	player play order, values: 'list', 'random'|
|preload	|auto|	values: 'none', 'metadata', 'auto'|
|volume	|0.7|	default volume, notice that player will remember user setting, default volume will not work after user set volume themselves|
|mutex	|true|	prevent to play multiple player at the same time, pause other players when this player start play|
|lrc-type	|0|	lyric type|
|list-folded	|false|	indicate whether list should folded at first|
|list-max-height	|340px|	list max height|
|storage-name	|metingjs|	localStorage key that store player setting|

如果你在使用中并没有什么BUG,那么恭喜你。


本站现在使用的方法主要是需要一个音乐的外链。然后使用下而的代码就可以实现。




```
<iframe src="音乐外链" 
        height="25" 
        width="297" 
        style="border:0; position: fixed; bottom: 0; left: 0;" 
        scrolling="no" 
        frameborder="0" 
        allowtransparency="true">
</iframe>
```