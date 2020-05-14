---
layout: post
tags: 
- Google Sheets
- Excel
- 高效
title: 什么机缘巧合让我学会了用Text函数
excerpt: 
date: 2020.05.12 19:55:00
location: 上海
---

因为我是比较追求“简约”、“自动化”的人（好吧，我就是懒），所以当我发现一个单元格中的文字需要我每次手动去更新的时候就有点崩溃。想必大家也很有感触，因为自己去更新就有极大的可能弄错，或者干脆忘记了更新，所以我就想一定要把这个单元格设置成自动化更新的，这样妈妈再也不用担心我忘记更新啦~

如果你也是一个喜欢高效、“自动化”的人，那就和我一起看下去吧！

下面是我工作的表格，其中工作簿“公司1”、“公司2”、“公司3”里的数据支持部分的数据不一样，但其他结构是一样的，让我手动去更新每张表的“总结”部分岂不是要累死我？

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-12-How-to-use-the-Text-function-before.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-12-How-to-use-the-Text-function-before.png" title="“公司1”工作簿中的内容" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-12-How-to-use-the-Text-function-before.png">
	</a>
</div>

于是我使用了concatenate函数、无数个被双引号包裹的字符串、几个引用的单元格地址、几个其他公式，终于完成了自动化，长舒一口气，觉得是时候捧起一本书看看了。结果！敲击回车之后，被眼前这凌乱的单元格吓了一跳：
<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-12-How-to-use-the-Text-function-middle.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-12-How-to-use-the-Text-function-middle.png" title="好不容易用公式拼接了字符串，然而有不少问题" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-12-How-to-use-the-Text-function-middle.png">
	</a>
</div>


月薪不是我想要的千分位的数字格式，绩效平均分也不是我想要保留的两位小数点。失望！这都是什么？！难道我的自动化大业终究无法实现？噢，我的心好痛啊！


但是我怎么可能是这么容易就服输的人呢，于是我开始夜以继日的查资料。终于，在我不懈努力的查找之下，让我发现了这个函数：Text函数，他就像是黑夜里的一盏灯，照亮了我前进的路。感恩！经过查找，我最终把单元格中的内容变成我想要的格式：
<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-12-How-to-use-the-Text-function-after.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-12-How-to-use-the-Text-function-after.png" title="用TEXT函数纠正了数据部分的格式" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-05-12-How-to-use-the-Text-function-after.png">
	</a>
</div>


接下来只要把公式复制到其他的几个工作簿中就可以完成自动化，以后只要把下载下来的数据更新到工作簿中就好了。就算是遇到其他的数据，我也可以轻松处理啦~

这里需要注意的一点是，TEXT函数会把传入的数据都转化为text(文本)，所以如果你之后还想要对数值做数字运算（加法、减法之类的），记得引用原来单元格。或者说，其实你的单元格只有一个数字（不是像例子中那样需要拼接）的话，那么调整格式请使用“设置单元格格式”里面的选项来进行更改哦！这样不会改变单元格的数据类型！

此外，**<a href="https://support.microsoft.com/zh-cn" target="_blank">微软支持中心网站</a>**真的有很多非常有用的帮助文档，官方的解释总是更加详尽，大家一定要利用起来哦！

参考链接：
1. <a href="https://support.office.com/zh-cn/article/text-%E5%87%BD%E6%95%B0-20d5ac4d-7b94-49fd-bb38-93d29371225c" target="_blank">Text函数</a>