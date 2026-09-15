---
layout: default
title: Research
permalink: /research/
---

<section class="home-status" markdown="0">
  <p class="eyebrow">RESEARCH ARCHIVE</p>
  <h2>Research</h2>
  <div class="status-card" style="margin-top: 20px;">
    <div class="status-beacon-wrapper">
      <span class="beacon-dot"></span>
      <span class="beacon-label">Empirical &amp; Behavioral Systems</span>
    </div>
    <p style="margin-bottom: 16px;">The Research Archive maintains a structured repository of working papers, strategic syntheses, and computational models.</p>
    <div class="focus-panel">
      <span>Current Focus:</span>
      <p>Foundational ResearchGate Publication &mdash; <em>In Progress</em></p>
    </div>
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
