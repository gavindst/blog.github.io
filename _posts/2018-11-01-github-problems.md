---
layout: post
title: github无法访问或者显示不全解决方法 
date: 2018-11-01 00:00:00 +0300
description: description # Add post description (optional)
img: github.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Github,Problems]
---
# 解决方法

因为dns污染所以无法正常访问github,所以最简单的方式就是更改hosts文件，
不去请求dns服务器，直接访问hosts文件中的ip地址

1. 更改/etc/hosts文件
- github.com
- github.global.ssl.fastly.net
- assets-cdn.github.com
- documentcloud.github.com
- gist.github.com
- help.github.com
- nodeload.github.com
- raw.github.com
- status.github.com
- traning.github.com
- www.github.com
- avatars0.githubusercontent.com
- avatars1.githubusercontent.com
- codeload.github.com
- 将以上的网址使用dns查询工具查询ip(记得要ping一下ip地址看看能不能用)我用的是tool.chinaz.com/dns/

2. 如果使用一段时间后又不能用了，那么打开github网站，按下F12,在Network下看看哪个网站又没响应了，
再重新查询一下那个网站ip，不要问我为什么知道，我的hosts文件已经改了好多次了
