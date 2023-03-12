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
<div class="tag-list">
{% for cat in site.categories %}
  <div class="tag-group">
    {% capture cat_name %}{{ cat | first }}{% endcapture %}
    <h5 class="tag-group-title" id="{{ cat_name | slugize }}">{{ cat_name }}</h5>
    {% for post in site.categories[cat_name] %}
    <article class="tag-item">
      <a class="tag-item-title" href="{{ site.url }}{{ post.url }}">{{post.title}}</a>
    </article>
    {% endfor %}
  </div>
{% endfor %}
</div>
