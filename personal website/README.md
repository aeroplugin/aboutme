# Personal website

A small, dependency-free personal site. Serif/essay typography and a warm cream palette
(darshshri.dev), script section headings + list rows with dates and clean fade-up motion
(diwen.dev), a lowercase, pared-back voice (idhant.dev), and a persistent multi-page top
nav (krishivthakuria.com) — with an **interactive topological space** as the home-page
centerpiece instead of a molecule. No build step, no frameworks.

Each page is a single self-contained `.html` file — CSS and the 3D script are inlined — so
you can just **double-click any file to open it** in a browser. Nothing to serve, no shared
files to keep in sync at load time.

## Pages

| File | What it is |
|------|------------|
| `index.html` | Home — hero, the topological centerpiece, intro, selected work |
| `work.html` | Work — image + title — year + description entries |
| `writing.html` | Writing — essay/notes list with dates |
| `about.html` | About — bio, "now", and contact |

The top nav (`home · work · writing · about`) is repeated in each file — to add or rename a
page, update the `<nav>` block in all four and move `class="active"` to the current page.

## Customize

Edit the blocks marked `<!-- EDIT ... -->`. Your name, the intro, work entries, writing
rows, and footer links are all plain HTML. Duplicate a `.entry` (work) or `.row` (writing)
to add items. For work images, swap the `<div class="ph">` placeholder for:

```html
<img class="entry-media" src="images/project.jpg" alt="Project screenshot" />
```

### Colors & fonts
- Rebrand with **one value**: `--accent` in the `:root` block at the top of each file's
  `<style>`. Dark mode is automatic (it follows the OS) and has its own token block below.
- The `<style>` block is identical in all four pages — if you change styling, update each
  file (or re-link a shared `style.css` if you'd rather keep it in one place).
- Fonts are **Newsreader** (serif) + **Dancing Script** (headings), from Google Fonts, with
  a system-serif fallback if offline.

### The topological centerpiece
A tiny canvas 3D engine inlined at the bottom of `index.html` (no libraries) renders a
**Möbius strip** — a surface with a single side and one continuous edge (highlighted in the
accent color). It auto-rotates, responds to drag, zooms with − / +, and is disabled for
visitors who prefer reduced motion. To swap in another surface, replace the `mobius()`
point generator.

## Hosting (whenever you want)

These are plain static files, so they work on any static host — Netlify, Vercel, Cloudflare
Pages, an S3 bucket, or your own server. Just upload the folder; `index.html` is the entry
point. No build and no configuration required.
