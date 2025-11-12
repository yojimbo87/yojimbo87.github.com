---
title: Polars
layout: default
parent: Tags
permalink: /tags/polars
---

# Polars

{% assign tag_posts = site.posts | where_exp: 'post', "post.tags contains page.title" %}
{% if tag_posts.size > 0 %}
Bites:

<ul>
{% for post in tag_posts %}
    <li><a href="{{ post.permalink }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
{% endif %}

External resources:

- [User guide](https://docs.pola.rs/user-guide/getting-started/)