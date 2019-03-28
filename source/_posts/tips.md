---
title: tips
date: 2018-01-29 17:55:55
tags:
  - tip 
categories:
- 技术  
toc: true
---
1、快速切图
2、hexo生成博文插入图片
3、目录

<!-- more -->
#### 快速切图
`找到对应的图层，然后ctrl+a  ctrl+c  ctrl+n   ctrl+v `
Hexo server报错Cannot read property 'offset' of null解决方法
 ~~~
自己把_config.yml中的时区timezone改成了beijing
 解决办法就是把timezone改成Asia/Shanghai就好了。
~~~

配置github
~~~
deploy:
  type: git
  repo: git@github.com:sunshinefc/sunshinefc.github.io.git
  branch: master
~~~
然后执行命令：
`npm install hexo-deployer-git --save`

每次部署的步骤，可按以下三步来进行。

~~~
    hexo clean

    hexo generate

    hexo deploy
~~~

一些常用命令：

~~~
hexo new"postName" #新建文章

hexo new page"pageName" #新建页面

hexo generate #生成静态页面至public目录

hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）

hexo deploy #将.deploy目录部署到GitHub

hexo help # 查看帮助

hexo version #查看Hexo的版本
~~~


git回退到某个历史版本
~~~
1. 使用git log命令查看所有的历史版本，获取某个历史版本的id，假设查到历史版本的id是139dcfaa558e3276b30b6b2e5cbbb9c00bbdca96。
2. git reset --hard 139dcfaa558e3276b30b6b2e5cbbb9c00bbdca96  
3. git push -f -u origin master 

~~~

## hexo生成博文插入图片

### First
```
1 把主页配置文件_config.yml 里的post_asset_folder:这个选项设置为true

2 在你的hexo目录下执行这样一句话npm install hexo-asset-image --save，这是下载安装一个可以上传本地图片的插件，来自dalao：dalao的git

3 等待一小段时间后，再运行hexo n "xxxx"来生成md博文时，/source/_posts文件夹内除了xxxx.md文件还有一个同名的文件夹
```

### Second
```
4 最后在xxxx.md中想引入图片时，先把图片复制到xxxx这个文件夹中，然后只需要在xxxx.md中按照markdown的格式引入图片：
![你想输入的替代文字](xxxx/图片名.jpg)

注意： xxxx是这个md文件的名字，也是同名文件夹的名字。只需要有文件夹名字即可，不需要有什么绝对路径。你想引入的图片就只需要放入xxxx这个文件夹内就好了，很像引用相对路径。

5 最后检查一下，hexo g生成页面后，进入public\2017\02\26\index.html文件中查看相关字段，可以发现，html标签内的语句是<img src="2017/02/26/xxxx/图片名.jpg">，而不是<img src="xxxx/图片名.jpg>。这很重要，关乎你的网页是否可以真正加载你想插入的图片。
```
### hexo  删除文章
在本地直接执行删除。然后依次执行hexo g，hexo d


### 目录
npm i hexo-generator-json-content --save
### _config.yml   配置文件
~~~
jsonContent:
    meta: false
    pages: false
    posts:
      title: true
      date: true
      path: true
      text: false
      raw: false
      content: false
      slug: false
      updated: false
      comments: false
      link: false
      permalink: false
      excerpt: false
      categories: false
      tags: true
~~~