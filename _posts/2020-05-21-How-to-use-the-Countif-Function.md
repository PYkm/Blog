---
layout: post
tags: 
- Google Sheets
- Excel
- 高效
title: 超有用的countif函数
excerpt: 
date: 2020.05.21 21:13:00
location: 上海
---

如果有人问我，在工作中，真的很经常使用的函数是什么？我一定会回答：COUNT相关的函数！count相关的函数有很多，最简单的有count，还有counta，然后就是countif，countifs。今天我们来介绍一下countif~

要想了解一个函数的使用方法，我们首先来了解一下这个函数的含义。countif = count + if，也就是说count A if B，**如果**B满足就去范围A里进行**数数**。造句：如果绩效考核大于3.5就是合格，那么数一数范围中有多少人合格。

了解了含义，我们来了解一下countif的语法规则：

**=COUNTIF(要去数数的范围A, 设置的条件B)**

再来看一个例子，又到了月底绩效考核的时间，公司规定，绩效分数达到3.5才算是合格，达到4分是优秀。老板让你计算一下，这个月合格的人有几个？看看下面的表格：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-21-How-to-use-the-Countif-Function-0.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-21-How-to-use-the-Countif-Function-0.png" title="“公司1”工作簿中的内容" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-21-How-to-use-the-Countif-Function-0.png">
	</a>
</div>

很简单你数了数，有6个。那么假设数据有1000条，怎么办，自己数么？且不说数据太多，再说你认真的数了也很可能会数错。更何况数据每个月都会变，如果每次都要手动去数数，岂不是平白增加了自己的工作量？况且，这一切其实只要一个函数就能搞定。就是下面这个。

=COUNTIF(F6:F14, ">=3.5")

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-21-How-to-use-the-Countif-Function-1.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-21-How-to-use-the-Countif-Function-1.png" title="好不容易用公式拼接了字符串，然而有不少问题" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-21-How-to-use-the-Countif-Function-1.png">
	</a>
</div>

这个函数虽然解决了我们的问题，但是可复用性不强。如果下个月领导把绩效考核分数调高了，那岂不是还要进入公式改？而且如果这个表格交给了同事去更新，那么还要麻烦同事点击每个函数去看每个月的绩效分数？我们的目标是避免麻烦！于是我们在此基础上进行了调整，这下及格分数一目了然，即使更改条件也一目了然，省了很多事：

=COUNTIF(F6:F14,">="&A2)

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-21-How-to-use-the-Countif-Function-2.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-21-How-to-use-the-Countif-Function-2.png" title="好不容易用公式拼接了字符串，然而有不少问题" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-21-How-to-use-the-Countif-Function-2.png">
	</a>
</div>

现在，大功告成啦~我们成功的完成了报表自动化的一步。其实学校评奖学金的绩点、班级成绩分段、年龄段分布都可以用这个函数，非常有用又省事哦！

此外，**<a href="https://support.microsoft.com/zh-cn" target="_blank">微软支持中心网站</a>**真的有很多非常有用的帮助文档，官方的解释总是更加详尽，大家一定要利用起来哦！

参考链接：
1. <a href="https://support.office.com/zh-cn/article/countif-%E5%87%BD%E6%95%B0-e0de10c6-f885-4e71-abb4-1f464816df34" target="_blank">COUNTIF 函数</a>