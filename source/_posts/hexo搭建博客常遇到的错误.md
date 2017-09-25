---
title: hexo搭建博客常遇到的错误
date: 2017-08-03 10:56:41
tags:
---
在用hexo+github搭建个人博客时，很幸运，只遇到了两个小坑，下面是问题跟解决方案

<!-- more -->

## 常遇问题1:

报错内容：
	Error: Cannot find module './build/Release/DTraceProviderBindings'

### 解决方式：

方案1：需卸载hexo-cli再重新安装

``` bash
$ sudo npm unninstall hexo-cli -g
$ sudo npm ninstall hexo-cli -g
```

方案2：

``` bash
$ install hexo --no-optional
```

两种方案，对于不同的用户，可能有的生效，有的不生效，本人亲测，方案1有效！


## 常遇问题2:

报错内容：
	ERROR Process failed: _posts/
	TypeError: Cannot read property 'offset' of null

### 解决方式：

找到blog目录下的 _config.yml 文件

方案1： 

timezone 设置为 timezone: Asia/Shanghai

方案2： 

timezone 设置为 timezone: zh-CN

两种方案，对于不同的用户，可能有的生效，有的不生效，本人亲测，方案1有效！