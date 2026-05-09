---
title: 设置黑白色的LOGO
slug: "set-black-white-logo"
date: 2024-03-22
categories: ['分享']
draft: false
summary: 去BING搜索了一个太极的SVG当LOGO,右键使用词本打开SVG进行编辑。
---




### 第一步

去BING搜索了一个太极的SVG当LOGO。

右键使用词本打开SVG进行编辑。

### 第二步

找到

```
fill="#000000" style="fill: rgb(0, 0, 0);
```
这段代码 改 000000 到 ffffff 改 rgb(0,0,0) 到 rgb(255,255,255) 就变成了黑色的太极的LOGO

### 第三步

改themes/hextra/layouts/partials/navbar.html

找到并修改“LOGO路径”

```
{{- if (.Site.Params.navbar.displayLogo | default true) }}
        <img class="block dark:hidden" src="白LOGO路径" alt="{{ .Site.Title }}" height="{{ $logoHeight }}" width="{{ $logoWidth }}" />
        <img class="hidden dark:block" src="黑LOGO路径" alt="{{ .Site.Title }}" height="{{ $logoHeight }}" width="{{ $logoWidth }}" />
{{- end }}

```

