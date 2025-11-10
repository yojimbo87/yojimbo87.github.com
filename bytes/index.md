---
title: Bytes
layout: default
permalink: /bytes/
has_toc: false
---

# Bytes

Sometimes it's hard to remember what was for breakfast this morning, not even to recollect important lessons from yesterday. Hence the existence of the following sub-pages that aim to store subjectively important bytes of information and hard (l)earned knowledge from various fields of interest for later use.

{% assign years = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in years %}
**Bytes from {{ year.name }}**

<ul>
{% for post in year.items %}
    <li>
    <a href='{{ post.url }}'>{{ post.title }}</a>
    </li>
{% endfor %}
</ul>
{% endfor %} 