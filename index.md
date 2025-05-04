---
layout: default
title: Home
---

# Benvenuto nel mio blog

{% for post in site.posts %}
## [{{ post.title }}]({{ post.url }})

<p>{{ post.excerpt }}</p>

**Tags**:
{% for tag in post.tags %}
  <a href="/tag/{{ tag | slugify }}/" style="margin-right:10px;">#{{ tag }}</a>
{% endfor %}

<hr>
{% endfor %}
