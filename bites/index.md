---
title: Bites
layout: default
permalink: /bites/
has_toc: false
---

# Bites

Sometimes it's hard to remember what was for breakfast this morning, not even to recollect important lessons from yesterday. Hence the existence of the following posts, that aim to store subjectively important "bites" of information and hard (l)earned knowledge from various fields of interest for later use.

{% assign years = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in years %}
**Bites from {{ year.name }}**

<ul>
{% for post in year.items %}
    <li>
    <a href='{{ post.url }}'>{{ post.title }}</a>
    </li>
{% endfor %}
</ul>
{% endfor %} 