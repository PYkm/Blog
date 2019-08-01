---
layout: post
tags: 
- Web Front-End面试
title: Beats上海彼邑公司前端面试
excerpt: 拎着大雨，裤子都湿了的情况下，趟着水，赶到了Beats公司面试。
date: 2019.07.01 10:00:00
location: 上海
---

拎着大雨，裤子都湿了的情况下，趟着水，赶到了Beats公司面试。

面试题目如下：
<hr/>

Q1. h5语义化标签有哪些？语义化的作用。


A1. 常用标签：header nav article section aside footer

 不常用的：ruby rp rt time mark wbr hgroup address figure figcaption progress details summary datelist keygen menu  

 作用：

 a. 去掉或样式丢失的时候能让页面呈现清晰的结构  

 b. 屏幕阅读器（如果访客有视障）会完全根据你的标记来“读”你的网页。  

 c. 搜索引擎的爬虫依赖标签确定上下文和权重问题。

 d. 移动设备能够更完美的展现网页（对css支持较弱的设备）

 e. 便于团队开发和维护

 f. 但是语义化标签有兼容问题

<hr/>


Q2. 块级/行内标签有哪些？

A2. 块级： div h1-h6 p hr br blockquota pre ul ol dl figure

行内：img span strong em mark q a 
<hr/>

Q3. 清除浮动的方法

A3. 清除浮动的方法: 
 
 a. clear: left / right / both; 
 
 b. 伪元素:after{ content:''; display:block; clear:both; }
<hr/>

Q4. display:none 和 visibility: hidden的区别.

A4.
 
 display:none - 
 
 a. 显示为否。隐藏后的元素无法点击，无法使用屏幕阅读器等辅助设备访问，占据的空间消失。
 
 b. 不会被继承。父元素有此设置,而子元素display设置为block等仍不会显示。
 
 c. 无法触发器绑定的事件
 
 d. 过渡动画transition对于display是无效的

 
 visibility: hidden - 
 
 a. 可视为隐藏。虽然元素不可见了，但是仍然会影响页面布局。
 
 b. 会被继承。父元素有此设置,而子元素visibility设置为visible会显示。
 
 c. 可以触发器绑定的事件
 
 d. 过渡动画transition对于visibility也是无效的

 
 添加扩展：opacity:0的对比
 
 a. 元素的不透明度为0。虽然元素不可见了，但是仍然会影响页面布局。
 
 b. 会被继承。父元素有此设置,而子元素opacity设置为1并不会显示。
 
 c. 可以触发器绑定的事件
 
 d. 过渡动画transition对于opacity是有效的

visibility: hidden 与 opacity:0 会使页面重绘。而display:none 还会导致回流
<hr/>

Q5. JQuery中添加、删除、修改、查找DOM元素的方法有哪些？有什么区别？
<hr/>

Q6. 去除下面数组中重复的项，并升序排列返回 数组为 let a = [1,2,2,3,5,7,9,'9',9,10]

A6. 若将'9'视为9，则：

<code>

      function sort(a) {
        return a.sort((prev, curr) => prev - curr);
      }
      function ClearDuplicatesAndSort(a) {
        //console.log(sort(a));
        return sort(a).reduce((prevArray, curr) => {          
          if (prevArray.length == 0 || curr != prevArray[prevArray.length - 1]) {
            prevArray.push(curr);
          }
          return prevArray;
        }, []);
      }      
      const finalArray = ClearDuplicatesAndSort(a);
      console.log(finalArray);
</code>

<hr/>
Q7. 请在这两个函数完成后输出'Hello world!'. 
<code>

    let a = setTimeOut(()=>{},500); 
    let b = setTimeOut(()=>{},Math.random * 1000);
</code>

<hr/>
Q8. 请写出四个vue的指令及使用说明

A8.
指令 | 解释  
-|-
v-for | 根据内容循环展示列表之类的循环操作 |
v-if | 根据内容，有条件的渲染列表中的选项等，不显示，则不渲染 |
v-show | 根据内容，有条件的显示列表中的选项等，即使不显示，也被渲染出来了 |
v-bind | 根据内容，绑定标签原有属性，使之可以动态变化 |
v-model | 有名的双向绑定 |

<hr/>
Q9. 输出100以内的素数

A9.
方案1：
<code>

      function prime(n){
        let arr=[];
        let count=0;
        for(let i = 2; i < n+1; i++){
          for(let j=i-1; j>1; j--){
            if(!(i % j)){
              count++;
            }
          }
          if(!count){
            arr.push(i);        
          }
          count=0;          
        }
        return arr;
      }      
      console.log(prime(100)); 
</code>

方案2：
<code>

      var prime = function(len) {
        let i, j;
        let arr = [];
        for (i = 1; i < len; i++) {
          for (j = 2; j < i; j++) {
            if (i % j === 0) {
              break;
            }
          }
          if (i <= j && i != 1) {
            arr.push(i);
          }
        }
        return arr;
      };
      document.write(prime(100));
</code>

<hr/>
Q10. 正交相机和景深相机的区别

A10. Three.js的内容。没用过，不知道。查找的答案如下：
<div class="zentangle">
  <img title="正交相机与透视相机的区别" src="{{ site.url }}/{{ site.baseurl }}/imgs/posts/2019-07-01-Interview-with-Beats-I.png"/>
</div>

<hr/>
Q11. web页面性能优化的方案

A11. 优化方案，根据浏览器的渲染原理，应该尽量减少页面的回流和重绘，这就要求：
  
  a. 将多次频繁的对DOM元素的操作整合为一个，进行一次更改。
  
  b. 使用CDN（内容分发网络）
  
  c. 减少HTTP请求
  
  d. 将样式表放在头部
  
  e. 将脚本放在底部（body标签结束前）
  
  f. 使用外部的JavaScript和CSS
  
  g. 对于AJax请求，尽量使用GET方法（可以缓存）

<hr/>
Q12. 如果可以，你想要去掉微信的哪个功能，为什么？你想要添加哪个功能，为什么？

A12. 没有希望去掉的，希望加上夜间模式。

<hr/>
Q13. JS有哪些数据类型？哪些是基本数据类型？

A13. 数据类型8种：Number String Symbol Null Undefined Boolean Bigint Object ，前七种是基本数据类型

<hr/>
Q14. transform的常用属性有哪些？

A14. transform的常用属性: 

matrix(a1,a2,a3,a4,a5,a6) matrix3d(a1,a2,a3,a4,a5,a6,a7,a8,a9,a10,a11,a12,a13,a14,a15,a16)
perspective(a1) 

rotate(a1,a2) rotate3d(a1,a2,a3) rotateX(a1) rotateY(a1) rotateZ(a1) 

scale(a1,a2) scale3d(a1,a2,a3) scaleX(a1) scaleY(a1) scaleZ(a1) 

skew(a1,a2) skewX(a1) skewY(a1) 

translate(a1,a2) translate3d(a1,a2,a3) translateX(a1) translateY(a1) translateZ(a1)



对Q5,Q10,Q11的参考网站：
1. [jQuery里面的DOM操作（查找，创建，添加，删除节点）](https://www.cnblogs.com/remain/p/9494297.html)
2. [Three.js基础探寻二——正交投影照相机](https://www.cnblogs.com/xulei1992/p/5707733.html)
3. [Web前端性能优化——如何提高页面加载速度](https://www.cnblogs.com/yzhihao/p/9385467.html)