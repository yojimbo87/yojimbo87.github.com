---
title: Tags
layout: default
permalink: /tags/
has_toc: false
---

# Tags

List of tags which has "bites" in them:

<ul>
{% for tag in site.tags %}
    {% assign tag_name = tag | first %}
    <li><a href="/tags/{{ tag_name | downcase }}">{{ tag_name }}</a></li>
{% endfor %}
</ul>