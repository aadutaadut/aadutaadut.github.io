---
layout: default
title: "Post con tag tag2"
permalink: /tag/tag2/
tag: tag2
---

<h1>Post con tag: #tag2</h1>

<ul style="list-style: none; padding: 0;">
{% assign tagged_posts = site.posts | where_exp: "post", "post.tags contains page.tag" %}
  {% for post in tagged_posts %}
    <li style="margin-bottom: 2rem;">
      <h2 style="margin-bottom: 0.2rem;">{{ post.title }}</h2>

      <p style="margin-top: 0; margin-bottom: 0.2rem;">
        {% for t in post.tags %}
          {% if t != page.tag %}
            <a href="/tag/{{ t | slugify }}/" style="color: black; text-decoration: none;">#{{ t }}</a>{% unless forloop.last %}, {% endunless %}
          {% endif %}
        {% endfor %}
      </p>

      <p style="margin-top: 0.5rem; color: black;">
        {{ post.excerpt }} <a href="{{ post.url }}" style="color: black; text-decoration: none;">[read more]</a>
      </p>
    </li>
  {% endfor %}
</ul>
