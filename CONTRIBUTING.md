# Publishing the bilingual technology watch

## Site routes

| Page | English | Français |
| --- | --- | --- |
| Home | `/` | `/fr/` |
| About | `/about/` | `/fr/a-propos/` |
| Technology watch | `/en/vigie/` | `/vigie/` |
| RSS | `/en/vigie/feed.xml` | `/vigie/feed.xml` |
| Daily edition | `/en/vigie/YYYY-MM-DD/` | `/vigie/YYYY-MM-DD/` |

The academic archive is no longer published or linked in navigation. Its historical source remains in Git.

## Add or correct a daily edition

Publish every day, including weekends. Create a matched pair of files: `_vigie/YYYY-MM-DD.md` in French and `_vigie_en/YYYY-MM-DD.md` in English. Both contain the same verified news, qualifiers, dates, sources and practical recommendations, expressed naturally in each language. Use the actual local publication date and UTC offset for America/New_York.

French front matter:

```yaml
---
title: "Un titre concis qui décrit la nouvelle principale"
date: 2026-10-21 09:00:00 -0400
summary: "Une ou deux phrases qui décrivent le bulletin."
lang: fr
translation_url: /en/vigie/2026-10-21/
---
```

English front matter:

```yaml
---
title: "A concise title describing the main news"
date: 2026-10-21 09:00:00 -0400
summary: "One or two sentences describing the bulletin."
lang: en
translation_url: /vigie/2026-10-21/
---
```

Use the date of the actual edition in both translation URLs. The collection defaults select the bilingual edition layout. Jekyll automatically builds each language's latest-edition links, archives and RSS. No API key is needed to build or read the site.

Include the announcement date, an explicit link to each checked primary source, practical implications and any uncertainty. Distinguish a published release, a merged code change and an unconfirmed issue. Do not fill a quota when nothing significant has changed. Publish a brief quiet-day edition in both languages when no significant new development is identified; never present old material as new.

Keep public content independent of private conversations and internal work. Do not copy private correspondence, personalized operational details, unpublished project descriptions, AI tool citation tokens or private links into an edition. Keep personalized LinkedIn advice in the private report. Preserve personal-site attribution in the layout.

Use one file per date per language. Read the current file and its SHA before updating it. Publish the pair in one commit where possible, so language-switch links do not point at a missing translation. Mark material corrections with their date in both versions. Commit to the publishing branch (`master`); do not edit generated `_site` files or unrelated pages.

## Validation

With Ruby and Bundler available, run `bundle install` and `bundle exec jekyll build`. Check both homepages, About pages, watch indexes, edition translations and RSS feeds. Validate RSS as XML, verify reciprocal language links, and check a narrow viewport. Confirm `/school/` is no longer published. Verify deployment separately from the source commit.

The recurring research/publication task is managed outside this repository. Publication requires a task with access to both current sources and this GitHub repository. Report publication failures instead of claiming that the site was updated.
