---
layout: page
title: Samples
---

{% assign sorted_date = site.samples | sort: "date" %}
{% assign sorted = sorted_date | sort: "title" %}
<div>
  <h2>Available Samples</h2>
  <ul>
    {% for sample in sorted %}
      {% if page.title != sample.title and sample.num_samples > 1 %}
      <li><a href="{{ sample.url }}">{{ sample.title }} <span style="font-size:0.7em">({{ sample.date | date_to_string }})</span></a></li>
      {% endif %}
    {% endfor %}
  </ul>
</div>

<div>
  <h2>Past Samples</h2>
  <ul>
    {% for sample in sorted %}
      {% if page.title != sample.title and sample.num_samples < 1 %}
      <li style="text-decoration:line-through;"><a href="{{ sample.url }}">{{ sample.title }} <span style="font-size:0.7em">({{ sample.date | date_to_string }})</span></a></li>
      {% endif %}
    {% endfor %}
  </ul>
</div>
