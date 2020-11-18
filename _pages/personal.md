---
layout: page
permalink: /personal/
title: personal
description: music, co-op and coding projects

nav: true
---

## personal project pages

<div class="projects grid">

  {% assign sorted_projects = site.personalprojects | sort: "importance" %}
  {% for project in sorted_projects %}
  <div class="grid-item">
    {% if project.redirect %}
    <a href="{{ project.redirect }}" target="_blank">
    {% else %}
    <a href="{{ project.url | relative_url }}">
    {% endif %}
      <div class="card hoverable">
        {% if project.img %}
        <img src="{{ project.img | relative_url }}" alt="project thumbnail">
        {% endif %}
        <div class="card-body">
          <h2 class="card-title text-lowercase">{{ project.title }}</h2>
          <p class="card-text">{{ project.description }}</p>
          <div class="row ml-1 mr-1 p-0">
            {% if project.github %}
            <div class="github-icon">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ project.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
              </div>
              {% if project.github_stars %}
              <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                <i class="fas fa-star"></i>
                <span id="{{ project.github_stars }}-stars"></span>
              </span>
              {% endif %}
            </div>
            {% endif %}
          </div>
        </div>
      </div>
    </a>
  </div>
{% endfor %}

</div>

## quick info

* I am from Michigan
* I have been playing instruments since I was in middle school, and consider it a really important part of my life
* I believe that housing is a human right and actively participate in local organizing efforts to assert that right for both myself and others
* I am really like housing cooperatives, and have lived in them for four years
* I really like all kinds of skiing (downhill, x-country, backcountry)
* I will never turn on the overhead light in a room if there is a lamp I could use instead
