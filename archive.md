---
layout: default
title: Archive
---

# Archive

{% for post in site.posts %}
  {% assign currentdate = post.date | date: "%Y" %}
  {% if currentdate != date %}
    {% unless forloop.first %}</ul>{% endunless %}
    <h2 id="y{{post.date | date: "%Y"}}">{{ currentdate }}</h2>
    <ul class="posts-by-year">
    {% assign date = currentdate %}
  {% endif %}
    <li>
      <time datetime="{{ post.date | date_to_xmlschema }}">
        {{ post.date | date: "%B %d" }}
      </time>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% if forloop.last %}</ul>{% endif %}
{% endfor %}
