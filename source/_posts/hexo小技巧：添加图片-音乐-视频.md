---
title: hexo小技巧
date: 2017-08-04 15:25:02
tags:
---
以hexo 3.x.x为例

### 1.添加图片

在source目录下新建文件夹，命名为images，此文件夹会被编译到public文件夹下，在文档中插入图片的代码如下：

``` bash 
![图片描述](/blog/images/图片名字.jpg)
```

### 2.插入音乐

首先找到自己想要插入的音乐的链接，复制下来，代码如下：

``` bash 
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86   
  src="https://music.163.com/outchain/player?type=2&id=25706282&auto=0&height=66">  
</iframe> 
```
tips: 资源的url的protocol,与你网站的protocol保持一致

### 3.插入视频

首先找到自己想要插入的视频的链接，复制下来，代码如下：

``` bash 
<iframe      
  src="https://player.youku.com/embed/XMjkzNTU5ODA1Mg==" allowfullscreen>  
</iframe>
```

tips: 视频资源链接同样面临http与https的问题

### 4.命令行执行hexo new "title"新建md文件后，自动打开文件

新建scripts文件夹(***与source文件夹同级！！！)，在其下新建js文件，名字不重要

``` bash 
var exec = require('child_process').exec;
// Hexo 3
hexo.on('new', function(data){
    exec('open -a "/Applications/Sublime Text.app" ' + data.path);
});
```