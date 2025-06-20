---
title: "Publications"
layout: single
permalink: /publications/
---

For the latest publications list, please check [Google Scholar](https://scholar.google.com/citations?user=7BdjDuwAAAAJ).

## Journal Publications

{% assign pubs = site.data.publications | sort: "year" | reverse %}
{% assign count = pubs | size %}

<ol reversed>
{% for pub in pubs %}
  <li>
    {{ pub.authors }} ({{ pub.year }}). {{ pub.title }}. <i><strong>{{ pub.venue }}</strong></i>. {{ pub.volume }} {{ pub.page }}.
    {% if pub.doi %}
      <a href="https://doi.org/{{ pub.doi }}" target="_blank">DOI</a>
    {% elsif pub.url %}
      <a href="{{ pub.url }}" target="_blank">Link</a>
    {% endif %}
  </li>
{% endfor %}
</ol>
