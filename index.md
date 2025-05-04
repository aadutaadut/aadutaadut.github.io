---
layout: default
title: Home
---

# Benvenuto nel mio blog

{% for post in site.posts %}
## [{{ post.title }}]({{ post.url }})

<p>{{ post.excerpt }}</p>

{% if post.tags %}
<small>
  {% for tag in post.tags %}
    <a href="/tag/{{ tag | slugify }}/">#{{ tag }}</a>{% unless forloop.last %}, {% endunless %}
  {% endfor %}
</small>
{% endif %}

<hr>
{% endfor %}