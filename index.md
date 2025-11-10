---
title: Home
layout: default
permalink: /
nav_order: 1
has_toc: false
---
 
# Home

Main purpose of this website is, for the time being, to store specific bits of knowledge as [bytes](/bytes) categorized under various [tags](/tags).

**Recent bytes:**

<ul>
{% for post in site.posts limit 10 %}
    <li>
    <a href='{{ post.url }}'>{{ post.title }}</a>
    </li>
{% endfor %}
</ul>