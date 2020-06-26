---
layout: post
tags: 
- Google Sheets
- Excel
- 高效
title: 简单又好用的transpose函数
excerpt: 
date: 2020.06.26 20:51:00
location: 上海
---

要想了解一个函数的使用方法，就要首先了解一下这个函数的含义。Transpose，中文翻译为转置。如果你还记得被转置矩阵支配的那个学期的恐惧。那么你已经非常熟悉这个函数了。

了解了含义，我们来了解一下Transpose函数的语法规则：

**=TRANSPOSE(一个数组或范围)**

来讲讲我为什么会用到这个函数。其实是在工作时，遇到个情况：工作簿中有一张总结表格，还有很多其他详细的分表格。而在总结表格中写到的内容，其实在分表格中也是成块聚集在一起的。懒得每次改文字都要去总结表格里面手动更新，再加上如果错误就是烦上加烦，所以就去研究有没有什么函数可以帮忙。果然被我找到一个，就是Transpose函数，简单又好用。

首先我们来看这样两张表格：

公司的总结表格，需要各部门填入自己的全年计划：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-26-How-to-use-the-Transpose-Function-0.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-26-How-to-use-the-Transpose-Function-0.png" title="公司的全年计划表" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-26-How-to-use-the-Transpose-Function-0.png">
	</a>
</div>

技术部的详细表格：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-26-How-to-use-the-Transpose-Function-1.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-26-How-to-use-the-Transpose-Function-1.png" title="技术部的全年计划" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-26-How-to-use-the-Transpose-Function-1.png">
	</a>
</div>

都说计划赶不上变化，虽然写了一个全年计划的表格，但是其实这也只是个初稿，之后肯定会改，每次改都去总表上做更新实在太累。于是我们用上了Transpose函数，让之后的更新都能自动被捕获。如下：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-26-How-to-use-the-Transpose-Function-2.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-26-How-to-use-the-Transpose-Function-2.png" title="使用Transpose函数，即使更新也不怕" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-26-How-to-use-the-Transpose-Function-2.png">
	</a>
</div>

完美，又节省了时间，也避免了错误！非常简单实用的函数。使用过程中需要注意以下两点：
1. 在谷歌表格和Excel 365中使用时，可以直接输入公式。但如果是更低版本的Excel，则要使用Enter + Shift + Ctrl来对数组函数进行操作才可以。
2. 数组函数要有足够的空间才能展开，否则会出现报错。所以请确保留出足够的空间。

此外，**<a href="https://support.microsoft.com/zh-cn" target="_blank">微软支持中心网站</a>**和**<a href="https://support.google.com/docs#topic=1382883" target="_blank">谷歌文档编辑器帮助</a>**真的有很多非常有用的帮助文档，官方的解释总是更加详尽，大家一定要利用起来哦！

参考链接：
1. <a href="https://support.google.com/docs/answer/3094262?hl=en" target="_blank">TRANSPOSE 函数（谷歌）</a>