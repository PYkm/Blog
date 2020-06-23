---
layout: post
tags: 
- Google Sheets
- Excel
- 高效
title: countifs函数
excerpt: 除了countif这个非常常用的函数，countifs这个双胞胎姐妹也很有用，会经常用到哦，点进来了解更多详情吧！
date: 2020.06.21 20:35:00
location: 上海
---

其实除了count A if B（也就是**<a href="../../../2020/05/21/How-to-use-the-Countif-Function/" target="_blank">countif</a>**）以外，我们还经常会遇到这样的需求：count if A, B and C.即：如果A、B、C都满足的情况下数数。于是就要请出今天的主角啦：countifs

要想了解一个函数的使用方法，我们首先来了解一下这个函数的含义。countifs = count + ifs，也就是说count if A[, B & C & ...]，**如果**A[、B、C……]满足就去范围里进行**数数**。

了解了含义，我们来了解一下countifs的语法规则：

**=COUNTIFS(要去数数的范围A1, 设置的条件A2,[要去数数的范围B1，设置的条件B2...]**

其中[]里的内容是可选的。所以只有一对A的时候，countifs=countif函数。

举例如下：统计医院不同科室有多少个男医生，有多少女医生。

首先我们有了这样一张表：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-21-How-to-use-the-Countifs-Function-1.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-21-How-to-use-the-Countifs-Function-1.png" title="“统计报表”工作簿中的内容" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-21-How-to-use-the-Countifs-Function-1.png">
	</a>
</div>

我们搭好了基本框架，相当于一个前台显示页面。

而这，是我们的数据支持，包括医生的姓名、性别、所在科室、详情：
<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-21-How-to-use-the-Countifs-Function-2.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-21-How-to-use-the-Countifs-Function-2.png" title="背后的数据支持，50名医生的数据" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-21-How-to-use-the-Countifs-Function-2.png">
	</a>
</div>

接下来，就是确定公式。假设我们要统计科室为“内科”且细分为“呼吸内科”的性别为“女”的医生的个数。那么

1. 条件1。统计科室=“内科”
2. 条件2。细分=“呼吸内科”
3. 条件3。性别=“女”

查找范围和条件成对出现。再分析如下：
1. 数数的范围：'科室医生数据'!C:C（“科室医生数据”中的第C列）。 设置的条件："内科"。
2. 数数的范围：'科室医生数据'!D:D（“科室医生数据”中的第D列）。 设置的条件："呼吸内科"。
3. 数数的范围：'科室医生数据'!B:B（“科室医生数据”中的第B列）。 设置的条件："女"。

于是统计科室为“内科”且细分为“呼吸内科”的性别为“女”的医生的个数的公式为：

=countifs('科室医生数据'!C:C, "内科", '科室医生数据'!D:D, "呼吸内科", '科室医生数据'!B:B, "女")

写好了一个，其他的就好总结了~为了复用，我们把条件改为单元格地址，整理如下：

**=countifs('科室医生数据'!C:C,A2,'科室医生数据'!D:D,B2,'科室医生数据'!B:B,"女")**

而对应的男医生的个数为：

=countifs('科室医生数据'!C:C,A2,'科室医生数据'!D:D,B2,'科室医生数据'!B:B,"男")

将函数填充进表格内，得出以下结果：
<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-21-How-to-use-the-Countifs-Function-3.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-21-How-to-use-the-Countifs-Function-3.png" title="填入函数" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-21-How-to-use-the-Countifs-Function-3.png">
	</a>
</div>

不放心的小伙伴可以随机挑选一种进行检查呦~


现在，大功告成啦~我们成功的完成了报表统计的自动化，又省了不少时间。大家可以扩展更多的使用场景哦！

此外，**<a href="https://support.microsoft.com/zh-cn" target="_blank">微软支持中心网站</a>**和**<a href="https://support.google.com/docs#topic=1382883" target="_blank">谷歌文档编辑器帮助</a>**真的有很多非常有用的帮助文档，官方的解释总是更加详尽，大家一定要利用起来哦！

参考链接：
1. <a href="https://support.google.com/docs/answer/3256550?hl=en" target="_blank">COUNTIFS 函数（谷歌）</a>