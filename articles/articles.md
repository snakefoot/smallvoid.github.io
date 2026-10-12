---
title: Articles
date: '2006-11-14T23:28:05+01:00'
permalink: /articles/
author: Snakefoot
excerpt: ''
type: page
id: 3
description:
    - 'Sitemap of the posted articles and their categories.'
---

<h1>{{ page.title | escape }}</h1>

{% assign versions = "windows-95,windows-98,windows-me,windows-nt4,windows-2000,windows-2003,windows-xp,windows-vista,windows-7-win7,windows-8-win8,windows-10-win10,windows-11-win11" | split: "," %}

{% for version in versions %}
  {% assign version_total = 0 %}
  {% assign categories = "" | split: "," %}
  {% assign prefix = version | append: "-" %}

  {% for post in site.posts %}
    {% assign has_version = false %}

    {% for category in post.categories %}
      {% assign category_prefix = category | slice: 0, prefix.size %}

      {% if category_prefix == prefix %}
        {% assign has_version = true %}

        {% unless categories contains category %}
          {% assign categories = categories | push: category %}
        {% endunless %}
      {% endif %}
    {% endfor %}

    {% if has_version %}
      {% assign version_total = version_total | plus: 1 %}
    {% endif %}
  {% endfor %}

  {% if version_total > 0 %}
    <h2>{{ version | replace: "-", " " | capitalize }} ({{ version_total }} articles)</h2>

    {% assign categories = categories | sort %}

    <ul>
      {% for category in categories %}
        {% assign category_total = 0 %}

        {% for post in site.posts %}
          {% if post.categories contains category %}
            {% assign category_total = category_total | plus: 1 %}
          {% endif %}
        {% endfor %}

        {% assign group_name = category | remove_first: prefix %}

        <li>
          <a href="{{ '/windows/' | append: version | append: '/' | append: group_name | append: '/' | relative_url }}">
            {{ group_name | replace: "-", " " | capitalize }}
          </a>
          ({{ category_total }})
        </li>
      {% endfor %}
    </ul>
  {% endif %}
{% endfor %}