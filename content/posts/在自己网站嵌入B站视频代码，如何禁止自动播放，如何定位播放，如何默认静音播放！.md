---
title: "在自己网站嵌入B站视频代码，如何禁止自动播放，如何定位播放，如何默认静音播放！"
slug: "bilibili-video-embed-code"
date: 2024-03-08
draft: false
tags: ['分享']
categories:  ['分享']
summary: 很多人在 B站 上传视频后，都会有转发到自己网站 或 个人博客的需求，B站也提供了一键复制网站嵌入代码，可以很方便的把B站的视频，引用转发到自己需要播放该视频的网站中去。
---
很多人在 B站 上传视频后，都会有转发到自己网站 或 个人博客的需求，

B站也提供了一键复制网站嵌入代码，可以很方便的把B站的视频，引用转发到自己需要播放该视频的网站中去。


B站 视频播放页，有视频分享功能，可以很方便的 一键复制分享视频 代码，如下图所示：

![](pic/Bilibili-1.png)



但有个问题！

在B站，直接复制的视频嵌入代码，默认情况下：是会自动播放视频的。



一般网站访问者，都不太喜欢在浏览网页时，打开一个网页就自动播放视频和声音的，

因为，这也太突然、太打扰了吧。。。





一、如何禁止B站视频自动播放！


有什么方法，让调用的b站视频不要自动播放吗？当然有方法：


1.如果要让引用的视频不自动播放，只要在src链接尾部，添加参数 &autoplay=0 就行，如下所示：


<iframe src="//player.bilibili.com/player.html?aid=927246340&bvid=BV1xT4y1c75o&cid=238186831&page=1&autoplay=0" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>









2.如果要让引用的视频自动播放，只要在src链接尾部，添加参数 &autoplay=1 就行，如下所示：



<iframe src="//player.bilibili.com/player.html?aid=927246340&bvid=BV1xT4y1c75o&cid=238186831&page=1&autoplay=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>







二、如何让B站的视频，在指定位置开始播放！



如果想要让引用的 B站 视频，从指定的某分某秒处开始播放，

可以在视频网址链接尾部，添加参数 &t=多少秒 就行，如下所示：


http://player.bilibili.com/player.html?aid=927246340&t=221



&t=多少秒，就会从多少秒处开始播放，比如要从 3分41秒 处开始播放视频，就是 &t=221  


【计算方式是： 60*3=180秒  再加41，就是221秒！ 所以填入 &t=221，就是从 3分41秒 处开始播放视频。】




三、如何让B站视频，默认静音播放！



如果想要让引用的 B站 视频， 默认在网页中静音播放，

可以在视频网址链接尾部，添加参数 &muted=true 就行，如下所示：


http://player.bilibili.com/player.html?aid=927246340&muted=true



如果我们在引用的 B站 视频网址中，添加上 &muted=true 时，

视频在播放时就没有声音，需要手动点击取消静音模式，视频才有声音。


muted 视频静音 （当 muted 等于 true 时，视频将会 默认静音播放）。

转自：https://www.87com.com/post-55.html