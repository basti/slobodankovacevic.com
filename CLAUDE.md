# Project

Jekyll personal site. Docker-only workflow.

## Commands

| Task | Command |
|------|---------|
| Preview | `docker compose up` then open `http://localhost:4000` |
| Build (validate) | `docker compose run --rm jekyll jekyll build` |
| Stop | `docker compose down` |
| Reset (after dep changes) | `docker compose down -v && docker compose up` |

## Source files

- `index.html` — homepage content and sections
- `_config.yml` — site data (bio, resume entries, metadata)
- `blog.md` — blog index page
- `_posts/` — blog posts
- `_layouts/` — custom templates
- `css/style.css` — site-specific styles

## Common tasks

- Update homepage copy or sections → edit `index.html`
- Update bio, resume, or site metadata → edit `_config.yml`
- Update blog landing page → edit `blog.md`
- Add or edit a blog post → add/edit files in `_posts/`
- Adjust site styling → edit `css/style.css`

## Do not edit

- `_site/`, `.jekyll-cache/` — generated output
- `css/bootstrap*.css`, `js/`, `fonts/` — vendored third-party assets
- Scaffold defaults in `_config.yml` — leave unless task explicitly says otherwise

## Validation

Before finishing any change:
1. `docker compose up` — visually verify at localhost:4000
2. `docker compose run --rm jekyll jekyll build` — must exit 0

## Detailed docs

- Workflow and rules: [CONTRIBUTING.md](CONTRIBUTING.md)
- Source file map: [docs/repo-map.md](docs/repo-map.md)
