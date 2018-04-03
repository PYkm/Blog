{% include header_post.html %}
{% include nav_post.html %}

<div class="content_post">
	<div class="nav_post">
		<ul>
			<li><a href="{{ site.baseurl }}/">首页</a></li>
		</ul>
	</div>


	<h2 id="{{ page.title }}">{{ page.title }}</h2>

	<div class="tags">
		{% for tag in page.tags %}
			<a class="tag" href="{{ site.baseurl }}/all?tag={{ tag }}">{{ tag }}</a>
		{% endfor %}
	</div>

　　{{ content }}

	<div class="date">
		{{ page.date | date: "%Y年%m月%d日" }}于{{ page.location }}
	</div>

</div>

{% include tip.md %}
{% include pages.md %}
{% include recent.md %}
{% include contact.md %}
{% include footer.html %}