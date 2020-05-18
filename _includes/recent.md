<div class="recents">

{% assign postHasSimilar = false %}

{% for post in site.posts %}
{% if post.title != page.title %}
	<!-- <script>console.log("postHasSimilar post.title: {{ post.title }}");</script>
	<script>console.log("postHasSimilar page.title: {{ page.title }}");</script> -->
	{% for tag in post.tags %}
	<!-- <script>console.log("postHasSimilar tag: {{ tag }}");</script> -->
		{% for pageTag in page.tags %}
	<!-- <script>console.log("postHasSimilar pageTag: {{ pageTag }}");</script> -->
			{% if pageTag == tag %}
				{% assign postHasSimilar = true %}
			{% endif %}
    	{% break %}<!-- 添加此行May 18，为了与下方逻辑保持一致，只有其他的博文与此博文的第一个标签一致时，才认为是近似博文 -->
		{% endfor %}
	<!-- <script>console.log("postHasSimilar: {{ postHasSimilar }}");</script> -->
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