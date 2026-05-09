---
title: 如何在博客网站hexo的文章中添加图片
slug: "how-to-add-image-in-hexo-article"
date: 2024-01-23 16:13:02
categories:  ['分享']
tags: ['分享']
---
1.安装插件

npm install hexo-asset-image --save
<!--more-->
2.需要配置文件

在博客的根目录的配置文件_config.yml中，添加post_asset_folder: true

3.新建文章

hexo new post newArticle

随即在source/_posts下就会产生和文章名字一样的目录newArticle，此为新创建文章的图片存储目录；

4.引用图片

在文章中使用如下语句，引用目录里的图片：

```![此处写上关于图片的备注](hexo-theme.png)```

在本主题下面经过尝试

先用```hexo new posts 博文名字```创建文章

然后添加图片应该是这样的路径
```![](/post/图片文件夹/img.jpg)```

作者：那年六月六
链接：https://www.jianshu.com/p/ae862bbe929a
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。