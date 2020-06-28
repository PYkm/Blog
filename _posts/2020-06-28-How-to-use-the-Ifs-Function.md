---
layout: post
tags: 
- Google Sheets
- Excel
- 高效
title: 你一定会想用的函数：Ifs
excerpt: 
date: 2020.06.28 21:45:00
location: 上海
---

要想了解一个函数的使用方法，就要首先了解一下这个函数的含义。Ifs = If + s，中文翻译为好几个如果。这个函数会评估多个条件并返回与第一个真实条件相对应的值。所以，这是一个如果A就B，如果C就D的函数。

了解了含义，我们来了解一下Ifs函数的语法规则：

**=IFS(条件1, 返回值1, [条件2, 返回值2, …])**

当只有一对参数时，Ifs函数和If函数功能一样。

来讲讲什么情况下会经常用到这个函数，比如说，你是个语文老师，每一次考试，你都需要把班里学生的成绩汇总一下反馈给班级的班主任，可是每次都自己手工去数，重复劳作不说，还容易数错。于是你决定借用Excel这个强大的工具实现统计的自动化。

你已经把学生成绩输入到表格中了，像这样：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-0.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-0.png" title="学生分数表" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-0.png">
	</a>
</div>

首先你确定了成绩分段的条件：
1. 85+ 优秀 
2. 70-85 良好
3. 60-70 合格
4. 60- 不及格

为了实现分段我们添加一列“成绩”，并分析如何使用Ifs函数。

1. 条件1: >85，返回值1: "优秀"
2. 条件2: >=70，返回值2: "良好"
3. 条件3: >=60，返回值3: "合格"
4. 条件4: <60，返回值4: "不及格"

这里的条件2-3只写了大于的条件，而不是判断区间，原因就是：这个函数会评估多个条件并返回与**第一个真实条件**相对应的值。比如说90分，满足条件1直接返回值，而不会再向下判断。而80分，因为不满足条件1，于是去条件2判断，并且返回值。所以条件更简单了。

于是我们汇总了参数，制作了这样的公式：

**=IFS(C3 >85, "优秀", C3 >=70, "良好", C3 >=60, "合格", C3 <60, "不及格")**


<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-1.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-1.png" title="添加一列“成绩”，加入IFS函数" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-1.png">
	</a>
</div>


接下来，我们还可以结合之前提到的**<a href="../../../2020/05/26/How-to-use-Conditional-Formatting/" target="_blank">条件格式</a>**，让整个表格显示的更鲜明：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-2.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-2.png" title="使用条件格式，让表格显示更鲜明" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-2.png">
	</a>
</div>

也可以配合使用之前提到的**<a href="../../../2020/05/21/How-to-use-the-Countif-Function/" target="_blank">countif</a>**方便的统计班级中四个分段的学生人数：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-3.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-3.png" title="使用countifs函数，统计各分段学生人数" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-28-How-to-use-the-Ifs-Function-3.png">
	</a>
</div>

是不是觉得很方便，又节省了很多时间？要结合之前的知识点一起学习哦~

此外，**<a href="https://support.microsoft.com/zh-cn" target="_blank">微软支持中心网站</a>**和**<a href="https://support.google.com/docs#topic=1382883" target="_blank">谷歌文档编辑器帮助</a>**真的有很多非常有用的帮助文档，官方的解释总是更加详尽，大家一定要利用起来哦！

参考链接：
1. <a href="https://support.google.com/docs/answer/7014145?hl=en&ref_topic=3105413" target="_blank">IFS 函数（谷歌）</a>