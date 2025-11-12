---
title: Home
layout: default
permalink: /
nav_order: 1
has_toc: false
---
 
# Home

Main purpose of this website is (for the time being) to store specific bits of knowledge in the form of ["bites"](/bites) categorized under various [tags](/tags).

**Recent bites:**

<ul>
{% for post in site.posts limit 10 %}
    <li>
    <a href='{{ post.url }}'>{{ post.title }}</a>
    </li>
{% endfor %}
</ul>