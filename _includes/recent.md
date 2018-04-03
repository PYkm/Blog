<div class="recents">

{% assign postHasSimilar = false %}

{% for post in site.posts %}
{% if post.title != page.title %}
	{% for tag in post.tags %}
		{% for pageTag in page.tags %}
			{% if pageTag == tag %}
				{% assign postHasSimilar = true %}
			{% endif %}
		{% endfor %}
	{% endfor %}
{% endif %}
{% endfor %}


{% if postHasSimilar %}
<div class="recent similar">
	<h2>相似博文</h2>
	<ul>
{% assign hasSimilar = '' %}
{% for post in site.posts %}
{% if hasSimilar.size < 5 and post.title != page.title %}
	{% for tag in post.tags %}

	{% for pageTag in page.tags %}

	{% if pageTag == tag %}	
	<li class="recentBlogs">
		<a class="tit" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
	</li>

    {% capture hasSimilar %}{{ hasSimilar }}*{% endcapture %}

	{% endif %}
    {% break %}

	{% endfor %}
	{% endfor %}
{% endif %}

{% endfor %}
	</ul>
</div>
{% endif %}

<div class="recent">
<h2>最近博文</h2>
<ul>
{% for post in site.posts limit:5 %}
	<li class="recentBlogs">
		<a class="tit" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
	</li>
{% endfor %}
</ul>
</div>
</div>