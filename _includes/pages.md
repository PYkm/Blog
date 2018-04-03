<!-- 调页链接 -->
<div class="pagination page">

{% if page.previous %}
<div class="left">
<a href="{{ site.baseurl }}/{{ page.previous.url }}">上一篇：{{ page.previous.title }}</a>
</div>

{% endif %}

{% if page.next %}
<div class="right">
<a href="{{ site.baseurl }}/{{ page.next.url }}">下一篇：{{ page.next.title }}</a>
</div>
{% endif %}

</div>