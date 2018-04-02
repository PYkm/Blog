<div class="recent">
<h1>最近博文</h1>
<ul>
{% for post in site.posts limit:5 %}
	<li class="recentBlogs">
		<a class="tit" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
	</li>
{% endfor %}
</ul>
</div>