---
layout: default
---

<h1>全部博文</h1>
{% for post in paginator.posts %}
<div class="synopsis">
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
<div class="pagination">

{% if paginator.previous_page %}
<a href="{{ site.baseurl }}/" class="">首 页</a>
{% if paginator.previous_page != 1 %}
<a href="{{ site.baseurl }}/page{{ paginator.previous_page }}" class="">上一页</a>
{% else %}
<a href="{{ site.baseurl }}/" class="">上一页</a>
{% endif %}
{% else %}
<span class="">首 页</span>
<span class="">上一页</span>
{% endif %}

<span class="page_number ">{{ paginator.page }} / {{ paginator.total_pages }}</span>

{% if paginator.next_page %}
<a href="{{ site.baseurl }}/page{{ paginator.next_page }}" class="">下一页</a>
<a href="{{ site.baseurl }}/page{{ paginator.total_pages }}" class="">末 页</a>
{% else %}
<span class="">下一页</span>
<span class="">末 页</span>
{% endif %}

</div>