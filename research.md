---
layout: default
title: Research
permalink: /research/
---

# Research

This section will collect research publications, analytical deep-dives, and structured research notes.

{% assign research_posts = site.posts | where_exp: "post", "post.categories contains 'Research'" %}
{% if research_posts.size > 0 %}
  {% for post in research_posts %}
    <article class="article-card">
      <p class="card-kicker">{{ post.date | date: "%d %B %Y" }}</p>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      {% if post.excerpt %}<p>{{ post.excerpt | strip_html | truncate: 260 }}</p>{% endif %}
    </article>
  {% endfor %}
{% else %}
  <article class="status-card">
    <h2>Research archive initializing</h2>
    <p>Research posts will appear here after the Blogger archive is converted into Jekyll posts.</p>
  </article>
{% endif %}
