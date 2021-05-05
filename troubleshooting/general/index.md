---
layout: default
title: General troubleshooting tips for TinyMCE 5
title_nav: General troubleshooting
keywords: troubleshooting debugging console error banner
type: folder
---
{% assign navigaton = site.data.nav %}
{% for entry in navigaton %}
  {% if entry.url == "troubleshooting" %}
    {% for subentry in entry.pages %}
      {% if subentry.url == "general" %}
        {% assign links = subentry.pages %}
      {% endif %}
    {% endfor %}
  {% endif %}
{% endfor %}

{% include index.html links=links %}