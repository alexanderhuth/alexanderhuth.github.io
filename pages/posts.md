---
layout: page
title: Posts
permalink: /posts/
---

# Posts

<ul>
  {% for post in site.posts %}
    <li>
      {% if post.date %}{{ post.date | date: "%b %-d, %Y" }} · {% endif %}<a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
