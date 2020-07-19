---
layout: post
tags: 
- Google Sheets
- Excel
- 高效
title: 超简单函数：Len
excerpt: 
date: 2020.07.09 21:59:00
location: 上海
---

在编程中，我们经常会需要判断字符串的长度。那么excel也可以计算吗？答案是肯定的。请出今天的主角Len函数啦~ 这个函数结合if等函数可以实现更复杂的目标哦。

我们先来了解一下这个函数的含义。Len：长度。Returns the length of a string.

了解了含义，我们来了解一下len的语法规则：

**=Len(字符串)**

来看看下面的字符串和他们的长度计算结果：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-09-How-To-Use-the-Len-Function-1.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-09-How-To-Use-the-Len-Function-1.png" title="字符串和对应的Len值" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-09-How-To-Use-the-Len-Function-1.png">
	</a>
</div>


第1个很好理解，英文是半角符号，按照字母个数来算。

第2个，虽然中文都是全角符号，但个数还是按照字数，而不是字数 X 2，所以大家要注意，其实这样的答案更符合我们的逻辑。

第3个和第4个分别在开头、开头和结尾处添加了两个空格。要注意，空格也会被算在len里面。

第5个，添加了一个回车的符号，这个符号也记作一个长度。

所以这个超级简单地函数在使用时需要注意的点，就是字符串中的空格、换行等符号都会被记录在内。如果不想出现错误的答案，填写表格的时候一定要小心哦！如果想要免除空格的干扰，可以配合**<a href="../../../2020/07/11/How-to-use-the-Trim-Function/" target="_blank">trim函数</a>**进行使用，像这样：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-09-How-To-Use-the-Len-Function-2.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-09-How-To-Use-the-Len-Function-2.png" title="配合trim函数使用" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-09-How-To-Use-the-Len-Function-2.png">
	</a>
</div>

但是trim函数不会处理换行符哦，所以还是要注意！

此外，**<a href="https://support.microsoft.com/zh-cn" target="_blank">微软支持中心网站</a>**和**<a href="https://support.google.com/docs#topic=1382883" target="_blank">谷歌文档编辑器帮助</a>**真的有很多非常有用的帮助文档，官方的解释总是更加详尽，大家一定要利用起来哦！

参考链接：
1. <a href="https://support.google.com/docs/answer/3094081" target="_blank">Len（谷歌）</a>