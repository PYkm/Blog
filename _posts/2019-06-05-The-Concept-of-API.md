---
layout: post
tags: 
- Web Front-End
title: API到底是什么？
excerpt: 很多人一看接口就觉得很难，不知所云。其实看英语<strong>Interface</strong>，也有界面的意思，现在是不是有点感觉了？看了下面的例子你一定会恍然大悟。现在智能手机、智能手表、掌上电脑等等设备层出不穷，对于手机来说，一点亮屏幕，你看到的就是<strong>Interface</strong>，你在手机上按几个数字就可以打电话了；
date: 2019.06.05 16:13:00
location: 上海
---

<strong>API(Application Programming Interface)</strong>应用程序接口。

很多人一看接口就觉得很难，不知所云。其实看英语<strong>Interface</strong>，也有界面的意思，现在是不是有点感觉了？看了下面的例子你一定会恍然大悟。现在智能手机、智能手表、掌上电脑等等设备层出不穷，对于手机来说，一点亮屏幕，你看到的就是<strong>Interface</strong>，你在手机上按几个数字就可以打电话了；对于电脑来说(假设为Windows系统)，开机后你看到的桌面(desktop)就是<strong>Interface</strong>，你可以设置无线来访问网络、查看文件夹中的文件...

让我们再具体一点，我们每天都会在手机或者电脑上使用一双手都数不过来的应用程序(APPs)。比如说，手机上大多是微信、QQ、微博、知乎、豆瓣、Bilibili；再比如说，电脑上，计算器、浏览器、HBuilder、Word。这些我们经常使用的应用程序也叫做软件。

而API就是一个让我们可以无障碍的和应用程序交流<strong>(其实就是使用APP)</strong>，来实现我们想要实现的功能<strong>(聊天、查找信息)</strong>的一个接口<strong>(界面)</strong>。当你使用这些应用程序时你不需要知道这个应用程序是用什么语言写的，当你使用这些程序时，只要简单地在屏幕上点几个选项、在键盘上输入文字(如果有必要)就可以完成你想做的事了。而这一切的实现都是因为有了API(应用程序接口)。

为了方便理解我们举一个现实生活中经常碰到的情况：买早餐。买早餐的过程是，你走到早餐店(应用程序)，告诉店员(接口/界面)，我要买菜包和八宝粥(想要实现的功能)。那么显然这里的店员就是API，他让你不需要自己进到笼屉前自己去找菜包和八宝粥，他完成了你和早餐店店铺之间的交互。

为了方便你的记忆，请看下图：
<div class="zentangle">
	<img title="API的概念图" src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2019-06-05-The-Concept-of-API-I.jpg"/>
</div>

<br>
<hr><br>

看完了这张图，我们来讲讲web中的API。通常API有两种形式：XML和JSON。
这里以github提供的[API](https://api.github.com/)为例(删减部分数据，并以省略号代替)：

{% highlight json %}
{
  ......
  "emails_url": "https://api.github.com/user/emails",
  "emojis_url": "https://api.github.com/emojis",
  "events_url": "https://api.github.com/events",
  "feeds_url": "https://api.github.com/feeds",
  "followers_url": "https://api.github.com/user/followers",
  "following_url": "https://api.github.com/user/following{/target}",
  "gists_url": "https://api.github.com/gists{/gist_id}",
  "hub_url": "https://api.github.com/hub",
  "issue_search_url": "https://api.github.com/search/issues?q={query}{&page,per_page,sort,order}",
  "issues_url": "https://api.github.com/issues",
  "keys_url": "https://api.github.com/user/keys",
  "notifications_url": "https://api.github.com/notifications",
  "organization_repositories_url": "https://api.github.com/orgs/{org}/repos{?type,page,per_page,sort}",
  ......
}
{% endhighlight %}

这里返回的API是JSON格式的。由键值对组成，和JS中的对象格式一样，因此提取其中的属性等操作非常的方便。这里有个小技巧，如果你点击这个[链接](https://api.github.com/users/pykm)。可以看到用户pykm的头像地址、最近一次登录时间等等相关信息，你可以自己发掘更多有趣的链接，也非常欢迎与我分享。


如果你还想知道怎样的API是RESTful的，以及怎样设计RESTful API。欢迎点击我的下一篇博文！