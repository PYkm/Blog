---
layout: all
title: 所有相关博文
---

<script type="text/javascript">
	function getQueryString(name) { 
		var r, param, searches = decodeURI(window.location.search).substr(1);
		param = searches.split('&');
		/*param[]*/
		for(x=0; x<param.length; x++){
			if (param[x].indexOf(name + '=') > -1)
			{
				r = param[x].substr(4);
			}
		}
        return r;
    } 

    var tagActive = getQueryString('tag');
    console.log(decodeURI(tagActive));
    console.log(decodeURI(window.location.search));
</script>


<!--
{% for tag in site.tags %}
{% if tag[0] == '书单' %}
{% for post in tag[1] %}

<div class="synopsis tag-{{tag[0]}}">
<h2><a class="tit" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>
<p class="author">
<span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>
</p>
<div class="tags">
	{% for tag in post.tags %}
	<a class="tag" href="">{{ tag }}</a>
	{% endfor %}
</div>
<div class="excerpt">
<a class="exc" href="{{ site.baseurl }}{{ post.url }}">{{ post.excerpt }}</a>
</div>
</div>

{% endfor %}
{% endif %}
{% endfor %}
-->


<!-- 所有博文 -->

<div class="nav_post">
	<ul>
		<li><a href="{{ site.baseurl }}/">首页</a></li>
	</ul>
</div>
<h1 id="tagName"></h1>
{% for post in site.posts %}
<div class="synopsis {% for tag in post.tags %} tag-{{ tag }}{% endfor %}">
<h2><a class="tit" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>
<p class="author">
<span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>
</p>
<div class="tags">
	{% for tag in post.tags %}
	<a class="tag" href="{{ site.baseurl }}/all?tag={{ tag }}">{{ tag }}</a>
	{% endfor %}
</div>
<div class="excerpt">
<a class="exc" href="{{ site.baseurl }}{{ post.url }}">{{ post.excerpt }}</a>
</div>
</div>
{% endfor %}

<!-- 分页链接 -->
<!--
<div class="pagination">
{% if paginator.previous_page %}
{% if paginator.previous_page != 1 %}
<a href="{{ site.baseurl }}/page{{ paginator.previous_page }}" class="">上一页</a>
{% else %}
<a href="{{ site.baseurl }}/" class="">上一页</a>

{% endif %}
{% else %}
<span class="">上一页</span>
{% endif %}
<span class="page_number ">{{ paginator.page }} / {{ paginator.total_pages }}</span>
{% if paginator.next_page %}
<a href="{{ site.baseurl }}/page{{ paginator.next_page }}" class="">下一页</a>
{% else %}
<span class="">下一页</span>
{% endif %}
</div>
-->

<script>
	
    var i;

    
    var y = document.getElementsByClassName('synopsis');
    for (i = 0; i < y.length; i++) {
    	y[i].style.display = "none";
	}


	document.getElementById('tagName').innerText="所有与" + decodeURI(tagActive) + "有关的博文";
    var x = document.getElementsByClassName('tag-' + decodeURI(tagActive));

    for (i = 0; i < x.length; i++) {
    	x[i].style.display = "block";
	}

</script>