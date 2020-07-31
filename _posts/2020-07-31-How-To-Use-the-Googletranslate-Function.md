---
layout: post
tags: 
- Google Sheets
- 高效
title: Googletranslate函数，帮你快速翻译文字
excerpt: 
date: 2020.07.31 22:37:00
location: 上海
---

你的工作经常需要你把文字翻译成另一种语言吗？虽然机器翻译不是特别准确，但是审核校对总比自己打字省时间吧。所以我来推荐工具啦~

Google Sheets中才可以使用的函数：Googletranslate函数。OK，我知道这个单词有点长，但是其实就是google + translate啊，所以函数名还是比较好记得呢。

我们来了解一下Googletranslate的语法规则：

**=Googletranslate(文本,[源语言],[目标语言])**

记忆方法：拿着文本，把它从源语言翻译为目标语言。[]表示选填。注意源语言如果没填，目标语言也不要填哦！如果源语言没有填，那么其实默认值为"auto"，如果目标语言没有填，那么其实默认就是系统语言。好像有那么一点道理哈。这里的源语言、目标语言位置只需要填字母语言代码就好了。常用的英文是"en"，中文简体是"zh"，中文繁体是"zh-Hant"。如果你不确定字幕语言代码是什么，可以使用detectlanguage函数。

来看看使用Googletranslate函数的样子：

<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-31-How-To-Use-the-Googletranslate-Function-0.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-31-How-To-Use-the-Googletranslate-Function-0.png" title="字符串和他们的修剪后的结果" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-31-How-To-Use-the-Googletranslate-Function-0.png">
	</a>
</div>

下面这个函数使用时未填充后面两个参数：
<div class="zoom-pic-full">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-31-How-To-Use-the-Googletranslate-Function-1.png" data-detail="" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-31-How-To-Use-the-Googletranslate-Function-1.png" title="字符串和他们的修剪后的结果" style="width:251px; height:120px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2020-07-31-How-To-Use-the-Googletranslate-Function-1.png">
	</a>
</div>

此外，**<a href="https://support.microsoft.com/zh-cn" target="_blank">微软支持中心网站</a>**和**<a href="https://support.google.com/docs#topic=1382883" target="_blank">谷歌文档编辑器帮助</a>**真的有很多非常有用的帮助文档，官方的解释总是更加详尽，大家一定要利用起来哦！

参考链接：
1. <a href="https://support.google.com/docs/answer/3093331?hl=en" target="_blank">GOOGLETRANSLATE（谷歌）</a>
2. <a href="https://support.google.com/docs/answer/3093278" target="_blank">DETECTLANGUAGE（谷歌）</a>