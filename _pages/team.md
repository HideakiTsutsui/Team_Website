---
title: "Our Team"
layout: single
permalink: /team/
---

## Team Members

{% for member in site.data.team %}
### ![{{ member.name }}]({{ member.image }}){: .align-left width="100px" }

**{{ member.name }}**  
*{{ member.role }}*  
📧 [{{ member.email }}](mailto:{{ member.email }})

{{ member.bio }}

---
{% endfor %}

