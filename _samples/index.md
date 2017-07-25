---
layout: page
title: Samples
---

<div>
  <ul>
    {% for sample in site.samples %}
      {% if page.title != sample.title %}
      <li><a href="{{ sample.url }}">{{ sample.title }}</a></li>
      {% endif %}
    {% endfor %}
  </ul>
</div>
