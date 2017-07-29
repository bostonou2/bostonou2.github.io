---
layout: page
---

<h4>Last Updated: July 25, 2017</h4>

{% assign sorted_date = site.samples | sort: "date" %}
{% assign sorted = sorted_date | sort: "title" %}
<div>
  <h2>Available Samples</h2>
  <ul>
    {% for sample in sorted %}
      {% if page.title != sample.title and sample.num_samples > 0 %}
      <li style="background:url('/img/whiskey-full.jpg') no-repeat left top;list-style:none;margin:0;padding:5px 0 10px 25px;"
><a href="{{ sample.url }}">{{ sample.title }} - {{ sample.num_samples }} available <span style="font-size:0.65em">({{ sample.date | date_to_string }})</span></a></li>
      {% endif %}
    {% endfor %}
  </ul>
</div>

<div>
  <h2>Past Samples</h2>
  <ul>
    {% for sample in sorted %}
      {% if page.title != sample.title and sample.num_samples < 1 %}
      <li style="text-decoration:line-through;background:url('/img/whiskey-empty.jpg') no-repeat left top;list-style:none;margin:0;padding:5px 0 10px 25px;"><a href="{{ sample.url }}">{{ sample.title }} <span style="font-size:0.7em">({{ sample.date | date_to_string }})</span></a></li>
      {% endif %}
    {% endfor %}
  </ul>
</div>
