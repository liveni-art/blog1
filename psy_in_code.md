---
layout: default
title: Home
---

<div class="posts">
  {% for post in site.categories.psy_in_code %}
  <article class="post">
    <h1 class="post-title">
      <a href="{{ post.url | relative_url }}">
        {{ post.title }}
      </a>
    </h1>

    <time datetime="{{ post.date | date_to_xmlschema }}" class="post-date">{{ post.date | date_to_string }}</time>

    <!-- {{ post.content }} -->
    <p class="post_content">{% if post.content %}{{ post.content  | strip_html | strip_newlines | truncate: 450 }}{% else %}{{ post.content | strip_html | strip_newlines | truncate: 450 }}{% endif %}</p>   

  </article>
  {% endfor %}
</div>

<div class="pagination">
  {% if paginator.next_page %}
    <a class="pagination-item older" href="{{ paginator.next_page_path | relative_url }}">Older</a>
  {% else %}
    <span class="pagination-item older">Older</span>
  {% endif %}
  {% if paginator.previous_page %}
    <a class="pagination-item newer" href="{{ paginator.previous_page_path | prepend: relative_url }}">Newer</a>
  {% else %}
    <span class="pagination-item newer">Newer</span>
  {% endif %}
</div>
