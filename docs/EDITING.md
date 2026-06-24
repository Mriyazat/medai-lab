# Editing Guide

All editable content lives in `_data/`, `_posts/`, and `images/`.
Push to `main` and the site rebuilds automatically.

## Where things live

| To update… | Edit | Images go in |
| --- | --- | --- |
| Lab members | `_data/members.yml` | `images/members/`, `images/research/` |
| News | a file in `_posts/` | `images/news/` |
| Publications | `_data/publications.yml` | `images/publications/` |
| Research page | `_data/research.yml` | `images/research/` |
| About page | `_data/about.yml` | — |
| Openings page | `_data/openings.yml` | — |
| Homepage cards / intro | `_data/contentbox.yml` | `images/banners/`, `images/backgrounds/` |
| Homepage slider | `_data/slides.yml` | `images/banners/` |
| Navigation menu | `_data/navlinks.yml` | — |

## Adding new content

**Member** — in `_data/members.yml`, copy a block and edit the fields. Active members
under `members:`, alumni under `recent_graduates:`. Add the photo to `images/members/`
as `firstname_lastname.png` and set `image: "/images/members/firstname_lastname.png"`.

**News post** — add `_posts/YYYY-MM-DD-short-title.md` starting with:

```
---
title: "Your headline"
date: 2026-02-14
---
```

Write content below (Markdown + HTML). Reference images as
`{{site.baseurl}}/images/news/your_image.png`.

**Publication** — in `_data/publications.yml`, copy a block and fill `title`, `authors`,
`journal`, `year`, `article_url`, and `image:` (from `images/publications/`).

**Page text** (research / about / openings) — edit the matching `_data/*.yml` file.
`<strong>`, `<em>`, and `<a href="...">` are allowed inside the text.

## Naming

Lowercase with underscores, e.g. `jane_doe.png`, `spie_2026_jane_poster.png`.
