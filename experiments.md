---
layout: default
title: Experiments
permalink: /experiments/
---
<h1 class="page-heading">Experiments</h1>

<p class="page-index">Jump to:
{% for section in site.data.experiments %}<a href="#{{ section.id }}">{{ section.title }}</a>{% unless forloop.last %} &middot; {% endunless %}{% endfor %}
</p>

{% for section in site.data.experiments %}
<div class="experiments-section">
  <h2 id="{{ section.id }}" class="page-section-heading">{{ section.title }}</h2>
  <p class="experiments-description">{{ section.description }} <a class="experiments-project-link" href="{{ section.project_url | relative_url }}">Read more: {{ section.project_label }} &raquo;</a></p>

  <div class="row experiments-grid">
    {% for item in section.items %}
    <div class="col-xs-12 col-sm-6 col-md-4">
      <div class="experiment-card">
        <a class="experiment-thumb" href="{{ item.url }}">
          <img src="{{ "assets/experiments/" | append: item.thumb | relative_url }}" alt="{{ item.title | escape }}" width="300" height="300" loading="lazy" />
        </a>
        <h4 class="experiment-title"><a href="{{ item.url }}">{{ item.title }}</a></h4>
        <details class="experiment-about">
          <summary>About</summary>
          <p>{{ item.about }}</p>
        </details>
      </div>
    </div>
    {% endfor %}
  </div>
</div>
{% endfor %}
