---
layout: page
title: projects
permalink: /projects/
description: A collection of things I've built.
nav: true
nav_order: 1
display_categories: [web, tools, experiments]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{% if page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endfor %}

{% else %}

<!-- Display projects without categories -->
  {% assign sorted_projects = site.projects | sort: "importance" %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
{% endif %}
</div>
