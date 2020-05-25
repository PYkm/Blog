---
layout: post
tags: 
- Google Sheets
- Excel
- 高效
title: 超好用的条件格式，别说你不知道
excerpt: 你用过Excel的条件格式吗？如果你从来没用过，甚至没听说过，那你一定要点进来了解一下这个超有用的功能哦！
date: 2020.05.26 14:18:00
location: 上海
---

最近遭遇了一个困境：想要从一组数据中找出客户想要的数据，然后标红，告诉客户结果。以往都是这么做的：
1. 添加一个过滤列；
2. 用if函数做判断，结果用Y/N来表示；
3. 把Y过滤出来；
4. 手动标红。

但遇到的问题也很明显：

1. 只是为了标红满足条件的数据，就用了4步；
2. 如果数据改了或条件改了，标红的就乱套了，以上四步需要返工。

这样不智能的事情不应该发生才对，于是开始寻找解决办法，于是就找到了超好用的**条件格式(Conditional Formatting)**

按照惯例，分析一下条件格式是什么意思。条件格式(Conditional Formatting)，在满足**附件条件**的时候更改其**格式**。于是这一功能的最终目的表露无疑，就是我们想要的功能啊！

这个功能的使用方法是（以Excel 2003为例）：
1. 选中要进行“条件格式”的数据；
2. 选择“格式” --> “条件格式”；
3. 选择或输入“条件”；
4. 更改其“格式”；
5. 点击“确定”即可。

下面来看一个场景案例：

你是一名语文老师，想要了解办理9个学生的语文成绩状况，分为三档：
1. 不及格（<60分） - 红色
2. 良好（60-84分） - 黄色
3. 优秀  （>84分） - 绿色


选中数据区域，设置条件格式：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-26-How-to-use-Conditional-Formatting-middle.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-26-How-to-use-Conditional-Formatting-middle.png" title="选择条件和格式" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-26-How-to-use-Conditional-Formatting-middle.png">
	</a>
</div>

设置了条件格式后：

<div class="zoom-pic-half">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-26-How-to-use-Conditional-Formatting-after.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-26-How-to-use-Conditional-Formatting-after.png" title="添加条件格式后" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-26-How-to-use-Conditional-Formatting-after.png">
	</a>
</div>

不是只能对数字设置，你还可以设置其他公式。想要了解更多选项和更多案例。点击下方的参考链接即可哦~

此外，**<a href="https://support.microsoft.com/zh-cn" target="_blank">微软支持中心网站</a>**真的有很多非常有用的帮助文档，官方的解释总是更加详尽，大家一定要利用起来哦！

参考链接：
1. <a href="https://support.office.com/zh-cn/article/%E4%BD%BF%E7%94%A8%E6%9D%A1%E4%BB%B6%E6%A0%BC%E5%BC%8F%E7%AA%81%E5%87%BA%E6%98%BE%E7%A4%BA%E4%BF%A1%E6%81%AF-fed60dfa-1d3f-4e13-9ecb-f1951ff89d7f" target="_blank">条件格式</a>