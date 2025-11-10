---
title: Jekyll
layout: default
parent: Tags
permalink: /tags/jekyll
---

# Jekyll

{% assign tag_posts = site.posts | where_exp: 'post', "post.tags contains page.title" %}
{% if tag_posts.size > 0 %}
Bytes:

<ul>
{% for post in tag_posts %}
    <li><a href="{{ post.permalink }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
{% endif %}

External resources:

- [Installation guide on Windows](https://www.geeksforgeeks.org/installation-guide/how-to-install-jekyll-on-windows/)
- [Liquid filters docs](https://jekyllrb.com/docs/liquid/filters/)

Running local server:

```bash
bundle exec jekyll serve
```