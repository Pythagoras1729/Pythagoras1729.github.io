---
layout: default
title: Stream of Consciousness
---

# Stream of Consciousness

{% for entry in site.stream reversed %}
  <article class="stream-entry">
    <time datetime="{{ entry.date | date_to_xmlschema }}">
        {{ entry.date | date: "%B %d, %Y %H:%M" }}
    </time>
    {{ entry.content }}
  </article>
{% endfor %}