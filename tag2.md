---
layout: default
title: "Post con tag tag2"
permalink: /tag/tag2/
tag: tag2
---

<h1>Post con tag: #tag2</h1>

<ul>
{% assign tagged_posts = site.posts | where_exp: "post", "post.tags contains page.tag" %}
  {% for post in tagged_posts %}
    <li>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <p><strong>Descrizione:</strong> {{ post.excerpt }}</p>

      <p><strong>Altri tag:</strong> 
        {% for t in post.tags %}
          {% if t != page.tag %}  <!-- Escludiamo il tag corrente -->
            <a href="/tag/{{ t | slugify }}/">#{{ t }}</a>{% unless forloop.last %}, {% endunless %}
          {% endif %}
        {% endfor %}
      </p>
    </li>
  {% endfor %}
</ul>
