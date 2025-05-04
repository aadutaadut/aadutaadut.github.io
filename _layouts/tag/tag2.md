---
layout: default
title: Post con tag "tag2"
permalink: /tag/tag2/
tag: tag2
---

<h1>Post con tag: #tag2</h1>

{% assign tagged_posts = site.posts | where_exp: "post", "post.tags contains page.tag" %}
<ul>
  {% for post in tagged_posts %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
