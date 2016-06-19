---
layout: post
title:  "python-docx安装失败, 缺少vcvarsall.bat的解决办法"
date:   2016-06-19 15:28:54 +0800
permalink: /install-python-docx-failed/
---

## 背景
在MAC下安装python-doc，执行`pip install python-docx`一次成功。（pip还同时安装了依赖包lxml)。
在Windows 7下，执行同样的命令，但在安装依赖包lxml时提示`无法找到vcvarsall.bat文件`，导致安装失败。

## 解决方案

[此方案来自知乎](https://www.zhihu.com/question/26857761 "解决方案")。不得不提的是，这是极少数在Google搜索纯英文关键字，返回结果排位第一名是中文网页的情况。
解决方案如下:

1. 下载lxml的.whl文件，[下载地址](http://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml "lxml下载")。
	- 注意1：whl文件不要改名
	- 注意2：whl文件要对应Python版本。cp后面的数字即版本。
2. 在命令行切换至存放.whl的文件夹
3. 运行命令pip install name-of-whl.whl
4. 显示lxml安装成功！
5. 直接pip install python-docx，成功！

## 延伸阅读

1. 搜出了一篇[文档](http://blog.csdn.net/secretx/article/details/17472107%20)，声称可以彻底解决Python在安装包时缺少.bat文件的问题。
2. 关于什么是whl文件，请参考[PEP 427](https://www.python.org/dev/peps/pep-0427/#abstract)
