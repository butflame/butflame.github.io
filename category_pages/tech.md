---
layout: page
permalink: /category/tech/
---

<h3 class="post-list-heading">  技术文档  </h3>
  <ul class="post-list">
    {% assign posts = site.categories.tech | sort: "date" | reverse %}
    {% for post in posts %}
      {% unless post.hidden %}
        <li>
          {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
          <span class="post-meta">{{ post.date | date: date_format }} {% if post.tags.size > 0 %} | {{ post.tags | join: ", " }} {% endif %}</span>
          <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
          {%- if site.show_excerpts -%}{{ post.excerpt }}{%- endif -%}
        </li>
      {% endunless %}
    {% endfor %}
  </ul>
