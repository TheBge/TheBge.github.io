title: hexo admin 插入图片裂开问题
author: Bing
tags:
  - hexo
categories: []
date: 2021-02-02 21:54:00
---
使用hexo admin截图复制下来的图片都会变成下面这样  
![upload successful]（路径）  

路径从\改成/就好了，直接粘贴复制的图片会存在source下的images文件夹，而且只有保存在md里的图片会存进去，这一点我觉得还蛮好的。  
昨天刚开始使用Typora编辑器管理wiki相关的文章，图片插入问题也是路径位置不对，而且网上搜了半天也没关于这么简单的问题，索性直接去官方文档看。因为这里wiki使用的是Mkdocs搭建的，所以查这里（https://www.mkdocs.org/user-guide/writing-your-docs/?#writing-with-markdown）  mkdocs的图片文件夹叫img，使用Typora编辑可以插入图片时设置复制到指定的路径。