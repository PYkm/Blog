{% include header_post.html %}
{% include nav_post.html %}

<div class="content_tip">
	<div class="nav_post">
		<ul>
			<li><a href="{{ site.baseurl }}/">首页</a></li>
		</ul>
	</div>
　　{{ content }}
</div>

{% include contact.md %}
{% include footer.html %}