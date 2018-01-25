---
title: 搭建hexo+github+next博客
date: 2018-01-19 14:37:36
tags:
  - Android
  - Hexo
  - githob
categories: hexo
---

# 搭建博客

为什么选择hexo呢，因为要拥抱markdown啊，workPress虽然也支持markdown，但是太不好用了。（hexo是一个基于[Nodejs](http://nodejs.cn/)的静态博客网站生成器）

## 准备工作

1. ### 创建GitHub 仓库

    **登录注册**

   [github](https://github.com/)作为一个程序化必须必知道的一个网站，有账号的登录，没账号的赶紧注册吧。

   **创建仓库**

   ![创建](https://ws1.sinaimg.cn/large/6a7720d1ly1fnlzyaez23j20hl05g0t0.jpg)

   ![仓库名称](https://ws1.sinaimg.cn/large/6a7720d1ly1fnlzzttixvj20mc0hc3zu.jpg)

   注意仓库名称的地方一定要使用：你的用户名.github.io(上面是因为我已经创建过了的提示)，否则github默认不会给你生成[GitHub Pages ](https://pages.github.com/)，需要去创建好的仓库的设置里面更改。

   ![更改1](https://ws1.sinaimg.cn/large/6a7720d1ly1fnm07t9jjjj20nn0btgmf.jpg)
   可以更改选择master branch，这样你的博客网址就是二级网址：http://oneapp1e.github.io/你的仓库名称

   ![更改](https://ws1.sinaimg.cn/large/6a7720d1ly1fnm03lweusj20lv0ilgmx.jpg)
   只有创建的仓库名是：你的用户名.github.io，才是正解，可以到设置中更改名称啊！！

   **总结**

   在github上创建一个你的用户名.github.io 的仓库。

2. ### 电脑git环境准备

   打开[git](https://git-scm.com/download/)官网，根据自己的系统下载进行安装。直接默认安装即可。

3. ###  Nodejs安装

   打开[Nodejs](http://nodejs.cn/)官网，选择最新版本就行，没有特殊要求，直接默认安装即可。

4. ###  Hexo安装

   打开[hexo](https://hexo.io/)官网，网站清晰的告诉你安装方法就是一句话

   ```shell
   $ npm install hexo-cli -g
   ```

   ​

## 创建博客

打开命令行，进入需要存放本地博客的目录：

```shell
//cmd 打开cmd终端
$ cd E:/blog

//使用如下命令初始化
$ hexo init 你的用户名.github.io
//进入该目录
$ cd 你的用户名.github.io
//进行安装
$ npm install
//启动
$ hexo server

```

![启动成功](https://ws1.sinaimg.cn/large/6a7720d1ly1fnm0w9d73yj20ei04r0sv.jpg)
看到上图说明安装成功，服务已经启动，在浏览器中输入  http://localhost:4000/ 能够访问了。

hexo已经安装成功了，已经默认有一个hello world了。可以到你本地目录的source/_posts中查看文件。（下一步就是发布到github上，使用github的网址访问了。）

## 发布

发布之前需要更改**_config.yml**配置文件，在本地博客的根目录，注意备份哦。

关于配置的详细信息[hexo官方配置文档](https://hexo.io/zh-cn/docs/configuration.html)，下面是必须改动的地方:

```shell
deploy: # 部署相关配置
    type: git # 使用 Git 提交
    repo: git@github.com:xxx/xxx.github.io.git # 就是存放博客的仓库地址
```

改动好配置文件，就可以往github上发布了，发布hexo也已经帮我们解决了，使用如下命令即可

```shell
//安装发布工具
$ npm install hexo-deployer-git --save

//使用命令 清除缓存
$ hexo clean

//生成静态网页
$ hexo generate 
或者缩写
$ hexo g

//开始部署
$ hexo deploy
或者缩写
$ hexo d
```

这样就已经发布到github上了，赶紧去浏览器里面试试吧！！



## Next主题使用

这个我也是看官网教程配置，目前也是学习阶段，具体可看[官方教程](http://theme-next.iissnan.com/getting-started.html)，就只说一下基本配置吧

```shell
//打开cmd窗口，进入博客的根目录，将next主题克隆到自己本地themes目录
$ git clone https://github.com/iissnan/hexo-theme-next themes/next
```

更改根目录的**_config.yml**配置文件

```shell
//刚刚克隆的主题名称
$ theme: next 
```

就这样重新生成网页和部署之后，Next主题就有生效了。





### 补充

忘了写github的ssh访问方式了，这里也不再另外写了，搭建搜一下吧！



## 思考

1. github上存储的都是静态页面，每次都是本地生成发布，换电脑了或者电脑坏了怎么办。

   参考：[关于博客同步的解决办法](http://devtian.me/2015/03/17/blog-sync-solution/)

2. 如何更改的使用Next主题

3. hexo的更高级的使用



