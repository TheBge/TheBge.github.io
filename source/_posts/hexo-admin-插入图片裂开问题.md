title: hexo admin 插入图片裂开问题
author: Bing
tags:
  - hexo
categories: []
date: 2021-02-02 21:54:00
---
使用hexo admin截图复制下来的图片都会变成下面这样  
![upload successful]（路径）  
粘贴的图片路径都是\，从\改成/就好了,Settings里面可以设置的路径是存放的路径，直接粘贴复制的图片会存在source下的images文件夹，Setting里路径是/images，但是复制的图片后引用的是\\images\blablabla...每次都这么改有点麻烦，所以这里要去改一下粘贴图片时添加的路径。  

**解决**  
修改hexo admin插件下的api.js,修改filename。
```
    filename = imagePath + "/" + filename    //这里
    var outpath = path.join(hexo.source_dir, filename)

    var dataURI = req.body.data.slice('data:image/png;base64,'.length)
    var buf = new Buffer(dataURI, 'base64')
    hexo.log.d(`saving image to ${outpath}`)
    fs.writeFile(outpath, buf, function (err) {
      if (err) {
        console.log(err)
      }
      hexo.source.process().then(function () {
        res.done({
          src: filename,   //和这里
          msg: msg
        })
      });
    })
  });
```
昨天刚开始使用Typora编辑器管理wiki相关的文章，图片插入问题也是路径位置不对，而且网上搜了半天也没关于这么简单的问题，索性直接去官方文档看。因为这里wiki使用的是Mkdocs搭建的，所以查这里（https://www.mkdocs.org/user-guide/writing-your-docs/?#writing-with-markdown），mkdocs的图片文件夹叫img，使用Typora编辑还可以插入图片时设置复制到指定的路径。