---
layout: default
title: Research
permalink: /research/
---

<section class="article-card">
  <p class="card-kicker">RESEARCH ARCHIVE</p>
  <h1 style="margin-top: 0; margin-bottom: 16px;">Research</h1>
  <div class="status-card" style="margin-top: 20px;">
    <p style="margin-bottom: 16px;">The Research Archive maintains a structured repository of working papers, strategic syntheses, and computational models.</p>
    <p class="status-note" style="margin-bottom: 0;">System status: Consolidating foundational publications.</p>
  </div>
</section>

{% assign research_posts = site.posts | where_exp: "post", "post.categories contains 'Research'" %}
{% if research_posts.size > 0 %}
  {% for post in research_posts %}
    <article class="article-card" style="margin-top: 28px;">
      <p class="card-kicker">{{ post.date | date: "%d %B %Y" }}</p>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      {% if post.excerpt %}<p>{{ post.excerpt | strip_html | truncate: 260 }}</p>{% endif %}
    </article>
  {% endfor %}
{% endif %}
