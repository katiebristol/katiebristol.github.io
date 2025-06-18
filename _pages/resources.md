---
layout: archive
title: "Resources"
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: banner2.jpg
  actions:
excerpt: "Helpful links and resources"
permalink: /resources/
author_profile: true
---

{% include base_path %}

{% for post in site.resources %}
  {% include archive-single.html %}
{% endfor %}