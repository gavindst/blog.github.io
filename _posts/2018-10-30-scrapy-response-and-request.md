---
layout: post
title: Request and Response in Scrapy
date: 2018-10-30 00:00:00 +0300
description: description # Add post description (optional)
img:  # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Python,Scrapy]
---
# Response objects

## Parameters

- url(string)
- status(HTTP status)
- headers(dict)
- body Response.body is always a bytes object,This attribute is read-only
- request
- meta
- flags
- copy()
- replace([url,status,headers,body,request,flafs,cls])
- urljoin(url)
- follow(url, callback=None, method='GET', headers=None, body=None, 
	cookies=None, meta=None, encoding='utf-8', priority=0, 
	dont_filter=False, errback=None)

## Response subclasses 响应的子类

### TextResponse object

- text -- Response body as unicode.same as response.body.decode(response.encoding)
- encoding
- selector
- xpath(query)
- css(query)
- follow
- body_as_unicode() same as text ,prefer text

### HtmlResponse objects

### XmlResponse objects


