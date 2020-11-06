---
layout: page
permalink: /publications/
title: publications & presentations
description: publications and conference presentations over the course of my undergraduate degree.
years: [2020, 2017]
nav: true
---

<div class="publications">

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
