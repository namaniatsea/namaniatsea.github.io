---
layout: page
title: "Blog Archive by Category"
nav_title: "Archive"
permalink: /archive/
---

<div class="category-links">
  <strong>Jump to:</strong>
  {% assign sorted_categories = site.categories | sort %}
  {% for category in sorted_categories %}
    {% if category[0] != 'blog' and category[0] != 'nicky_page' %}
      <a href="#{{ category[0] | slugify }}">{{ category[0] | replace: "_", " " }} </a>
    {% endif %}
  {% endfor %}
</div>

<hr>

{%- for category in sorted_categories reversed -%}
{%- if category[0] != 'blog' and category[0] != 'nicky_page' -%}
<h2 id="{{ category[0] | slugify }}">{{ category[0] | replace: "_", " " }}</h2>
<ul class="post-list">
    {% for post in category[1] %}
    <li style="margin-bottom: 10px; list-style: none;">
        <span class="post-meta" style="color: #828282;">{{ post.date | date: "%b %-d, %Y" }}</span>
        <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
        </a>
        </h3>
    </li>
    {% endfor %}
</ul>
{%- endif -%}
{%- endfor -%}