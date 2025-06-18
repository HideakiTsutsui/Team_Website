---
title: "Publications"
layout: single
permalink: /publications/
---

## Selected Publications

{% assign pubs = site.data.publications | sort: "year" | reverse %}

{% for pub in pubs %}
- **{{ pub.authors }}** ({{ pub.year }}).  
  *{{ pub.title }}*. _{{ pub.venue }}_.  
  {% if pub.doi %}
    [DOI](https://doi.org/{{ pub.doi }})
  {% elsif pub.url %}
    [Link]({{ pub.url }})
  {% endif %}
{% endfor %}
