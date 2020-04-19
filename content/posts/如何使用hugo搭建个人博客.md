---
title: "如何使用hugo搭建个人博客"
date: 2020-04-19T13:43:22+08:00
draft: false
---

# 如何使用hugo搭建个人博客

## 第一步：下载hugo

首先要[[点击这里](https://github.com/gohugoio/hugo/releases)]把hugo文件给下载下来，进入网址后根据自己电脑的操作系统来下载对应的压缩包，我的电脑是Windows10 64位操作系统，故以下以该系统为例。

## 第二步：配置PATH

下载完成后，推荐把压缩包里的hugo.exe文件解压到D盘的Software文件夹里，并且复制该目录的地址。然后右击此电脑 - 属性 - 高级系统设置 - 环境变量 - 系统变量 - PATH - 把刚刚复制的地址给添加进去，完成后建议重启电脑一下以完成设置。

重启后，在bash控制台输入命令：

```
hugo versoin
```

回车后显示hugo对应的版本号，说明配置PATH成功。

## 第三步：配置hugo

在D盘新建一个文件夹，取一个自己的名字，这里我的文件夹名字为：*codinglmy.github.io-creator*，运行以下几个步骤来完成个人博客的搭建：

### step1：建立新的网站

```
hugo new site 站点名字
```

### step2：给网站添加主题

```
git init
git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
echo 'theme = "ananke"' >> config.toml
```
### step3:添加一篇博客

```
hugo new posts/我的第一篇博客.md
```
然后用编辑器打开后，就可以编辑自己第一篇博客的内容了，写完后记得把

```
draft:true
```
这里把true改为false，这样才能显示文章内容，否则会被视为草稿状态。

### step4：启动hugo服务器

```
hugo server -D
```
输入以上命令后，控制台里就会出现一个地址:

http://localhost:xxxx/

这时我们点击这个地址，就能看到已经搭建好的博客内容了。

## 第四步：把博客上传到github，使之能被在线访问

这里我们需要新建一个.gitnore文件，然后在里面输入
```
/public/
```

把 **public文件夹** 给添加到git忽略列表里面。

然后在github上新建一个仓库，本地进入public文件夹，把里面的所有文件都上传到远程仓库里，就可以在线访问自己的博客了。