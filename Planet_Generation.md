---
layout: page
title: Planet Generation/Terraforming
header_image: assets\images\PlanetGeneration\image-248.png
---

<style>
.responsive-flex {
  display: flex;
  align-items: flex-start;
  gap: 24px;
  margin-bottom: 40px;
}
.responsive-flex video {
  border-radius: 8px;
  flex-shrink: 0;
  max-width: 100%;
  height: auto;
}
@media (max-width: 900px) {
  .responsive-flex {
    flex-direction: column !important;
    gap: 16px;
  }
  .responsive-flex video {
    width: 100% !important;
    max-width: 100%;
  }
}
</style>

{% for section in site.data.Planet_Generation.sections %}
  <div class="responsive-flex"{% if section.direction == "right" %} style="flex-direction: row-reverse;"{% endif %}>
  {% if section.video and (section.direction == "right" or section.direction == "left") %}
    <video src="{{ section.video }}" width="600" loop autoplay muted>
      Your browser does not support the video tag.
    </video>
  {% endif %}
    <div>
      <h3>{{ section.title }}</h3>
      {{ section.content | markdownify }}
        {% if section.video and section.direction == "below" %}
      <video src="{{ section.video }}" width="600" loop autoplay muted>
        Your browser does not support the video tag.
      </video>
  {% endif %}
    </div>
  </div>
{% endfor %}