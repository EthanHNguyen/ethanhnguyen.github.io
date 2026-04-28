---
layout: archive
title: "Publications"
permalink: /publications/
excerpt: "Peer-reviewed machine learning research by Ethan H. Nguyen in computer vision and medical image analysis, connected to frontier AI systems, evaluation, reliability, and operational trust."
description: "Peer-reviewed machine learning research by Ethan H. Nguyen in computer vision and medical image analysis, connected to frontier AI systems, evaluation, reliability, and operational trust."
author_profile: true
---

My research background is in deep learning, computer vision, and medical image analysis. Today, I apply that research foundation to production ML systems: model evaluation, deployment constraints, data quality, observability, and the engineering required to make advanced AI useful in real environments.

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
