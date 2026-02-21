---
title: Articles
date: '2006-11-14T23:28:05+01:00'
status: publish
permalink: /articles/
author: Snakefoot
excerpt: ''
type: page
id: 3
description:
    - 'Sitemap of the posted articles and their categories.'
tags:
    - ''
---

Browse articles by [Categories](/categories/) or [Tags](/tags/)

## Article Categories

<div class="articles-category-grid">
{% assign sorted_categories = site.categories | sort %}
{% for category in sorted_categories %}
  {% assign category_name = category | first %}
  {% assign category_posts = category | last %}
  {% assign category_slug = category_name | slugify %}
  <div class="article-category-card">
    <h3>
      <a href="{{ site.baseurl }}/category/{{ category_slug }}/">{{ category_name }}</a>
    </h3>
    <p class="category-count">{{ category_posts | size }} articles</p>
    <p class="category-preview">
      {% for post in category_posts limit:3 %}
        {{ post.title }}{% unless forloop.last %}, {% endunless %}
      {% endfor %}
      {% if category_posts.size > 3 %}...{% endif %}
    </p>
  </div>
{% endfor %}
</div>
