---
layout: default
title: Home
---

# Benvenuto nel mio blog

{% for post in site.posts %}
  - [{{ post.title }}]({{ post.url }})
{% endfor %}
