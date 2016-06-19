---
layout: post
title:  "为Github Pages绑定个人域名"
date:   2016-06-19 15:28:54 +0800
permalink: /bind-custom-domain-name-to-my-github-page/
---

## 申请域名

打算在[万网](https://wanwang.aliyun.com/)申请个人域名。首选`churui.com`已经被注册，2017年2月到期。如果此君不续费，那明年可以考虑把.com域名握在手里。不过鉴于我或者与我同名者成名的概率极低，这个域名大概是不会有什么升值的空间了。

于是直接选择了第一备选的`churui.me`，.me还是很适合做个人博客域名的。付费5年，提交身份证。小事一桩。

## 复习DNS的知识

工欲善其事，必先利其器。
为了更好的使用这个域名，我还顺便复习了一遍域名和DNS的工作原理：[how domain name works](http://domain.me/how-domain-names-work/)。
与我而言，目前需要知道的有：

- 如何让域名指向服务器的IP地址，什么是ANAME
- 如何让域名指向另一域名，什么是CNAME
- 域名结构
- DNS工作原理

## 将域名指向Github Pages的基本方法

Github Pages的个人站点，默认的域名形式为`username.github.io`。如果想在输入churui.me这个域名时，也有默认域名的效果，需要做这么几件事情：

1. 在万网后台，增加两条A record记录，将域名指向Github的IP（详见[官方文档](https://help.github.com/articles/setting-up-an-apex-domain/#configuring-a-records-with-your-dns-provider)）。
2. 在万网后台，增加一条CNAME记录，写入Github Pages的默认域名，即`musray.github.io.`。
- 此处是个隐藏的坑。在Github官方指导文章[setting-up-an-apex-domain](https://help.github.com/articles/setting-up-an-apex-domain/)里，并未提到需要在DNS Provider的域名解析中增加CNAME指向`musray.github.io`，导致我的域名churui.me一直无法被解析。后来查阅文章[GitHub Pages 绑定来自阿里云的域名](http://quantumman.me/blog/setting-up-a-domain-with-gitHub-pages.html)才尝试在万网增加CNAME。
- 另外，更要注意的是CNAME里io后面还要加一个`.`, 即`musray.github.io.`。
3. 在Github的项目Repository里增加CNAME文件，文件里写新域名`churui.me`即可。
DNS生效以后，就可以在浏览器输入churui.me来访问musray.github.io了。

## 子域名的使用(挖坑待填)

例如

- 如何在个人项目的站点使用子域名`projectname.churui.me`
- 如何为个人博客使用子域名`blog.churui.me`

等等。

This Official [post](https://help.github.com/articles/about-supported-custom-domains/) may help a lot.
