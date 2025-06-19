---
title: "Our Team"
layout: single
permalink: /team/
---

## Current Members

{% assign current_members = site.data.team | where: "status", "current" %}
{% assign sorted_current = current_members | sort: "year_joined" %}

{% for member in sorted_current %}
### ![{{ member.name }}]({{ member.image }}){: .align-left width="100px" }

**{{ member.name }}**  
*{{ member.role }}*  
📧 [{{ member.email }}](mailto:{{ member.email }})  
{{ member.bio }}

---
{% endfor %}

## Previous Members

### Postdocs

{% assign postdocs = site.data.team | where: "status", "alumni" | where: "position", "postdoc" | sort: "year_left" | reverse %}
{% for member in postdocs %}
{{ member.name }}, {{ member.year_left }}, {{ member.role }} 
{% endfor %}
---

### Graduate Students

{% assign grads = site.data.team | where: "status", "alumni" | where: "position", "grad" | sort: "year_left" | reverse %}
{% for member in grads %}
{{ member.name }}, {{ member.year_left }}, {{ member.role }} 
{% endfor %}
---

### Undergraduate Students

{% assign undergrads = site.data.team | where: "status", "alumni" | where: "position", "undergrad" | sort: "year_left" | reverse %}
{% for member in undergrads %}
{{ member.name }}, {{ member.year_left }}, {{ member.role }}
{% endfor %}
---

### Exchange Students and Visitors

{% assign visitors = site.data.team | where: "status", "alumni" | where: "position", "visitor" | sort: "year_left" | reverse %}
{% for member in visitors %}
{{ member.name }}, {{ member.year_left }}, {{ member.role }}
{% endfor %}
