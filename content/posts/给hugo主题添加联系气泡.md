---
title: "给hugo主题添加联系气泡"
slug: "hugo-qipao"
date: 2024-03-21
tags: ['分享']
categories:  ['分享']
summary: 给hugo主题添加联系气泡
---

![](https://pic.imgdb.cn/item/63e339c04757feff33e24c12.webp)

打开博客后发现右下角会有气泡，有什么事情都可以随时联系到我哦！

![](https://i.imgtg.com/2023/02/08/cTCDY.webp)

这是一个偶然的机会发现的有趣的小功能😂，是日本一家公司提供的 Channel.io。

在注册后打开 setting-install and configuration-install plugin for web，把显示的 JS 复制。

打开 layouts\partials\footer\components 下的 script.html 文件扔进去就好。

在设置里可以修改欢迎信息。

![](https://pic.imgdb.cn/item/63e339e84757feff33e28e61.webp)

那怎么才能得到通知嘞？ 笨诶😆，当然是去下载他们家的 APP 咯，Play Store 或 IOS 外区都有，Android 上如果可以访问 Google，连通 FCM 的话可以实时获取消息。