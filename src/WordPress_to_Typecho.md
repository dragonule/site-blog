---
layout: post
title: 从WordPress折腾到了Typecho
slug: wordpress-to-typecho
date: 2020-01-01 09:25
status: publish
author: 老张
categories: 
  - 生活
tags: 
  - 博客
  - WordPress
  - Typecho
excerpt: Typecho的的确很轻巧
---
感觉WordPress太臃肿了，而且主题太复杂,不懂代码实在太累。另外，收费主题功能太多太乱，所以决定尝试下Typecho.    
让老薛主机帮忙装了Typecho，一切很顺利。   
第一次用Typecho,感觉比WordPress轻巧太多，感觉比较适合自己。   
另外，Typecho的主题好像普遍比WordPress要便宜，买了Handsome,还是挺满意的。   

几点需注意的记录下：
- 永久链接/{category}/{slug}.html】更能符合SEO优化的特点。
- 需要在要目录下放一个.htaccess 文件解决地址中有index.php的问题

```
RewriteEngine On 
RewriteBase / 
RewriteCond %{REQUEST_FILENAME} !-f 
RewriteCond %{REQUEST_FILENAME} !-d 
RewriteRule ^(.*)$ /index.php/$1 [L]
RewriteCond %{SERVER_PORT} !^443$
RewriteRule (.*) https://%{SERVER_NAME}/$1 [R=301,L]
RewriteCond %{HTTP_HOST}!^aceact.com$ [NC]
RewriteRule ^(.*)$ http://www.aceact.com/$1 [L,R=301]
```

- 需要在要目录下放一个robots.txt

```
User-agent: *
Disallow: /admin/
Disallow:/install/
sitemap:https://www.xxxxxx.com/sitemap.xml
```
