---
layout: default
title: Search
permalink: /search/
---

# Search

<form class="site-search-page" action="{{ '/search/' | relative_url }}" method="get">
  <label for="search-query">Search research and articles</label>
  <div class="search-page-controls">
    <input id="search-query" name="q" placeholder="Search research &amp; articles..." type="search" value="">
    <button class="btn-primary" type="submit">Search</button>
  </div>
</form>

<div id="search-results" aria-live="polite">
  <p class="search-status">Loading search index...</p>
</div>

<script>
(function () {
  var posts = {{ site.posts | jsonify }};
  var params = new URLSearchParams(window.location.search);
  var query = (params.get('q') || '').trim();
  var input = document.getElementById('search-query');
  var results = document.getElementById('search-results');
  if (input) input.value = query;

  function text(post) {
    return [post.title, post.excerpt, (post.categories || []).join(' '), (post.tags || []).join(' ')].join(' ').toLowerCase();
  }
  function render(items) {
    if (!items.length) {
      results.innerHTML = '<p class="search-status">No matching research or articles were found.</p>';
      return;
    }
    results.innerHTML = items.map(function (post) {
      var excerpt = (post.excerpt || '').replace(/<[^>]+>/g, '').slice(0, 240);
      return '<article class="article-card"><p class="card-kicker">' + (post.date || '') + '</p><h2><a href="' + post.url + '">' + post.title + '</a></h2><p>' + excerpt + '</p></article>';
    }).join('');
  }
  if (!query) {
    results.innerHTML = '<p class="search-status">Enter a term to search the research archive.</p>';
  } else {
    render(posts.filter(function (post) { return text(post).indexOf(query.toLowerCase()) !== -1; }));
  }
}());
</script>
