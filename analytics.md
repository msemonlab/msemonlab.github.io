---
layout: default
title: Analytics
permalink: /analytics/
---

<section class="article-card">
  <p class="card-kicker">ANALYTICAL ARCHIVE</p>
  <h1 style="margin-top: 0; margin-bottom: 16px;">Analytics</h1>
  <div class="status-card" style="margin-top: 20px;">
    <p style="margin-bottom: 16px;">The Analytics Archive synthesizes data-driven models, behavioral telemetry, and system-level experimentation.</p>
    <div class="focus-panel">
      <span>Strategic Vectors:</span>
      <p>Customer-centric architecture, e-commerce scalability, and cognitive decision quality.</p>
    </div>
    <p class="status-note" style="margin-bottom: 0;">System status: Initializing computational pipelines.</p>
  </div>
</section>

{% assign analytics_posts = site.posts | where_exp: "post", "post.categories contains 'Analytics'" %}
{% if analytics_posts.size > 0 %}
  {% for post in analytics_posts %}
    <article class="article-card" style="margin-top: 28px;">
      <p class="card-kicker">{{ post.date | date: "%d %B %Y" }}</p>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      {% if post.excerpt %}<p>{{ post.excerpt | strip_html | truncate: 260 }}</p>{% endif %}
    </article>
  {% endfor %}
{% endif %}
