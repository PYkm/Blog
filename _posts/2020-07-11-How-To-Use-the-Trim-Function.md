---
layout: post
tags: 
- Google Sheets
- Excel
- 高效
title: Trim函数，避免空格错误的神器
excerpt: 
date: 2020.07.11 22:22:00
location: 上海
---

有的时候打字不仔细，就会在一个字符串的开头或者末尾地方添加很多多余的空格，平时放着还没什么问题，但是一旦添加了复杂的逻辑，比如说if判断、Text引用，Len长度计算，就会出现一些莫名其妙的错误，导致无法进行下去。那有什么好用的函数可以帮我们解决吗？

当然有啦，就是Trim函数。Trim是修剪的意思。

Trim函数的含义：Removes leading, trailing, and repeated spaces in text. 其实和修剪就是异曲同工对吧？所以说，学好英语实在能帮我们很多。

了解了含义，我们来了解一下Trim的语法规则：

**=Trim(字符串)**

来看看下面的字符串和他们修剪后的结果：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-11-How-To-Use-the-Trim-Function-1.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-11-How-To-Use-the-Trim-Function-1.png" title="字符串和他们的修剪后的结果" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-11-How-To-Use-the-Trim-Function-1.png">
	</a>
</div>

这里我们只强调最后两行。可以注意到第6行的字符串变短了，但是中间的空格还是存在，为什么呢？其实是函数的处理机制，如果是字符串的前后，那么直接去掉空格，一点都不犹豫，但是如果是字符串的中间出现了多个连续的空格，那么处理方式就变成了只保留1个空格。于是字符串中间的2个空格变成了1个空格。

第7行，虽然显示的好像去掉了换行符，但是如果你用**<a href="../../../2020/07/09/How-to-use-the-Len-Function/" target="_blank">len函数</a>**一检查，你就会发现，其实长度还是7。这是因为回车符号默认按照一个长度处理，且trim函数无法将空格修剪掉。不相信？我们用len函数配合一下：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-11-How-To-Use-the-Trim-Function-2.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-11-How-To-Use-the-Trim-Function-2.png" title="使用=Unique(B1:B16)后" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-11-How-To-Use-the-Trim-Function-2.png">
	</a>
</div>

Trim函数在和其他函数打配合、使用公式、条件判断的时候很有用，可以帮助我们避免很多麻烦。迅速get吧~是很简单好用的函数呐。

此外，**<a href="https://support.microsoft.com/zh-cn" target="_blank">微软支持中心网站</a>**和**<a href="https://support.google.com/docs#topic=1382883" target="_blank">谷歌文档编辑器帮助</a>**真的有很多非常有用的帮助文档，官方的解释总是更加详尽，大家一定要利用起来哦！

参考链接：
1. <a href="https://support.google.com/docs/answer/3094140?hl=en&ref_topic=3105625" target="_blank">Trim（谷歌）</a>