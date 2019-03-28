---
layout: hexo
title: Hexo server报错
date: 2018-01-29 11:55:27
tags:
  - hexo 
categories:
- 技术 
toc: true
---
Cannot read property 'utcOffset' of null
<!-- more -->
Cannot read property 'utcOffset' of null
~~~
 自己把_config.yml中的时区timezone改成了beijing
 解决办法就是把timezone改成Asia/Shanghai就好了。
~~~

hexo 写文章时附带图片
找到根目录下的 _config.yml 文件，将 post_asset_folder 的值改为 true。
以后你使用 hexo new '' 命令的时候，会在 source 目录新建一个同名的文件夹，然后把你的图片放进去就好了。


只要在config.yml里面写上插件配置在命令行的hexo server就失效。。。
（暂无解决办法）

```

# Plugins
index_generator:
  per_page: 5 ##首页默认5篇文章标题，如果值为0不分页
archive_generator:
  per_page: 20 ##归档页面默认20篇文章标题，如果值为0不分页
  yearly: true ##生成年视图
  monthly: true ##生成月视图
tag_generator:
  per_page: 20 ##标签页面默认20篇文章，如果值为0不分页
category_generator: 
  per_page: 20 ##分类页面默认20篇文章，如果值为0不分页
```

