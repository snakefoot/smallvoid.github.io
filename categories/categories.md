---
title: Categories
permalink: /categories/
layout: page
---

<div class="category-list">
{% assign sorted_categories = site.categories | sort %}
{% for category in sorted_categories %}
  {% assign category_name = category | first %}
  {% assign category_posts = category | last %}
  <div class="category-group">
    <h3 class="category-group-title" id="{{ category_name | slugify }}">
      {{ category_name }} <span class="category-count">({{ category_posts | size }})</span>
    </h3>
    <ul class="category-posts">
    {% for post in category_posts %}
      <li>
        <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
        <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
      </li>
    {% endfor %}
    </ul>
  </div>
{% endfor %}
</div>
