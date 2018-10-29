---
layout: post
title: Scrapy命令
date: 2018-10-29 21:13:20 +0300
description: description # Add post description (optional)
img:  # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Python,Scrapy]
---
# Scrapy 命令

## 全局命令
- startproject
- settings
- runspider
- shell
- fetch
- view
- version

## 项目命令
- crawl
- check
- list
- edit
- parse
- genspider
- deploy
- bench

### startproject
- 语法: ' scrapy startproject <project_name> '
在' project_name '文件下创建一个名字为 ' project_name '的scrapy项目

### genspider
- ' scrapy genspider [-t template] <name> <domain>'
name 爬虫名字
domain 爬取的网站
在当前项目创建爬虫

### shell
- scrapy shell [url]
以给定的URL(或者为空)启动Scrapy shell，以后会详解shell
