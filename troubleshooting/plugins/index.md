---
layout: default
title: Feature troubleshooting
title_nav: Feature troubleshooting
keywords: troubleshooting debugging console error banner
type: folder
---
{% assign navigaton = site.data.nav %}
{% for entry in navigaton %}
  {% if entry.url == "troubleshooting" %}
    {% for subentry in entry.pages %}
      {% if subentry.url == "plugins" %}
        {% assign links = subentry.pages %}
      {% endif %}
    {% endfor %}
  {% endif %}
{% endfor %}

{% include index.html links=links %}