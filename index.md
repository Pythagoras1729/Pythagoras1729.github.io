---
layout: default
title: Home
---

# Latest Posts

{% for post in site.posts limit:5 %}
  <article class="post-preview">
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <time datetime="{{ post.date | date_to_xmlschema }}">
        {{ post.date | date: "%B %d, %Y" }}
    </time>
    {{ post.excerpt }}
  </article>
{% endfor %}