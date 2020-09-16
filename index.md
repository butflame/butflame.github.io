---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---


{% for cate in site.categories %}
<h3 class="post-list-heading"> {{cate[0]}} </h3>
  <ul class="post-list">
    {% for post in cate[1] %}
    <li>
    	{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    	<span class="post-meta">{{ post.date | date: date_format }} | {{ post.tags }}</span>
    	<a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
    	{%- if site.show_excerpts -%}{{ post.excerpt }}{%- endif -%}
    </li>
    {% endfor %}
  </ul>

<br/>
{% endfor %}
