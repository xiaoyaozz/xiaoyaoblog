---
title: "图片使用指南"
slug: "图片使用指南"
date: 2026-05-14
summary: "本主题使用 GLightbox 灯箱，点击文章内的任意图片即可浮层放大、左右切换"
tags: ["记录"]
---

本主题已集成 **GLightbox** 灯箱插件，**无需任何短代码**，直接用标准的 Markdown 图片语法即可。

---

## 1. 单张图片

最简用法，一行 Markdown：

```markdown
![图片描述](pan1.jpg)
```

效果：

![示例图片](pan1.jpg)

点击图片 → 浮层放大 → 点击背景或按 ESC 关闭。

---

## 2. 多张图片（自动形成画廊）

连续多张图片会自动形成画廊，点击后可以用 **← → 箭头** 或 **鼠标左右拖动** 切换：

```markdown
![图片1](pan1.jpg)
![图片2](pan2.jpg)
```

效果（依次插入多张图片自动组成相册）：

![图片1](pan1.jpg)
![图片2](pan2.jpg)

点击任意一张 → 浮层放大 → 左右箭头切换 → 鼠标拖动。

---

## 3. 在文章段落中混排

图片可以和文字混排，点击同样生效：

```markdown
这是一段文字描述。

![风景图](pan1.jpg)

这是另一段文字，中间插入图片也不影响灯箱效果。
```

---

## 4. 图片路径说明

- 图片放在 `static/` 目录下
- 引用时以 `/` 开头，例如 `pan1.jpg`
- 支持子目录： `/images/album/photo.jpg`

---

## 5. 控制灯箱中的图片大小

GLightbox 默认按图片原始分辨率显示，并支持缩放。你可以通过以下方式控制灯箱中的图片展示效果：

### 5.1 使用 HTML 标签自定义大小

在 `.md` 文件中直接写 HTML（本主题已开启 HTML 支持），用 `data-width` / `data-height` 控制灯箱内的显示尺寸：

```html
<a href="原图.jpg" data-width="800px" data-height="auto">
  <img src="缩略图.jpg" alt="描述" />
</a>
```

```html
<a href="原图.jpg" data-width="90vw" data-height="70vh">
  <img src="缩略图.jpg" alt="描述" />
</a>
```

支持的单位：`px`、`%`、`vw`（视口宽度）、`vh`（视口高度）。

### 5.2 响应式图片（适配不同屏幕）

为不同分辨率提供不同图片：

```html
<a href="default.jpg"
   data-sizes="(max-width: 600px) 480px, 800px"
   data-srcset="/images/small.jpg 480w, /images/big.jpg 800w">
  <img src="/images/default.jpg" alt="描述" />
</a>
```

### 5.3 全局默认大小（修改所有灯箱图片）

如需统一限制灯箱内图片的最大尺寸，可以在 `static/css/index.css` 中添加样式：

```css
.gslide-image img {
  max-width: 90vw;
  max-height: 85vh;
  object-fit: contain;
}
```

> **注意：** 直接在 Markdown 中用 `![描述](图片.jpg)` 无法添加自定义属性。如需精细控制，请使用上方 HTML 语法替代 Markdown 图片语法。
