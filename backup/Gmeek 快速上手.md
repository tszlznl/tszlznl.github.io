> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.meekdai.com](https://blog.meekdai.com/post/Gmeek-kuai-su-shang-shou.html)

> Gmeek 快速上手

[Gmeek](https://github.com/Meekdai/Gmeek) 一个博客框架，超轻量级个人博客模板，完全基于`Github Pages` 、 `Github Issues` 和 `Github Actions`，可以称作`All in Github`。不需要本地部署，从搭建到写作，只需要 18 秒，2 步搭建好博客，第 3 步就是写作。

一、安装
----

> 安装及其简单，但是也要认真看下面的步骤，一步一步来。

1.  【创建仓库】点击[https://XXX.github.io](https://github.com/new?template_>通过模板创建仓库</a>，建议仓库名称为<code>XXX.github.io</code>，其中<code>XXX</code>为你的 github 用户名。</p>
    </li>
    <li>
    <p>【启用 Pages】在仓库的设置<code>Settings</code>中<code>Pages->Build and deployment->Source</code>下面选择<code>Github Actions</code>。</p>
    </li>
    <li>
    <p>【开始写作】打开一篇 issue，开始写作，并且<strong>必须</strong>添加一个<code>标签Label</code>（只添加一个），再保存 issue 后会自动创建博客内容，片刻后可通过 <a href=) 访问。
    
2.  【手动全局生成】这个步骤只有在修改`config.json` 文件或者出现奇怪问题的时候，需要执行。
    

```
通过Actions->build Gmeek->Run workflow->里面的按钮全局重新生成一次

```

二、配置文件
------

> 按照安装步骤成功搭建好后，就可以阅读下面的内容修改配置文件啦。  
> 注意修改配置文件后一定要手动全局生成一次，不然会报错。  
> 如果对`json`格式不熟悉，建议先简单学习一下。

`config.json` 文件就是配置文件，在创建的仓库内可以找到，对应修改为自己的即可。

```
{
    "title":"Meekdai",
    "subTitle":"童话是一种生活态度，仅此而已。",
    "avatarUrl":"https://github.githubassets.com/favicons/favicon.svg",
    "GMEEK_VERSION":"last"
}

```

以上是必须的字段，下面是可以自定义字段的描述，可以选择加入到`config.json`中。

```
"displayTitle":"Meekdai",
"homeUrl":"http://blog.meekdai.com",
"faviconUrl":"https://github.githubassets.com/favicons/favicon.svg",
"email":"meekdai@163.com",
"startSite":"02/16/2015",
"filingNum":"浙ICP备20023628号",
"onePageListNum":15,
"singlePage":["about"],
"iconList":{"circle":"M0 8a8 8 0 1 1 16 0A8 8 0 0 1 0 8Zm8-6.5a6.5 6.5 0 1 0 0 13 6.5 6.5 0 0 0 0-13Z"},
"commentLabelColor":"#006b75",
"yearColorList":["#bc4c00", "#0969da", "#1f883d", "#A333D0"],
"i18n":"CN",
"UTC":8,
"dayTheme":"light",
"nightTheme":"dark_colorblind",
"urlMode":"pinyin",
"style":"",
"script":"",

```

<table role="table"><thead><tr><th><strong>配置参数</strong></th><th><strong>说明</strong></th></tr></thead><tbody><tr><td>title</td><td>【必填】博客标题</td></tr><tr><td>subTitle</td><td>【必填】博客描述 &amp; 自述</td></tr><tr><td>avatarUrl</td><td>【必填】博客头像</td></tr><tr><td>GMEEK_VERSION</td><td>【必填】Gmeek 版本，一般写<code>last</code>也可以用具体 tag 版本</td></tr><tr><td>displayTitle</td><td>用于头像后面的标题展示，如果和<code>title</code>一致则不用添加</td></tr><tr><td>homeUrl</td><td>博客的主页地址，自定义域名时需要配置</td></tr><tr><td>faviconUrl</td><td>页面的 favicon 地址，如果和 avatarUrl 一致则不用添加</td></tr><tr><td>email</td><td>用于自动提交仓库时用，不添加也可以</td></tr><tr><td>startSite</td><td>用于页面底部显示网站运行天数</td></tr><tr><td>filingNum</td><td>用于页面底部显示备案信息</td></tr><tr><td>onePageListNum</td><td>用于首页每页展示的文章数量</td></tr><tr><td>singlePage</td><td>自定义独立页面，例如<code>about</code>或者<code>link</code>等</td></tr><tr><td>iconList</td><td>用于定义 singlePage 按钮展示的 <a href="https://primer.style/foundations/icons/#16px" rel="nofollow">SVG 图标</a> (16px)，<code>about</code>和<code>link</code>内置无需定义</td></tr><tr><td>commentLabelColor</td><td>用于自定义显示评论数量标签的颜色</td></tr><tr><td>yearColorList</td><td>用于自定义显示不同年份标签的颜色</td></tr><tr><td>i18n</td><td>用于定义博客语言，目前支持<code>EN</code>/<code>CN</code>/<code>RU</code></td></tr><tr><td>UTC</td><td>用于定义<a href="https://en.wikipedia.org/wiki/List_of_UTC_offsets" rel="nofollow">时区</a></td></tr><tr><td>dayTheme</td><td>用于定义<a href="https://github.com/settings/appearance">亮主题</a></td></tr><tr><td>nightTheme</td><td>用于定义<a href="https://github.com/settings/appearance">暗主题</a></td></tr><tr><td>urlMode</td><td>用于定义文章链接生成模式，目前支持<code>pinyin</code>/<code>issue</code>/<code>ru_translit</code></td></tr><tr><td>style</td><td>用于自定义文章页全局 CSS</td></tr><tr><td>script</td><td>用于自定义文章页全局 JavaScript</td></tr></tbody></table>

三、常见问题
------

### 1. 搭建不成功

多半是没有按照安装步骤来，其实搭建就这 2 步，不要自己乱点乱设置，就不会有问题。

*   案例一：[Meekdai/Gmeek#14](https://github.com/Meekdai/Gmeek/issues/14)
*   案例二：[Meekdai/Gmeek#18](https://github.com/Meekdai/Gmeek/issues/18)
*   案例二：[Meekdai/Gmeek#20](https://github.com/Meekdai/Gmeek/issues/20)

### 2. Actions 执行失败

修改了`config.json`配置文件后，需要全局生成。另外`label`标签没有打，或者多打也会出现这个问题。  
建议通过 Actions->build Gmeek->Run workflow-> 里面的按钮全局重新生成一次

*   案例一：[Meekdai/Gmeek#1](https://github.com/Meekdai/Gmeek/issues/1)
*   案例二：[Meekdai/Gmeek#10](https://github.com/Meekdai/Gmeek/issues/10)

### 3. 如果要导入以前的文章，如何设置发布时间呢？

如需修改发布时间，可以在文章最后一行添加如下代码。里面的时间是采用时间戳的形式，可以用如下[网站](https://tool.lu/timestamp)转换。

```
<!-- ##{"timestamp":1490764800}## -->

```

### 4. 自定义单篇文章页面的`style`和`script`

```
<!-- ##{"style":"<style>#postBody{font-size:20px}</style>"}## -->

```

```
<!-- ##{"script":"<script async src='//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js'></script>"}## -->

```

### 5. 可同时一起添加多种自定义参数：

```
<!-- ##{"script":"<script async src='//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js'></script>","style":"<style>#postBody{font-size:20px}</style>","timestamp":1490764800}## -->

```

### 6. 添加全局文章页面的`style`和`script`

在`config.json`文件中添加

```
"style":"<style>#postBody{font-size:20px}</style>",
"script":"<script async src='//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js'></script>",

```

### 7. 置顶博客文章, 只需要`Pin issue`即可。

### 8. 如果在评论里面登录后评论报错，可直接按照提示安装`utteranc app`即可

```
Error: utterances is not installed on xxx/xxx.github.io. If you own this repo, install the app. Read more about this change in the PR.


```

如何魔改
----

如果有朋友想修改博客的主题，或者添加一些东西，这个框架是支持魔改的。所有的 UI 都在 [templates](https://github.com/Meekdai/Gmeek/tree/main/templates) 文件中，可进行修改，如果合适，我会合并到主线，通过配置文件让用户选择哪个主题。