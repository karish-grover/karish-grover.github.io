---
layout: page
permalink: /publications/
title: Publications
description: Peer-reviewed work in geometric learning, graph machine learning, and language.
years: [2026, 2025, 2024, 2022, 2021]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
