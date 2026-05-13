# yanisstentzel.github.io

Personal portfolio website built with [Hugo](https://gohugo.io/) and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.

## Live site

- https://yanisstentzel.github.io/

## What this repository contains

- Hugo site configuration (`config.yml`)
- Portfolio content in Markdown (`content/projects`, `content/skills`)
- Static assets (favicons, images, PDFs) in `static/`
- Theme and template customizations (`themes/PaperMod`, `layouts/`, `assets/css/extended/custom.css`)

## Run locally

This project uses **Hugo Extended** (the GitHub Actions workflow currently uses `0.147.2`).

```bash
hugo server -D
```

Build the production output:

```bash
hugo --minify
```

Generated files are written to `public/`.

## Tech stack

- Hugo (static site generator)
- PaperMod theme
- Markdown content
- YAML configuration
- Custom CSS overrides in `assets/css/extended/custom.css`
