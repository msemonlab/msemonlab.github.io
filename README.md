# MS Emon Research Repository

This repository contains the Jekyll/GitHub Pages version of MS Emon's research repository, migrated from the Blogger site.

The current site foundation includes the responsive research-repository theme, homepage, navigation, About, Research, Analytics, 404 handling, and a GitHub Pages deployment workflow.

## Local development

Install Ruby and Bundler, then run:

```bash
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000` in a browser.

## Content migration

See [`MIGRATION_GUIDE.md`](MIGRATION_GUIDE.md) for Blogger export requirements, post conversion rules, media handling, URL mapping, and GitHub Pages setup.

Blogger content is not included yet. The next input required for full migration is a reviewed Blogger XML content export, plus the Blogger theme XML and original assets if exact content/theme fidelity is desired.
