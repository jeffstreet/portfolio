# Jeff Street Portfolio — Jekyll Site

## What this is
Personal portfolio site for Jeff Street — hardware/drone/product leader who is also into cycling and photography. Audience is potential collaborators and partners, not recruiters. The site should demonstrate that Jeff is a builder.

## Architecture
- **Static site generator**: Jekyll (GitHub Pages compatible)
- **Content/style separation**: All content is in markdown files with YAML frontmatter. Visual styling is entirely in `assets/style.css` using CSS custom properties. You can restyle without touching content.
- **No JavaScript dependencies**. No frameworks. No web fonts.

## Content structure
- `_projects/` — 47 project write-ups with frontmatter (title, year, tags, status, image, summary)
- `_posts/` — 58 blog posts (lifestyle, photography, travel, vehicles, drone videos)
- `pages/about.md` — Bio and external links
- `pages/now.md` — "What I'm working on" (template for Jeff to fill)
- `index.md` — Homepage with project grid and recent posts
- `projects/index.html` — All projects page
- `blog/index.html` — All posts page

## Frontmatter schemas

### Projects (`_projects/*.md`)
```yaml
title: "string"
year: number
tags: []          # e.g. [hardware, drones, making, cycling]
status: string    # shipped / in-progress / concept
image: string     # /assets/images/filename.ext
summary: string   # one sentence
layout: project
date: YYYY-MM-DD  # used for sorting
original_url: string  # original Tumblr permalink (if migrated)
```

### Posts (`_posts/YYYY-MM-DD-slug.md`)
```yaml
title: "string"
date: YYYY-MM-DD
tags: []
image: string     # /assets/images/filename.ext
original_url: string  # original Tumblr permalink
layout: post
```

## CSS custom properties (restyle hooks)
All visual styling uses these variables in `:root` of `assets/style.css`:
- `--color-primary`, `--color-bg`, `--color-text`, `--color-muted`
- `--color-border`, `--color-link`, `--color-link-hover`, `--color-surface`
- `--font-body`, `--font-heading`
- `--max-width`, `--content-width`

## Layouts
- `_layouts/default.html` — Base HTML shell with header nav and footer
- `_layouts/project.html` — Project detail page (extends default)
- `_layouts/post.html` — Blog post page (extends default)

## Includes
- `_includes/youtube.html` — Responsive YouTube embed (param: `id`)
- `_includes/vimeo.html` — Responsive Vimeo embed (param: `id`)
- `_includes/sketchfab.html` — Responsive Sketchfab embed (param: `id`)

## Local development
```bash
bundle install
bundle exec jekyll serve
```

## Deployment
GitHub Pages from the `main` branch. Base URL is `/portfolio`.

## Content origins
- Tumblr export (92 posts with local media) — primary source
- Reference folder with high-res images and project descriptions from cv.jeffstreet.com
- Web crawl of jeffstreet.com for supplementary content

## Known issues
See `PUNCH_LIST.md` for:
- Videos needing YouTube upload (17 local files)
- External links to verify
- Posts with minimal content
- Suggested new content
