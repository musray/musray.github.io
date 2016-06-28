---
layout: post
title:  "想当‹面霸›程序员？LeetCode是个好选择!"
date:   2016-06-28 8:27:35 +0800
permalink: /what-is-leetcode/
---

前几天决定把Chrome收藏夹里的中文技术类博客删一删，算是“减熵”了。

就在清理的过程中，发现了某博主写的“LeetCode账户被禁用”的文章，而且还表现出颇为着急的情绪。于是好奇，LeetCode是个什么东西？

## What is LeetCode?
> LeetCode OJ is a platform for preparing technical coding interviews. Pick from an expanding library of more than 190 questions, code and submit your solution to see if you have solved it correctly. It is that easy!

[LeetCode](https://leetcode.com)是针对技术面试的在线代码评估平台，题库由真实的互联网公司面试题构成。技术方向分为**算法**、**数据库**和**Bash**三个类型；支持使用9种占有率较高的编程语言进行解题，分别是C, C++, Java, Python, C#, JavaScript, Ruby, Bash, MySQL。

截止到2015年底，LeetCode平台拥有超过300道的技术面试问题，用户在共提交了4700万份答案。这使得LeetCode成了最大的在线评估（Online Judge）网站之一。

## 注册和服务

### 注册
LeetCode支持直接注册、或通过社交网站授权登陆。我选择了Github账户登陆（虽然不是程序员，但咱也是有Github账户的人）。

### 帐户类型
除了免费用户，你还可以选择成为订阅用户。有$25/Month或者$159/Year两种支付选项。订阅之后，比免费用户增加了一些独占试题，支持根据公司将试题分组，并且享有订阅用户独占的博客文章。
按我目前的水平，还是作为一个免费用户，把题库里的题都好好解一解才是正道。

### 购买电子书
Leetcode还提供官方出版的ebook，以方便随时学习。因为没有尝试，所以也先按下不表。但我个人很喜欢买电子书，因为可以打印成纸书。

## 尝试解题
多说无益，还是要赶紧做一道题领略一下Leetcode的风采。不如我们从简单的入手，先尝试一道Easy难度的Bash问题好了。

### 一个简单的Bash问题：**[如何显示`file.txt`文档的第10行](https://leetcode.com/problems/tenth-line/)？**

假定`file.txt`文件内容如下	

```
	Line 1
	Line 2
	Line 3
	Line 4
	Line 5
	Line 6
	Line 7
	Line 8
	Line 9
	Line 10
	Line 11
	...
```

如何使用Bash命令显示该文件的第10行？即显示内容`Line10`？

#### 第一次尝试
如果你比较熟悉命令行，看到上面的问题可能会想到用`head`和`tail`的组合，像这样：

`$ head -10 file.txt | tail -1`

上面这条命令，读取了file.txt的前10行内容，并通过管道传递；tail把接收内容中的最后一行输出到stdout。呵呵，看起来确实是个Easy难度的问题。那么，我们将答案输入命令框：

![LeetCode的输入框]({{ site.url }}/assets/post-images/head-tail-input.png)

提交验证，Oops！有情况！

![LeetCode的评估结果]({{ site.url }}/assets/post-images/head-tail-result.png)

LeetCode在验证的时候发现，如果file.txt只有9行，命令会输出第9行内容，这很明显是出错了。
看起来LeetCode还有点靠谱的。

#### 第二次尝试
让我们再试一次。这次决定请出文字处理专家`sed`：

`$ sed '10q;d' file.txt`

![LeetCode的输入框]({{ site.url }}/assets/post-images/sed-input.png)

再次进行验证：

![LeetCode的评估结果]({{ site.url }}/assets/post-images/sed-result.png)

哈哈，通过！
不仅如此，点击按钮More Details，LeetCode还会把本次验证所作尝试的次数、耗时进行计算，并将所有用户提交过的结果做一个排名：
![runtime distributin]({{ site.url }}/assets/post-images/accepted-solutions-runtime-distribution.png)
从上面的分布图里能看出来，我的这个方法的排名已经进入第一梯队，打败了85.38%的程序员呢！看来`sed`确实是这方面的专家。当然，这个方法也是我在Stackoverflow上学来的！

### LeetCode，学编程的好方法
这次我们只是选择了一个简单的命令行问题小试牛刀。LeetCode支持的数据库问题，都是SQL型的数据库，这个我还来不了。而算法类的问题，我又没有「勇气」挑战。
不过作为每日练习，使用LeetCode学编程确实是个贴近实际而且高效的方法。每次解出题目之后都会让人有更深的思考，还能让信心倍增。
就先写到这吧，马上去做一道Easy程度的算法题，判断一下我的逻辑思维和Python水平到底如何！
