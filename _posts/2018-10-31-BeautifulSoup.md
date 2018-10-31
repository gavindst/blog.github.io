---
layout: post
title: BeautifulSoup笔记 
date: 2018-10-31 00:00:00 +0300
description: description # Add post description (optional)
img:  # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Python,Scrapy]
---
# 快速开始

'''
from bs4 import BeautifulSoup
soup = BeautifulSoup(html_doc, 'html.parser')
print(soup.title)
print(soup.title.name)
print(soup.title.string)
> 找到文档中所有a标签的href链接
for link in soup.find_all('a'):
	print(link.get('href'))
'''


