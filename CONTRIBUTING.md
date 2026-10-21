# Publishing the technology watch

The public watch lives at `/vigie/`. Jekyll builds the archive, latest-edition links and `/vigie/feed.xml` from the `_vigie` collection. No API key is needed to build or read the site.

## Add or correct an edition

Create `_vigie/YYYY-MM-DD.md` with this front matter, using the publication's actual local date and offset:

```yaml
---
title: "A concise title describing the main news"
date: 2026-10-21 09:00:00 -0400
summary: "One or two sentences describing the edition."
lang: fr
---
```

Write the public bulletin in French. Include the announcement date, an explicit link to each primary source, practical implications, and any uncertainty. Distinguish a released version, a merged change and an unconfirmed issue. Do not fill a quota when nothing significant has changed. If publishing a quiet-day bulletin, say clearly that no significant new development was identified; never present older material as new.

Keep public content independent of private conversations and internal work. Do not copy personalized operational details, private links, correspondence, AI tool citation tokens, or unpublished project descriptions into an edition. Preserve the personal-site attribution in the layout. The first public edition deliberately contains only the verified ECMWF lead item, rather than the full private digest.

Use one file per date. Before retrying a publication, read the existing file and update it using its current SHA instead of creating duplicates. Mark material corrections in the bulletin with their date. Commit to the publishing branch (`master` in the current repository); do not edit generated `_site` files.

## Validation

With Ruby and Bundler available, run `bundle install` and `bundle exec jekyll build`. Check the homepage, `/about/`, `/vigie/`, an edition and `/vigie/feed.xml`. Validate RSS as XML, confirm internal links and check a narrow viewport. Verify the GitHub Pages deployment separately from the source commit.

The recurring research/publication task is managed outside this repository. The site does not generate news merely by being deployed; publication requires a task with access to both current sources and this GitHub repository. Report publication failures instead of claiming the site was updated.
