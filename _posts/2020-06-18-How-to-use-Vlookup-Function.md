---
layout: post
tags: 
- Google Sheets
- Excel
- 高效
title: 超常用函数vlookup，让你以后想用就用
excerpt: 是不是看过千遍vlookup的使用方法，到用的时候还是不会用？进来看，让你之后想用就用！
date: 2020.06.18 20:11:00
location: 上海
---

我们是不是经常会有这样的需求？需要去一大堆数据、图表里找到需要用的那个信息。当然，每次Ctrl + F搜索关键字是可以搜索到，但每次都要你自己去手动查找、翻阅，是不是也太不智能了呀？既然这样干脆做一个类似数据库查找操作的小界面不是很省事吗？说干就干，Let's go!

要想了解一个函数的使用方法，我们首先来了解一下这个函数的含义。vlookup = v + lookup，这里的v是vertical的简写。也就是vertical lookup. Searches down the first column of a range for a key and returns the value of a specified cell in the row found. 即纵向查找。在范围的第一列中自上而下搜索某个键（和Ctrl + F查找关键词一样），并返回找到的这一行中指定单元格的值。

了解了含义，我们来了解一下vlookup的语法规则：

**=VLOOKUP(键, 范围, 索引, [可选，是否模糊匹配])**

造句：请拿着**键**去**范围**中的第一列，自上而下找，找到之后请返回给我位于**范围**第**索引**列的对应值。最后一个参数可选，默认为TRUE（是模糊匹配）。模糊匹配：找到第一个相似的键后就返回位于索引处的单元格的值。很显然，最后一个参数，通常情况都是要设置成**FALSE**的，所以使用这个函数时，一定要记住，我们通常四个参数都会填！


再来看一个例子，领导让你给她一个前台界面，只要他输入/选择姓名，就能自动在旁边显示这位员工的工资。于是你大概改变了文档的样式，像这样：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-18-How-to-use-Vlookup-Function-1.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-18-How-to-use-Vlookup-Function-1.png" title="初始文档样式" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-18-How-to-use-Vlookup-Function-1.png">
	</a>
</div>


现在要用到函数了，才能帮助我们实现员工的对应的工资显示的自动化。

1. **键。**很明确，就是姓名，为了自动化，我们这里填A3
2. **范围。**因为函数已经确定了范围中的第一列必须是键所在的地方，所以范围中的第一列必须是姓名，这里是A列。范围中必须要包含想要知道的值，也就是月薪，所以我们选E列。那么范围就是A6:E15。
3. **索引。**值所在的列，月薪，在范围中是第5列，所以是5。
4. **[是否模糊查找]。**如上所说，这里是FALSE或者是0（计算机理解的2进制，1 = TRUE, 0 = FALSE）。

这样确定下来，应该填写的公式是：

**=VLOOKUP(A3, A6:E15, 5, FALSE)**

或

**=VLOOKUP(A3, A6:E15, 5, 0)**

放进表格里面试试：
<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-18-How-to-use-Vlookup-Function-2.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-18-How-to-use-Vlookup-Function-2.png" title="使用=VLOOKUP(A3, A6:E15, 5, 0)后" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-06-18-How-to-use-Vlookup-Function-2.png">
	</a>
</div>

大功告成！没错，就是这么简单。以后还要用VLOOKUP？别着急，按照之前我们造的句，对号入座，多用几次就熟能生巧啦~

看到这里你还没走？说明你是个有好奇心的宝宝。你的心里是不是有两个问题？
1. 既然有Vertical lookup，是不是也应该有Horizontal lookup才公平啊？**没错，有！想知道更多，点击下方参考链接**
2. 如果第四个参数我没填，就是TURE，会是什么答案？**案例中的答案是“月薪”，是不是很离谱？所以千万不要忘记这个参数要写FALSE或者0哦**

此外，**<a href="https://support.microsoft.com/zh-cn" target="_blank">微软支持中心网站</a>**和**<a href="https://support.google.com/docs#topic=1382883" target="_blank">谷歌文档编辑器帮助</a>**真的有很多非常有用的帮助文档，官方的解释总是更加详尽，大家一定要利用起来哦！

参考链接：
1. <a href="https://support.microsoft.com/zh-cn/office/vlookup-%E5%87%BD%E6%95%B0-0bbc8083-26fe-4963-8ab8-93a18ad188a1" target="_blank">VLOOKUP（微软）</a>
2. <a href="https://support.office.com/zh-cn/article/HLOOKUP-%E5%87%BD%E6%95%B0-A3034EEC-B719-4BA3-BB65-E1AD662ED95F" target="_blank">HLOOKUP（微软）</a>
3. <a href="https://support.google.com/docs/answer/3093318?hl=zh-Hans&ref_topic=9054531" target="_blank">VLOOKUP（谷歌）</a>
4. <a href="https://support.google.com/docs/answer/3093375?hl=zh-Hans" target="_blank">HLOOKUP（谷歌）</a>