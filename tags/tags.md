---
title: Tags
permalink: /tags/
layout: page
---

<div class="tag-cloud">
{% assign sorted_tags = site.tags | sort %}
{% for tag in sorted_tags %}
  {% assign tag_name = tag | first %}
  {% assign tag_posts = tag | last %}
  {% assign tag_count = tag_posts | size %}
  {% if tag_count > 10 %}
    {% assign tag_size = 'tag-large' %}
  {% elsif tag_count > 5 %}
    {% assign tag_size = 'tag-medium' %}
  {% else %}
    {% assign tag_size = 'tag-small' %}
  {% endif %}
  <a href="#{{ tag_name | slugify }}" class="tag-cloud-item {{ tag_size }}">
    {{ tag_name }} <span class="tag-count">({{ tag_count }})</span>
  </a>
{% endfor %}
</div>

<div class="tag-list">
{% for tag in sorted_tags %}
  {% assign tag_name = tag | first %}
  {% assign tag_posts = tag | last %}
  <div class="tag-group">
    <h3 class="tag-group-title" id="{{ tag_name | slugify }}">{{ tag_name }}</h3>
    <ul class="tag-posts">
    {% for post in tag_posts %}
      <li>
        <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
        <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
      </li>
    {% endfor %}
    </ul>
  </div>
{% endfor %}
</div>
