# Editing Guide

This guide explains how to update the website **content** (members, news, research, etc.)
without touching the site **design**.

The site is built with [Jekyll](https://jekyllrb.com/) and hosted on GitHub Pages at
<https://med-ai.uoguelph.ca>. When you push a change to the `main` branch, the site
rebuilds automatically (usually within a few minutes).

---

## The golden rule

| You want to update… | Edit this | Add images to |
| --- | --- | --- |
| **Lab members** | `_data/members.yml` | `images/members/` (photos), `images/research/` (research figures) |
| **News / announcements** | add a file in `_posts/` | `images/news/` |
| **Publications** | `_data/publications.yml` | `images/publications/` |
| **Research page text** | `_data/research.yml` | `images/research/` |
| **About page text** | `_data/about.yml` | — |
| **Openings page text** | `_data/openings.yml` | — |
| **Homepage focus cards / intro** | `_data/contentbox.yml` | `images/banners/`, `images/backgrounds/` |
| **Homepage hero slider** | `_data/slides.yml` | `images/banners/` |
| **Navigation menu** | `_data/navlinks.yml` | — |

> All editable content lives in **`_data/`**, **`_posts/`**, and **`images/`**.
> If you only edit files in those three places, you cannot break the design.

---

## ⚠️ Do NOT edit these (this is the design / site machinery)

Changing these can break the whole site. Leave them to a developer:

- `_layouts/` and `_includes/` — page templates and shared header/footer
- `assets/` — CSS and JavaScript
- `_config.yml` — Jekyll configuration
- `CNAME` — the custom domain
- `index.html` and the `*/index.html` files (e.g. `research/index.html`) — these are
  page **templates**. They now pull their text from the matching `_data/*.yml` file,
  so you should edit the data file instead.

---

## How-to recipes

### Add or update a lab member

1. Open `_data/members.yml`.
2. Copy an existing member block and edit the fields (`name`, `position`, `degree`,
   `bio`, links, etc.). Active members go under `members:`; alumni go under
   `recent_graduates:`.
3. Add their photo to `images/members/` named `firstname_lastname.png` (or `.jpg`)
   and set `image: "/images/members/firstname_lastname.png"`.
4. (Optional) Add research figures to `images/research/` and list them under
   `research_images:`.

### Add a news post

1. Create a file in `_posts/` named `YYYY-MM-DD-short-title.md` (the date matters).
2. Add front matter at the top:
   ```
   ---
   title: "Your headline here"
   date: 2026-02-14
   ---
   ```
3. Write the content below it (Markdown and basic HTML both work).
4. Put any images in `images/news/` and reference them like:
   `{{site.baseurl}}/images/news/your_image.png`.

### Update a publication

Edit `_data/publications.yml` — copy a block and fill in `title`, `authors`,
`journal`, `year`, `article_url`, and an `image:` under `images/publications/`.

### Edit the Research / About / Openings page text

Edit the matching data file — `_data/research.yml`, `_data/about.yml`, or
`_data/openings.yml`. Just change the text inside the quotes. Basic
`<strong>`, `<em>`, and `<a href="...">` tags are allowed inside the text.

---

## Image folders at a glance

| Folder | What goes here |
| --- | --- |
| `images/members/` | Member headshots (`firstname_lastname.png`) |
| `images/research/` | Research figures shown on member and research pages |
| `images/publications/` | Publication thumbnail figures |
| `images/news/` | Images used in news posts |
| `images/banners/` | Page header banner, homepage banner, hero video |
| `images/backgrounds/` | Page background textures and building photos |
| `images/logos/` | Social / institutional logos |

Use clear, lowercase names with underscores (e.g. `jane_doe.png`,
`spie_2026_jane_poster.png`).

---

## Previewing locally (optional, for developers)

```bash
bundle install
bundle exec jekyll serve
# open http://127.0.0.1:4000/
```
