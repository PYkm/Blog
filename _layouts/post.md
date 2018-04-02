{% include header_post.html %}
{% include nav_post.html %}

<div class="content_post">
	<h2 id="{{ page.title }}">{{ page.title }}</h2>

	<div class="tags">
		{% for tag in page.tags %}
			<a class="tag" href="{{ site.baseurl }}/all?tag={{ tag }}">{{ tag }}</a>
		{% endfor %}
	</div>

	<div class="date">
		{{ page.date | date_to_string }}
	</div>

　　{{ content }}

</div>

{% include tip.md %}
{% include recent.md %}
{% include contact.md %}
{% include footer.html %}