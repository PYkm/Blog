---
layout: post
tags: 
- Google Sheets
- Excel
- 高效
title: 简单、方便的函数：Unique
excerpt: 
date: 2020.07.05 17:47:00
location: 上海
---

你也经常会有这样的需求吗？一组数据里重复的值之算作一个值，然后返回这些值，或者返回这样的值的个数。今天介绍Unique函数，这个函数结合count、sort函数还可以实现更多效果。


那么我们先来了解一下这个函数的含义。Unique：唯一。Returns unique rows in the provided source range, discarding duplicates. Rows are returned in the order in which they first appear in the source range.

了解了含义，我们来了解一下unique的语法规则：

**=UNIQUE(范围)**

来看一个例子，学院绩点排名出来了，老师请你帮他确认排名前十五的学生都分布在哪些班级。原来的表格像这样：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-1.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-1.png" title="初始文档样式" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-1.png">
	</a>
</div>


现在函数要登场啦~

**范围** ： B2:B16。

于是应该填写的公式是：

**=Unique(B2:B16)**

懒得写表头，所以干脆把范围扩展到B1:B16。

现在的公式是：

**=Unique(B1:B16)**


放进表格里面试试：
<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-2.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-2.png" title="使用=Unique(B1:B16)后" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-2.png">
	</a>
</div>

效果很不错，但是如果班级也能排一下序就更好了，于是结合sort使用，加上表头，更改公式如下：

**=sort(unique(B2:B16))**

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-0.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-0.png" title="使用=sort(unique(B2:B16))后" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-0.png">
	</a>
</div>

还有个问题，前十五名分别落在了几个班级里呢？使用公式如下：

**=count(unique(B2:B16))**

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-3.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-3.png" title="使用=count(unique(B2:B16))后" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-05-How-To-Use-the-Unique-Function-3.png">
	</a>
</div>

大功告成！Unique函数就是这么简单、方便，可以节约我们好多时间哦~ 

此外，**<a href="https://support.microsoft.com/zh-cn" target="_blank">微软支持中心网站</a>**和**<a href="https://support.google.com/docs#topic=1382883" target="_blank">谷歌文档编辑器帮助</a>**真的有很多非常有用的帮助文档，官方的解释总是更加详尽，大家一定要利用起来哦！

参考链接：
1. <a href="https://support.google.com/docs/answer/3093198?hl=en" target="_blank">Unique（谷歌）</a>
2. <a href="https://support.microsoft.com/zh-cn/office/unique-%e5%87%bd%e6%95%b0-c5ab87fd-30a3-4ce9-9d1a-40204fb85e1e?ui=zh-cn&rs=zh-cn&ad=cn" target="_blank">Unique（微软）</a>