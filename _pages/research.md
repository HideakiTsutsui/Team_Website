---
title: "Research"
layout: single
permalink: /research/
---

## Ongoing Projects

{% for research in site.data.research %}
### {{ research.title }}

![{{ research.title }}]({{ research.image }}){: .align-left .feature__image }  

{{ research.summary }}

[Learn more]({{ research.url }})
{% endfor %}
