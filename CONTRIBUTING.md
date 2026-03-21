# Contributing

Jekyll personal site. Docker-only workflow.

## Commands

| Task | Command |
|------|---------|
| Preview | `docker compose up` then open `http://localhost:4000` |
| Build (validate) | `docker compose run --rm jekyll jekyll build` |
| Stop | `docker compose down` |
| Reset (after dep changes) | `docker compose down -v && docker compose up` |

## Source files

| File | Purpose |
|------|---------|
| `index.html` | Homepage template (About, Resume, Contact sections) |
| `_config.yml` | Site data: about text, resume entries, contact copy, metadata |
| `_includes/header.html` | Custom header with nav links and dark/light toggle |
| `_includes/footer.html` | Custom footer with social icons and copyright |
| `_sass/minima/custom-styles.scss` | Site-specific style overrides |
| `_sass/minima/custom-variables.scss` | Sass variable overrides |
| `blog.md` | Blog index page (currently `published: false`) |
| `_posts/` | Blog posts |

## Common tasks

- Update homepage copy or sections → edit `index.html`
- Update about, resume, contact, or site metadata → edit `_config.yml`
- Update blog landing page → edit `blog.md`
- Add or edit a blog post → add/edit files in `_posts/`
- Adjust site styling → edit `_sass/minima/custom-styles.scss`

## Do not edit

- `_site/`, `.jekyll-cache/` — generated output
- Scaffold defaults in `_config.yml` — leave unless task explicitly says otherwise

## Working rules

- Use `docker compose` for all preview and build commands.
- Do not rely on host Ruby or Bundler.
- Never edit generated output (`_site/`, `.jekyll-cache/`).
- Keep changes source-based — prefer editing content, config, includes, and Sass.
- If a layout or partial is not clearly referenced, verify usage before changing it.

## Validation

Before finishing any change:
1. `docker compose up` — visually verify at `http://localhost:4000`
2. `docker compose run --rm jekyll jekyll build` — must exit 0
