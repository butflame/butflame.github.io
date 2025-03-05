---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<h2 class="page-heading"> 最近博客 </h2>
<h3 class="post-list-heading">  技术文档 </h3>
  <ul class="post-list">
    {% assign posts = site.categories.tech | sort: "date" | reverse | slice: 0, 3 %}
    {% for post in posts %}
        <li>
        	{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
        	<span class="post-meta">{{ post.date | date: date_format }} {% if post.tags.size > 0 %} | {{ post.tags | join: ", " }} {% endif %} </span>
        	<a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        	{%- if site.show_excerpts -%}{{ post.excerpt }}{%- endif -%}
        </li>
    {% endfor %}
  </ul>

<br/>


<h3 class="post-list-heading">  生涯随记  </h3>
  <ul class="post-list">
    {% assign posts = site.categories.career | sort: "date" | reverse | slice: 0, 3 %}
    {% for post in posts %}
        <li>
            {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
            <span class="post-meta">{{ post.date | date: date_format }} | {% if post.tags.size > 0 %} | {{ post.tags | join: ", " }} {% endif %}</span>
            <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
            {%- if site.show_excerpts -%}{{ post.excerpt }}{%- endif -%}
        </li>
    {% endfor %}
  </ul>
<br/>



<h3 class="post-list-heading">  鸡零狗碎  </h3>
  <ul class="post-list">
    {% assign posts = site.categories.life | sort: "date" | reverse | slice: 0, 3 %}
    {% for post in posts %}
        <li>
            {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
            <span class="post-meta">{{ post.date | date: date_format }} {% if post.tags.size > 0 %} | {{ post.tags | join: ", " }} {% endif %}</span>
            <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
            {%- if site.show_excerpts -%}{{ post.excerpt }}{%- endif -%}
        </li>
    {% endfor %}
  </ul>

<br/>

