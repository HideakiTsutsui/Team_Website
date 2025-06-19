---
title: "Photo Gallery"
layout: single
permalink: /photos/
---

## Team Photo Archive

{% assign sorted_photos = site.data.photos | sort: "year" | reverse %}

{% for year_group in sorted_photos %}
### {{ year_group.year }}

{% for event in year_group.events %}
#### {{ event.title }}

<div class="gallery">
  {% for img in event.images %}
    <figure>
      <img src="{{ img.path }}" alt="{{ img.caption }}">
      <figcaption>{{ img.caption }}</figcaption>
    </figure>
  {% endfor %}
</div>

{% endfor %}

---
{% endfor %}
