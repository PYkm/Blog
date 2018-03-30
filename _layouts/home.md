---
layout: default
---

<!-- 
{% for post in site.posts %}
<div class="synopsis">
	<h2>{{ post.date | date_to_string }} </h2>
	<a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
	<p>{{ post.excerpt | strip_html }}</p>
</div>
{% endfor %}
 -->


<h1>中文博客</h1>

<!-- 遍历分页后的文章 -->

{% for post in paginator.posts %}
<div class="synopsis">
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
{{ post.excerpt }}
</div>
</div>
{% endfor %}

<!-- 分页链接 -->
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