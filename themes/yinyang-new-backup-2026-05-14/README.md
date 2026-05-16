# Hugo 主题 yinyang

简洁美观的 Hugo 博客主题，支持暗黑模式、打赏功能、评论系统等。

## 安装

### 方式一：克隆主题

```bash
cd your-hugo-site
git clone https://github.com/yourusername/hugo-theme-yinyang themes/yinyang
```

### 方式二：作为子模块

```bash
git submodule add https://github.com/yourusername/hugo-theme-yinyang themes/yinyang
```

## 使用

1. 在项目根目录创建 `config.toml`：

```toml
baseURL = "https://example.com/"
title = "我的博客"
theme = "yinyang"
hasCJKLanguage = true
summaryLength = 30

defaultContentLanguage = "zh"
[languages]
  [languages.zh]
    label = "中文"
    locale = "zh-CN"
    weight = 1
    [languages.zh.params]
      extraCSSFiles = ["/css/index.css", "/css/flexboxgrid-6.3.1.min.css"]
      extraHead = '<script src="/js/darkmode-js.min.js"></script>'

[pagination]
  pagerSize = 10

ShowPostNavLinks = true

[permalinks]
  posts = "/posts/:slug/"

[taxonomies]
  tag = "tags"

[outputs]
  home = ["HTML", "RSS", "JSON"]

[params]
  headTitle = "我的博客"
  [params.author]
    name = "作者名称"
    homepage = "https://example.com/"
  Description = "博客描述"
  comments = true
  mainSections = ["posts"]
  search = true
  reward = true
  reward_guide = "赞赏支持"
  favicon = "/img/favicon.ico"

  # 评论功能 (Twikoo)
  twikoo_envId = "your-twikoo-env-id"

  # 访问统计
  busuanzi = true

  # 额外 CSS
  extraCSSFiles = ["/css/index.css", "/css/flexboxgrid-6.3.1.min.css"]
  extraHead = '<script src="/js/darkmode-js.min.js"></script>'

  # 菜单配置
  [[params.menu]]
    name = "首页"
    url = "/"

  # 社交链接
  [[params.socials]]
    name = "关于"
    link = "/about"

  [[params.socials]]
    name = "订阅"
    link = "/index.xml"

[markup]
  [markup.goldmark]
    [markup.goldmark.renderer]
      unsafe = true
```

2. 创建第一篇文章：

```bash
hugo new posts/hello-world.md
```

3. 启动本地服务器：

```bash
hugo server
```

访问 http://localhost:1313 查看效果。

## 配置说明

| 参数 | 说明 | 示例 |
|------|------|------|
| `headTitle` | 网站标题 | "我的博客" |
| `author.name` | 作者名称 | "张三" |
| `author.homepage` | 作者主页 | "https://example.com" |
| `Description` | 网站描述 | "我的博客" |
| `comments` | 开启评论 | true/false |
| `reward` | 开启打赏 | true/false |
| `reward_guide` | 打赏提示文字 | "赞赏支持" |
| `twikoo_envId` | Twikoo 环境 ID | "xxx" |
| `busuanzi` | 开启不蒜子统计 | true/false |
| `search` | 开启搜索 | true/false |

## 菜单配置

```toml
[[params.menu]]
  name = "首页"
  url = "/"
[[params.menu]]
  name = "关于"
  url = "/about"
```

## 社交链接

```toml
[[params.socials]]
  name = "GitHub"
  link = "https://github.com/xxx"
```

## 侧边栏配置

```toml
[[params.sidebar]]
  title = "关于我"
  content = "<p>这里是侧边栏内容，支持 HTML</p>"
```

## 相关文章

主题会自动显示同标签的相关文章。

## 打赏功能

1. 在 `/static/img/dashang/` 目录下放置二维码图片：
   - `wechat-1.png`, `wechat-2.png`, `wechat-5.png`...
   - `alipay-1.png`, `alipay-2.png`, `alipay-5.png`...

2. 在配置中设置 `reward = true`

## 评论功能

使用 Twikoo 评论系统：

1. 在 https://twikoo.org 注册并创建环境
2. 获取 envId
3. 在配置中设置：
   ```toml
   comments = true
   twikoo_envId = "你的envId"
   ```

## 暗黑模式

主题内置暗黑模式支持，会根据系统主题自动切换。

## 许可证

MIT License