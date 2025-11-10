---
title: Jira Structure
layout: default
parent: Tags
permalink: /tags/jira-structure/
---

# Jira Structure

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

- [Formulas docs](https://help.tempo.io/structure/latest/formulas)
- [Formulas Standard functions](https://help.tempo.io/structure/latest/standard-functions)
- [Formulas Aggregate functions](https://help.tempo.io/structure/latest/aggregate-functions)
- [Jira fields and Structure attributes](https://help.tempo.io/structure/latest/predefined-variables)
- [Item properties](https://help.tempo.io/structure/latest/item-properties)