# Hexo博客

官网：https://hexo.io/zh-cn/

```
npm install hexo-cli -g
hexo init blog
cd blog
npm install
hexo clean
hexo server
```

快捷命令

```sh
一键本地启动：hexo clean && hexo g && hexo s
一键部署：hexo clean && hexo g && hexo d
$ hexo deploy --generate  或 hexo g -d or hexo d -g
```

## 创建和发布文章

`hexo new [layout] <title>`
新建一篇新文章，会自动按照模板里面的格式创建文章

里面的布局（layout），默认为 post，布局共有三种：

```
post	source/_posts
page	source
draft	source/_drafts
```

> WARNING
>
> 如果你没有 pug 以及 stylus 的渲染器，请下载安装：
>
> npm install hexo-renderer-pug hexo-renderer-stylus --save 或者
> yarn add hexo-renderer-pug hexo-renderer-stylus

### 本地搜索

```sh
$ npm install hexo-generator-search --save
$ npm install hexo-deployer-git --save
```



### Hexo设置跳过渲染某个文件或文件夹

https://github.com/hexojs/hexo/issues/1146

`_config.yml`有提供一个配置项skip_render来设置跳过渲染的文件及文件夹

```
// 跳过单个文件
skip_render: test.html

// 跳过所有的html的文件
skip_render: '*.html'

跳过某个目录下的所有文件的渲染
skip_render: test/*

跳过某一目录下的所有文件和子目录的渲染
skip_render: test/**

跳过多个目录，或者多个文件的渲染
skip_render: ['*.html', demos/**, test/*]
```



如果要忽略多个路径的文件或目录，可以这样配置：

```

skip_render:
  - "README.md"
  - ".github/**/**"
  - test.html
  - '*.html'
  - test/**
  - test/*
```

or

```
skip_render: [README.md, '.github/**/**', test/**, test/*]
```



### 自动化部署

https://knktc.com/2021/06/26/hexo-use-github-actions-to-submit-sitemap/

`Error: Need phone captcha validation, please follow wechat official account "Gitee" to bind account to turn off authentication.`

微信公众号关注Gitee，绑定Gitee账号就可以了。

