+++
title = 'Hugo博客添加友链'
slug = 'hugo friend'
date = 2024-03-22T09:14:41+08:00
draft = false
+++

### 1.友链html代码

首先在layouts/shortcodes目录下添加一个html文件，命名为friend.html，在里面添加如下代码
<!--more-->
```
{{- if .IsNamedParams -}}
<a target="_blank" href={{ .Get "url" }} title={{ .Get "name" }} class="friendurl">
  <div class="frienddiv">
    <div class="frienddivleft">
      <img class="myfriend" src={{ .Get "logo" }} />
    </div>
    <div class="frienddivright">
      <div class="friendname">{{- .Get "name" -}}</div>
      <div class="friendinfo">{{- .Get "word" -}}</div>
    </div>
  </div>
</a>
{{- end }}
```

### 2.友链css代码

然后新建/static/css/firend.css文件并引用，在里面添加如下css代码

```.friendurl {
    text-decoration: none !important;
    color: black;
    box-shadow: none !important;
}

.myfriend {
    width: 56px !important;
    height: 56px !important;
    border-radius: 50%!important;
    padding: 2px;
    margin-top: 20px !important;
    margin-left: 14px !important;
    background-color: #fff;
}

.frienddiv {
    overflow: auto;
    height: 100px;
    width: 49%;
    display: inline-block !important;
    border-radius: 5px;
    background: none;
    
    -webkit-transition: all ease-out 0.3s;
    -moz-transition: all ease-out 0.3s;
    -o-transition: all ease-out 0.3s;
    transition: all ease-out 0.3s;
}

.dark .frienddiv:hover {
    background: var(--code-bg);
}

.frienddiv:hover {
    background: var(--theme);
    transition: transform 1s;
    webkit-transform: scale(1.1);
    -moz-transform: scale(1.2);
    -ms-transform: scale(1.2);
    -o-transform: scale(1.2);
    transform: scale(1.1);
}

.frienddiv:hover .frienddivleft img { 
    transition: 0.9s !important;
    -webkit-transition: 0.9s !important;
    -moz-transition: 0.9s !important;
    -o-transition: 0.9s !important;
    -ms-transition: 0.9s !important;
    transform: rotate(360deg) !important;
    -webkit-transform: rotate(360deg) !important;
    -moz-transform: rotate(360deg) !important;
    -o-transform: rotate(360deg) !important;
    -ms-transform: rotate(360deg) !important;
}

.frienddivleft {
    width: 92px;
    float: left;
    margin-right: -5px;
}

.frienddivright {
    margin-top: 18px;
    margin-right: 18px;
}

.friendname {
    text-overflow: ellipsis;
    font-size: 100%;
    margin-bottom: 5px;
    color: var(--primary);
}

.friendinfo {
    text-overflow: ellipsis;
    font-size: 70%;
    color: var(--primary);
}

@media screen and (max-width: 600px) {
    .friendinfo {
        display: none;
    }
    .frienddivleft {
        width: 84px;
        margin: auto;
    }
    .frienddivright {
        height: 100%;
        margin: auto;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .friendname {
        font-size: 18px;
    }
}
```

### 3.填写友链

在要放友链的文件里输入下例的使用方法，比如我放在content/firend/index.md里

复制之后把“干扰”删除。
```
{{干扰<friend name="逍遥博客" url="http://blog.pjzpjs.com" logo="https://pic.imgdb.cn/item/65fcecc89f345e8d0307a98f.png" word="心空无住，任运逍遥。">干扰}}

```

————————————————
版权声明：本文为「Sulv's Blog」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://www.sulvblog.cn/posts/blog/hugo_link/


