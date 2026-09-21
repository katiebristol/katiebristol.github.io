---
layout: page
title: Teaching+Outreach
permalink: /teaching-outreach/
description: Some courses and outreach initiatives that I've been involved with.
nav: true
nav_order: 6
display_categories: [outreach, teaching] 
horizontal: false
---

<!-- pages/teaching-outreach.md -->
<div class="gallery">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_TO = site.gallery | where: "category", category %}
  {% assign sorted_TO = categorized_gallery | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for TO in sorted_TO %}
      {% include gallery_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for TO in sorted_TO %}
      {% include gallery.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_gallery = site.gallery | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for TO in sorted_TO %}
      {% include gallery_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for TO in sorted_TO %}
      {% include gallery.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>