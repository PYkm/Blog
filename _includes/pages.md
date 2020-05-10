<!-- 调页链接 -->
<div class="pagination page">

{% if page.previous %}
<div class="left">
<a href="{{ site.baseurl }}/{{ page.previous.url }}"><< {{ page.previous.title }}</a>
</div>

{% endif %}

{% if page.next %}
<div class="right">
<a href="{{ site.baseurl }}/{{ page.next.url }}">{{ page.next.title }} >></a>
</div>
{% endif %}

</div>