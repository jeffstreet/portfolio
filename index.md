---
layout: default
title: Home
---

<div class="home-intro">
  <p>Jeff Street is a product-oriented leader with engineering background. 15 years of leading small teams to develop innovative new vehicles.</p>
</div>

<section class="home-section">
  <h2>Projects</h2>
  <div class="projects-grid">
    {% assign sorted_projects = site.projects | sort: 'date' | reverse %}
    {% for project in sorted_projects limit: 12 %}
    <a href="{{ project.url | relative_url }}" class="project-card">
      {% if project.image %}
      <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" loading="lazy">
      {% endif %}
      <div class="project-card-body">
        <h3>{{ project.title }}</h3>
        <span class="year">{{ project.year }}</span>
        {% if project.summary %}<p>{{ project.summary }}</p>{% endif %}
      </div>
    </a>
    {% endfor %}
  </div>
  <p style="margin-top: 1.5rem;"><a href="{{ '/projects/' | relative_url }}">View all projects &rarr;</a></p>
</section>

<section class="home-section">
  <h2>Recent Posts</h2>
  <ul class="post-list">
    {% for post in site.posts limit: 8 %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>
    </li>
    {% endfor %}
  </ul>
  <p style="margin-top: 1rem;"><a href="{{ '/blog/' | relative_url }}">View all posts &rarr;</a></p>
</section>

<section class="home-section">
  <h2>Elsewhere</h2>
  <ul class="home-links">
    <li><a href="https://www.strava.com/athletes/jeffstreet">Strava</a> - Cycling adventures</li>
    <li><a href="http://tensegritysupply.com">Tensegrity Supply</a> - Construction kits and videos</li>
  </ul>
</section>
