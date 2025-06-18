---
title: "Publications"
layout: single
permalink: /publications/
---

## Publications

{% assign pubs = site.data.publications | sort: "year" | reverse %}
{% assign count = pubs | size %}

<ol reversed>
{% for pub in pubs %}
  <li>
    {{ pub.authors }} ({{ pub.year }}). {{ pub.title }}. <strong>_{{ pub.venue }}_</strong>. {{ pub.volume }} ({{ pub.issue }}) {{ pub.page }}.
    {% if pub.doi %}
      <a href="https://doi.org/{{ pub.doi }}" target="_blank">DOI</a>
    {% elsif pub.url %}
      <a href="{{ pub.url }}" target="_blank">Link</a>
    {% endif %}
  </li>
{% endfor %}
</ol>
