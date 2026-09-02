---
layout: default
title: Analytics
permalink: /analytics/
---

# Analytics

This section will present data-driven analyses, decision frameworks, visual explanations, and analytical experiments.

## Planned content

The initial collection will focus on customer-centric systems, e-commerce scalability, measurable operating frameworks, and the relationship between human cognition and decision quality.

{% assign analytics_posts = site.posts | where_exp: "post", "post.categories contains 'Analytics'" %}
{% if analytics_posts.size > 0 %}
  {% for post in analytics_posts %}
    <article class="article-card">
      <p class="card-kicker">{{ post.date | date: "%d %B %Y" }}</p>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      {% if post.excerpt %}<p>{{ post.excerpt | strip_html | truncate: 260 }}</p>{% endif %}
    </article>
  {% endfor %}
{% else %}
  <article class="status-card">
    <h2>Analytics archive initializing</h2>
    <p>Analytical studies will appear here as the Blogger material is migrated and new work is published.</p>
  </article>
{% endif %}
