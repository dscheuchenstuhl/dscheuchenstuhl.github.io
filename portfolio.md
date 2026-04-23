---
title: "Portfolio"
layout: single
permalink: /portfolio/
---

## Professional Experience

{% assign work_projects = site.portfolio | where: "category", "work" | sort: "order" %}
{% for project in work_projects %}
  <div class="card">
    <h3>
      <a href="{{ project.url }}">{{ project.title }}</a>
    </h3>
    <p>{{ project.excerpt }}</p>
  </div>
{% endfor %}

## Extracurricular & Competitive Projects

{% assign extra_projects = site.portfolio | where: "category", "extracurricular" | sort: "order" %}
{% for project in extra_projects %}
  <div class="card">
    <h3>
      <a href="{{ project.url }}">{{ project.title }}</a>
    </h3>
    <p>{{ project.excerpt }}</p>
  </div>
{% endfor %}
