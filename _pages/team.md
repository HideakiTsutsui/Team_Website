---
title: "Our Team"
layout: single
permalink: /team/
---

<style>
.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
}
.team-card {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
}
.team-card img {
  border-radius: 50%;
  width: 100px;
  height: 100px;
  object-fit: cover;
}
</style>

## Principal Investigator

<div class="team-grid">
{% assign principal_investigator = site.data.team | where: "status", "PI" | sort: "year_joined" %}
{% for member in principal_investigator %}
  <div class="team-card">
    <img src="{{ member.image }}" alt="{{ member.name }}">
    <div>
      <strong>{{ member.name }}</strong><br>
      <em>{{ member.role }}</em><br>
      {% if member.email %}
        📧 <a href="mailto:{{ member.email }}">{{ member.email }}</a><br>
      {% endif %}
      {{ member.bio }}
    </div>
  </div>
{% endfor %}
</div>

## Current Members

<div class="team-grid">
{% assign current_members = site.data.team | where: "status", "current" | sort: "year_joined" %}
{% for member in current_members %}
  <div class="team-card">
    <img src="{{ member.image }}" alt="{{ member.name }}">
    <div>
      <strong>{{ member.name }}</strong><br>
      <em>{{ member.role }}</em><br>
      {% if member.email %}
        📧 <a href="mailto:{{ member.email }}">{{ member.email }}</a><br>
      {% endif %}
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
