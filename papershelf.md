---
layout: default
title: Papershelf
permalink: /papershelf/
---

<section class="section">
  <h1>Papershelf</h1>
  <p>Notes and commentary on papers I've read.</p>
  
  <ul class="post-list">
    {% for paper in site.papershelf %}
      <li>
        <h3>
          <a class="post-link" href="{{ paper.url | relative_url }}">
            {{ paper.title | escape }}
          </a>
        </h3>
        {% if paper.description %}
          <p>{{ paper.description }}</p>
        {% endif %}
      </li>
    {% endfor %}
  </ul>
</section>
