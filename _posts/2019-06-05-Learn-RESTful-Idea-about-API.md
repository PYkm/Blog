---
layout: post
tags: 
- Web Front-End
title: RESTful API 设计理念
excerpt: 请注意这里假设你对web有一定的基础知识，并且已经熟悉了API，如果你还对API的概念模棱两可，建议你先查看我的上一篇博文([传送门]({{ site.url }}/{{ site.baseurl }}/2019/06/05/The-Concept-of-API.html))。
date: 2019.06.05 20:32:15
location: 上海
---

请注意这里假设你对web有一定的基础知识，并且已经熟悉了API，如果你还对API的概念模棱两可，建议你先查看我的上一篇博文([传送门]({{ site.url }}/{{ site.baseurl }}/2019/06/05/The-Concept-of-API.html))。
那么我们现在开始进入正题，首先看RESTful这个单词。和beautiful这个单词一样，RESTful是个形容词，<strong>ful</strong>这个词尾代表这个单词是个形容词，翻译为“的”，那么RESTful API就译为满足REST的API。

而REST? 其实这是一些单词的缩写，即<strong>Representational State Transfer</strong> 表现层的状态转化。看了之后还是一头雾水？没关系，我们来每逐字介绍：

### 一、Representational(表现层的)

这里的Representation指的是<strong>网络资源</strong>的表现层。

<strong>网络资源</strong>很好理解。我们都是通过互联网来实现“上网/冲浪”操作的。而我们使用互联网访问的所有东西都是资源。网页中的可下载的文件、可浏览图片、文字、音频、视频，甚至你看到的这个页面都是资源！这些资源都存在于互联网中的某台服务器中，我们通过URI来访问这些资源。

而<strong>表现层</strong>就是指这些资源呈现出来的形式。比如说，可下载的文件可以是Word、Excel、PowerPoint、Exe、Zip等格式；可浏览图片可以是jpg、png，也可以是gif等格式；文字可以是txt，也可以是html、xml等格式；音频可以是mp3也可以是wma、rm；视频可以是mp4也可以是rmvb、mkv。

这里需要注意的是：
URI只代表资源的实体，不代表它的形式。它的具体表现形式，应该在HTTP请求的头信息中用Accept和Content-Type字段指定。如果你当前使用的是chrome浏览器，那么你可以F12打开“开发者工具”，在其中找到“Network”标签，刷新当前页面，点击任意资源名，在右侧会显示其对应的http请求以及响应结果。打开其中的“Request Header”可以看到accept: ...... 的一行数据。这里的数据内容就是表现层了。请查看下面这个截图示例(点击放大)：
<div class="zoom-gallery">
	<a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2019-06-05-Learn-RESTful-Idea-about-API-I.png" data-detail="在Chrome中查看表现层细节" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2019-06-05-Learn-RESTful-Idea-about-API-I.png" title="表现层" style="width:1000px; height:331px;">
		<img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2019-06-05-Learn-RESTful-Idea-about-API-I.png" width="500" height="165">
	</a>
</div>


### 二、State(状态)

这里的状态和http协议有很大关系。我们都知道http是无状态协议。无状态就是指，当你使用http协议访问/操作资源时，服务器端并不会记下你是谁，你做了什么。比如说，你在饿了么点外卖，你在店铺页面选择了一家店铺，你进去点了一篮子的美食，结果结账的时候发现篮子是空的，你的时间和心血都白费了！这就是无状态的表现。但是为什么这个例子和我们日常的经历完全不同呢？这是因为工程师们为了让整个流程合理(结账时篮子里是你点的食物，不多不少)已经使用Cookie(客户端保存状态)或Session(服务端保存状态)将你在前一个页面的操作结果(状态)保存下来了，这样才实现了正常的功能。

淘宝购物车、信息填写页面，甚至最简单的登录到微博/微信(网页版)也都是使用了这些技术来手动的存取状态。


### 三、Transfer(转换)

知道了状态的概念我们来理解什么是转换。既然Http是无状态协议，那么如果我们(客户端)想要去操作服务器，就需要通过某种手段，让服务器端的状态发生转换。就像上面提到的Cookie和Session。请注意，这些状态转化是建立在表现层之上的。

看到这里想必你就明白了。那我们来总结看看。


### 四、Representational State Transfer

表现层状态转换，建立在资源的表现层上的状态的转换。我们知道常用的http request中有五个动词：

动词 | 行为 |  解释  
-|-|-
GET |  SELECT  |  从服务器取出资源（一项或多项）
POST |  CREATE  |  在服务器新建一个资源
PUT | UPDATE | 在服务器更新资源（客户端提供改变后的完整资源） |
PATCH | UPDATE | 在服务器更新资源（客户端提供改变的属性）, 通常是部分更新 |
DELETE | DELETE | 从服务器删除资源 |


这里强调一点，RESTful API的核心就是执行某访问/修改动作时，将其写作：

动词 URL(宾语)，例如：

√ GET /articles

× GET /getArticles


写在最后的注意：RESTful并不是一种标准，而是一种设计风格。
其他更多实际的建议请点击我的参考链接1进行查看。

本博客参考链接：
1. [RESTful API Design: 13 Best Practices to Make Your Users Happy](https://blog.florimond.dev/restful-api-design-13-best-practices-to-make-your-users-happy/)
2. [RESTful API 最佳实践](http://www.ruanyifeng.com/blog/2018/10/restful-api-best-practices.html)