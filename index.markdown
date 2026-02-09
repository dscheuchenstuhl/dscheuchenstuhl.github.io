---
title: "AI & Robotics Research Engineer"
layout: single
author_profile: true
---

## 👋 Hi, I’m Daniel Scheuchenstuhl

I am AI & Robotics Research Engineer at [Siemens AG Austria](https://www.siemens.com/global/en.html) specializing in production-grade machine learning systems with a strong and interdisciplinary background in AI, robotics, software engineering, distributed systems and embedded systems. I work at the intersection of research and engineering, owning the full ML lifecycle - from prototyping and evaluation to deployment, providing scalable solutions and long-term system reliability in industrial environments.

Prior to joining Siemens, I received my master (2023, with distinction) and bachelor (2020) degrees in Computer Engineering at the [Vienna University of Technology (TU Wien)](https://www.tuwien.at/).

### 🔹 What I Do
- Design and deploy scalable ML systems for real-world applications
- Translate research ideas into production-ready models
- Build and optimize low-latency inference pipelines (edge & cloud)
- Collaborate across research, engineering, and product teams

---

## ⭐ Featured Projects
{% assign work_projects = site.portfolio | where: "category", "work" | sort: "order" %}
{% for project in work_projects %}
  <div class="card">
    <h3>
      <a href="{{ project.url }}">{{ project.title }}</a>
    </h3>
    <p>{{ project.excerpt }}</p>
  </div>
{% endfor %}

👉 [View full portfolio →](/portfolio/)

---

## 📄 Publications
Selected peer-reviewed publications and preprints.

👉 [View publications →](/publications/)

---

## 📎 Curriculum Vitae
👉 [Download CV (PDF)](/user_assets/Scheuchenstuhl_Daniel_CV.pdf)
