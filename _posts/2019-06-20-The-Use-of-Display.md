---
layout: post
tags: 
- Web Front-End
title: flex布局还是float?
excerpt: 怎样在flex和float+posion+display之间做选择？
date: 2019.06.21 16:44:00
location: 上海
---

Q: 怎样在flex和float+posion+display之间做选择？
A: 首先必须强调，flex的出现就是为了让页面布局变得更轻松。所以一般推荐可以使用flex时，就使用flex。为了解答这个疑惑，请认真看完本片博文。 


<strong>Flex</strong>(Flexible Box，弹性盒子)。一个非常有弹性的盒子，意味着可伸缩、可调整。它的出现就是为了让页面布局变得更轻松。
通过设置<code>display:flex;</code>可以将一个<strong>块级</strong>元素设置为弹性布局。
也可以添加<code>display:inline-flex;</code>将一个<strong>行内</strong>
元素设置为弹性布局。

举例如下(为方便直接复制，将CSS与HTML写于同一文件index.html中)：
{% highlight html %}
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Flex布局示例</title>
    <style type="text/css">
      #parent{
        /*
        display: flex;
        flex-direction:row;
        flex-wrap: nowrap;
        */
      }
      #child1{
        background: yellowgreen;
        height:100px;
      }
      #child2{
        background: skyblue;
        height:200px;
      }
      #child3{
        background: palevioletred;
        height:150px;
      }
    </style>
  </head>
  <body> 
    <div id="parent">
      <div id="child1">
        我是child 1，我不想让你只是看着我
      </div>
      <div id="child2">
        我是child 2，我喜欢蓝色
      </div>
      <div id="child3">
        我是child 3
      </div>
      我就想看看会怎样
    </div>
  </body>
</html>

{% endhighlight %}

id="parent"的div未设置<code>display:flex;</code>时的页面如下：

<div class="zoom-gallery">
  <a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2019-06-20-The-Use-of-Display-I.png" data-detail="id为parent的div未设置flex时的页面" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2019-06-20-The-Use-of-Display-I.png" title="Flex未设置" style="width:259px; height:85.5px;">
    <img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2019-06-20-The-Use-of-Display-I.png" width="259" height="85.5">
  </a>
</div>

这是取消注释(加上flex属性)后：
<div class="zoom-gallery">
  <a href="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2019-06-20-The-Use-of-Display-II.png" data-detail="id为parent的div设置flex后的页面" data-source="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2019-06-20-The-Use-of-Display-II.png" title="Flex已设置" style="width:259px; height:85.5px;">
    <img src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2019-06-20-The-Use-of-Display-II.png" width="259" height="85.5">
  </a>
</div>

如果是使用<code>float:left;</code>进行设置我们同样可以达到同样的效果。那么为什么我还推荐使用flex？

{% highlight css %}
#parent{
  display: flex;
  flex-direction:row;
  flex-wrap: nowrap;
}
{% endhighlight %}

首先，就像上面写的这样，我们只要三行，甚至更少的CSS语句就可以完成使用float可能要占用十几甚至二十行的代码才能完成的设置。

其次，flex存在本身就是为了简化页面布局的设计难度。使用float，必须要注意使用<code>clear:both;</code>将之后不参与浮动的元素的浮动清除。这样还会造成一些其他麻烦，比如此时的最外层div的高度会有问题，必须重新设置，调整。

再者，还有其他与flex有关的属性可以设置(具体请查看下面列出的本博客参考链接，不一一介绍)。这一设置大大的减少了工程师的工作量。

#### 这里必须注意，设为 Flex 布局以后，子元素的float、clear 和 vertical-align 属性将失效。

那么，本次博客就介绍这些，更多细节欢迎点击下面的链接。

本博客参考链接：
1. [A visual guide to css3 flexbox properties](https://scotch.io/tutorials/a-visual-guide-to-css3-flexbox-properties)
2. [Flex 布局教程：语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)