# Site consistency fixes

These files were updated after comparing `https://msemonlab.github.io` with the current Blogger site at `https://www.msemon.iam.bd`.

## Updated files

- `_layouts/default.html`: removes the extra header tagline, uses the Blogger-style homepage title, avoids the nested homepage card, hides empty category/archive widgets, and keeps footer links aligned with the Jekyll pages.
- `index.md`: removes the GitHub-only Explore Research button and duplicate body-level About section.
- `_data/navigation.yml`: removes the duplicate Home navigation item.
- `_config.yml`: keeps the standard GitHub Pages URL and existing Jekyll metadata.
- `README.md`: keeps documentation independent of the retired custom domain.
- `MIGRATION_GUIDE.md`: keeps publishing guidance independent of the retired custom domain.

## Manual deletion

If the earlier package was already uploaded, delete `CNAME` from the repository. It is intentionally not included in this update because ZIP archives do not encode file deletions.

## Still intentionally not migrated

The Blogger logo is rendered by the theme rather than exposed as a standalone image asset. Blogger posts, pages, article images, downloads, and any theme-specific widgets still require the Blogger XML export and asset files before they can be migrated faithfully.
