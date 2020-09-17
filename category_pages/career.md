---
layout: page
permalink: /category/career/
---

<h3 class="post-list-heading">  生涯随记  </h3>
  <ul class="post-list">
    {% assign posts = site.categories.career | sort: "date" %}
    {% for post in posts %}
    <li>
    	{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    	<span class="post-meta">{{ post.date | date: date_format }} | {{ post.tags }}</span>
    	<a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
    	{%- if site.show_excerpts -%}{{ post.excerpt }}{%- endif -%}
    </li>
    {% endfor %}
  </ul>
