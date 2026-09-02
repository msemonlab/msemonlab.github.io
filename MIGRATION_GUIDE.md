# Blogger to GitHub Pages migration guide

## Files added in this migration pass

The repository now contains a Jekyll homepage, navigation data, About, Research, Analytics, and 404 pages, a Pages deployment workflow, and a guide for converting Blogger content.

## What is still needed from Blogger

Export the Blogger content from **Settings → Manage blog → Back up content** and upload the resulting XML file. Also upload the current Blogger theme XML if you want the migration to preserve any widgets, labels, custom sections, or content that is not visible on the public homepage. Please include the original logo, favicon, article images, downloadable files, and any custom CSS or JavaScript that the live site uses.

Do not upload passwords, API keys, private analytics credentials, or other secrets. Blogger XML may contain drafts or private material, so review it before sharing.

## Content conversion rules

Blogger posts should become dated Markdown files under `_posts/` with filenames in the form `YYYY-MM-DD-title.md`. Each post should have front matter such as:

```yaml
---
layout: default
title: Example research title
date: 2026-09-02 12:00:00 +0600
categories: Research
tags: [systems theory, e-commerce]
---
```

Blogger pages should become top-level Markdown files such as `about.md` or `contact.md`. Images should be copied into `assets/images/` and referenced with stable relative URLs. Blogger label URLs should be mapped to Jekyll categories or explicit archive pages.

## Publishing

The site is configured for the standard GitHub Pages address, `https://msemonlab.github.io`. In GitHub repository settings, enable Pages using **GitHub Actions** after the workflow is uploaded. No custom-domain or DNS configuration is included in this package.

## Suggested migration sequence

1. Review and upload the Blogger XML export.
2. Review and upload the Blogger theme XML and original assets if theme fidelity is required.
3. Convert posts and pages into Jekyll Markdown.
4. Copy article media into `assets/images/` and update links.
5. Check important Blogger URLs and add redirects or a URL map where necessary.
6. Upload the files to the `main` branch.
7. Enable GitHub Pages with the Actions source and verify the site at `https://msemonlab.github.io`.
