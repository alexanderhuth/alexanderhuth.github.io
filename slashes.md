---
layout: page
title: Slashes
seo_title: Slash Pages
permalink: /slashes/
---

# Slash Pages

My [slash page](https://slashpages.net), linking to all the pages that describe me somehow.

<ul class="link-list">
  {% for page in site.pages %}
    {% unless page.url == "/" or page.url == "/slashes/" or page.url == "/404.html" or page.url == "/feed.xml" or page.url == "/sitemap.xml" or page.url contains "/assets/" or page.path contains "_posts" %}
      <li><a href="{{ page.url }}">/{{ page.title | downcase }}</a></li>
    {% endunless %}
  {% endfor %}
</ul>
