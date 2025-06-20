---
title: "Research"
layout: single
permalink: /research/
---

## Ongoing Projects

{% for research in site.data.research %}
### {{ research.title }}

![{{ research.title }}]({{ research.image }}){: .align-left .feature__image }  <br/>

{{ research.summary }}

[Learn more]({{ research.url }})
---
{% endfor %}

## Our Sponsors

![Our Sponsors](../assets/images/research/Sponsors.png){: .center width="80%" }
