---
title: "Physical AI Engineer"
layout: single
author_profile: true
description: "Physical AI Engineer specializing in autonomous systems that perceive, reason, and act in complex real-world environments"
---

## 👋 Hi, I’m Daniel Scheuchenstuhl

I am a Research Scientist at [Siemens AG Austria](https://www.siemens.com/global/en.html) with 3 years of post-MSc professional experience and a 14-year technical trajectory in software engineering augmented with deep expertise in Machine Learning, Computer Vision, Robotics, Generative AI, and MLOps. I currently specialize in Physical AI: the development of autonomous systems that perceive, reason, and act in complex, real-world environments. My work lives at the intersection of Machine Perception, Distributed Systems, and Embedded AI. As a polyglot engineer, I operate across the full robotics stack where I have strong experience in designing robust model lifecycles for latency-critical applications.

Prior to joining Siemens, I received my master (2023, with distinction) and bachelor (2020) degrees in Computer Engineering at the [Vienna University of Technology (TU Wien)](https://www.tuwien.at/).

### 🔹 What I Do
- Design and architect end-to-end systems for Physical AI and Industrial Vision applications
- Design and deploy scalable, latency-critical ML systems for edge and cloud
- Translate cutting-edge research into production-ready solutions
- Collaborate across research, engineering, and product teams

---

## ⭐ Featured Projects

### Professional Experience
{% assign work_projects = site.portfolio | where: "category", "work" | sort: "order" %}
{% for project in work_projects %}
  <div class="card">
    <h3>
      <a href="{{ project.url }}">{{ project.title }}</a>
    </h3>
    <p>{{ project.excerpt }}</p>
  </div>
{% endfor %}

### Competitive & Extracurricular
{% assign extra_projects = site.portfolio | where: "category", "extracurricular" | sort: "order" %}
{% for project in extra_projects %}
  <div class="card">
    <h3>
      <a href="{{ project.url }}">{{ project.title }}</a>
    </h3>
    <p>{{ project.excerpt }}</p>
  </div>
{% endfor %}
<br>

👉 [View full portfolio →](/portfolio/)

---

## 📄 Publications
Selected peer-reviewed publications and preprints.

👉 [View publications →](/publications/)

---

## 📎 Curriculum Vitae
👉 [Download CV (PDF)](/user_assets/Scheuchenstuhl_Daniel_CV.pdf)
