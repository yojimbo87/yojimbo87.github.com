---
title: Vega-Altair
layout: default
parent: Tags
permalink: /tags/vega-altair
---

# Vega-Altair

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

- [Introduction to Altair](https://idl.uw.edu/visualization-curriculum/altair_introduction.html)
- [User guide](https://altair-viz.github.io/user_guide/data.html)
- [Example gallery](https://altair-viz.github.io/gallery/index.html)
- [Vega datasets definition](https://github.com/vega/vega-datasets/blob/main/datapackage.md)