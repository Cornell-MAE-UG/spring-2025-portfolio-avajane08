---
layout: default
title: Ava Farkash - Beyond Engineering
permalink: /beyond-engineering/
---
## Beyond Engineering

Outside of classes and my teams, this is where I keep the things I build and do just for fun.

<div class="gallery-container">
<div class="project-gallery">
    {% for project in site.projects %}
      {% if project.category != 'beyond' %}{% continue %}{% endif %}
      <div class="gallery-item">
        <a href="{{ project.url | relative_url }}">
          <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" />
          <p>{{ project.title}}</p>
        </a>
      </div>
    {% endfor %}
</div>
</div>
