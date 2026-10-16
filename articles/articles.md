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

{%- assign all_categories = "" | split: "," -%}
{%- for post in site.articles -%}
    {%- assign post_categories = post.categories | default: empty -%}
    {%- for category in post_categories -%}
        {%- unless all_categories contains category -%}
            {%- assign all_categories = all_categories | push: category -%}
        {%- endunless -%}
    {%- endfor -%}
{%- endfor -%}

{%- assign all_categories = all_categories | sort -%}
{%- assign current_version = "" -%}

{%- for category in all_categories -%}
    {%- assign category_parts = category | split: '_' -%}
    {%- assign version = category_parts | first -%}
    {%- assign group_name = category | remove_first: version | remove_first: '_' -%}

    {%- if version != current_version -%}
        {%- if current_version != "" -%}
</ul>
        {%- endif -%}
        {%- assign current_version = version -%}
        {%- assign version_total = 0 -%}

        {%- for post in site.articles -%}
            {%- assign post_categories = post.categories | default: empty -%}
            {%- assign post_has_version = false -%}
            {%- for post_category in post_categories -%}
                {%- assign post_version = post_category | split: '_' | first -%}
                {%- if post_version == version -%}
                    {%- assign post_has_version = true -%}
                    {%- break -%}
                {%- endif -%}
            {%- endfor -%}
            {%- if post_has_version -%}
                {%- assign version_total = version_total | plus: 1 -%}
            {%- endif -%}
        {%- endfor -%}

        {%- assign version_words = version | replace: '-', ' ' | split: ' ' %}
<h2>{% for word in version_words %}{{ word | capitalize }}{% unless forloop.last %} {% endunless %}{% endfor %} ({{ version_total }} articles)</h2>
<ul>
    {%- endif -%}

    {%- assign category_total = 0 -%}
    {%- for post in site.articles -%}
        {%- assign post_categories = post.categories | default: empty -%}
        {%- if post_categories contains category -%}
            {%- assign category_total = category_total | plus: 1 -%}
        {%- endif -%}
    {%- endfor -%}

    {%- assign group_words = group_name | replace: '-', ' ' | split: ' ' -%}
    {%- assign category_label = '' -%}
    {%- for word in group_words -%}
        {%- assign capitalized_word = word | capitalize -%}
        {%- assign category_label = category_label | append: capitalized_word -%}
        {%- unless forloop.last -%}
            {%- assign category_label = category_label | append: ' ' -%}
        {%- endunless -%}
    {%- endfor -%}

    {%- assign category_url = category | replace: '_', '/' -%}
<li>
    <a href="{{ '/articles/' | append: category_url | relative_url }}">{%- if group_name == '' -%}{{ version | replace: '-', ' ' | capitalize | escape }}{%- else -%}{{ category_label | escape }}{%- endif -%}</a>
    ({{ category_total }})
</li>
{%- endfor -%}

{%- if current_version != "" -%}
</ul>
{%- endif -%}