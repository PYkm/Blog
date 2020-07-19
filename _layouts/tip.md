{% include header_post.html %}
{% include nav_post.html %}

<div class="content_tip">
	<div class="nav_post">
		<ul>
			<li><a href="{{ site.baseurl }}/">部落格首页</a></li>
		</ul>
	</div>
	<h2 id="{{ page.title }}">{{ page.title }}</h2>
　　{{ content }}
</div>

{% include contact.md %}
{% include footer.html %}