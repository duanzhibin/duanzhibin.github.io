---
layout: post
title:  "第一篇博客"
categories: essay
tags:  essay 
author: duanzhibin
---

* content
{:toc}

  似乎就要大功告成了，搭建第一个个人博客系统，之所以想要弄这个，主要是觉得挺酷的。第五空间也有了我的身影，哈哈。
   
  所有经历过的东西好像都能在未来某一刻产生作用，之前参加`JAVAWEB`实习，想着自己不做前端工程师，以后用不到这些知识。没想到这么
  快就用到了。你经历过的东西，最不济也可以成为谈资。拥抱新事物，不断满足自己的好奇心。往往是书到用时方恨少。

    
  



## 目的：

写这篇文章的目的主要是为了测试在本地进行md文件的编写是否能使用hexo进行html生成，然后上传到github上，通过访问https://day21.top 这个网站查看能否看到最新的文章




## 操作步骤：

```js

spencer@spencer-it1 MINGW64 /f/myself/643435675.github.io (master)
$ gem install jekyll
Successfully installed jekyll-3.6.2
Parsing documentation for jekyll-3.6.2
Done installing documentation for jekyll after 2 seconds
1 gem installed

spencer@spencer-it1 MINGW64 /f/myself/643435675.github.io (master)
$ jekyll s
Configuration file: F:/myself/643435675.github.io/_config.yml
            Source: F:/myself/643435675.github.io
       Destination: F:/myself/643435675.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 5.499 seconds.
  Please add the following to your Gemfile to avoid polling for changes:
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?
 Auto-regeneration: enabled for 'F:/myself/643435675.github.io'
    Server address: http://127.0.0.1:4001/
  Server running... press ctrl-c to stop.


spencer@spencer-it1 MINGW64 /f/myself/643435675.github.io (master)
$ jekyll serve
Configuration file: F:/myself/643435675.github.io/_config.yml
            Source: F:/myself/643435675.github.io
       Destination: F:/myself/643435675.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 2.859 seconds.
  Please add the following to your Gemfile to avoid polling for changes:
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?
 Auto-regeneration: enabled for 'F:/myself/643435675.github.io'
    Server address: http://127.0.0.1:4001/
  Server running... press ctrl-c to stop.

```

主要进行了以上操作：
cd 643435675.github.io  文件夹下

执行命令：

`gem install jekyll `

下一步：
`jekyll s`

接下来：
`jekyll serve`

然后这样就可以在浏览器中输入：http://127.0.0.1:4001/ 进行刚刚文章的访问了。


补充：

因为首页与详情页显示某篇文章的内容是不一样的，在首页中进行文章的裁剪显示：
需要进行加入四个空行：
```md
## 目的：

写这篇文章的目的主要是为了测试在本地进行md文件的编写是否能使用hexo进行html生成，然后上传到github上，通过访问https://day21.top 这个网站查看能否看到最新的文章




## 操作步骤：
```

不进行添加的话，首页会把整篇文章完全展示出来，添加了四个空行之后就只会显示部分了，当然了，这篇文章在首页是显示的部分，也就是**目的下的内容**


