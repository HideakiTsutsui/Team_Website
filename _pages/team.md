---
title: "Our Team"
layout: single
permalink: /team/
---

<style>
.team-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
}
.team-member {
  flex: 0 0 48%;
  display: flex;
  align-items: flex-start;
  gap: 1rem;
}
.team-member img {
  border-radius: 50%;
  width: 100px;
  height: 100px;
  object-fit: cover;
}
</style>

## Current Members

<div class="team-grid">
{% assign current_members = site.data.team | where: "status", "current" %}
{% assign sorted_current = current_members | sort: "year_joined" %}
{% for member in sorted_current %}
  <div class="team-member">
    <img src="{{ member.image }}" alt="{{ member.name }}">
    <div>
      <strong>{{ member.name }}</strong><br>
      <em>{{ member.role }}</em><br>
      {% if member.email %}<a href="mailto:{{ member.email }}">{{ member.email }}</a><br>{% endif %}
      {{ member.bio }}
    </div>
  </div>
{% endfor %}
</div>

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
