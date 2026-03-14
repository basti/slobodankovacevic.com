# Contributing

This repository is maintained as a Docker-run Jekyll site. Use the Docker workflow for local preview and validation.

## Working rules

- Use `docker compose` for preview and build commands.
- Do not treat host Ruby or Bundler as the supported workflow.
- Never edit `_site/` or `.jekyll-cache/`.
- Keep changes source-based. Prefer editing content, config, layouts, and site CSS instead of generated output.
- Do not edit third-party vendor assets unless the task explicitly asks for it. This includes:
  - `css/bootstrap.css`
  - `css/bootstrap.min.css`
  - legacy files under `js/`
  - Font Awesome bundles under `fonts/font-awesome/`
- `_config.yml` contains some Jekyll scaffold defaults. Do not remove or normalize them unless the task includes config cleanup.

## Common source files

- `index.html`: main landing page sections and copy
- `_config.yml`: structured site content such as bio and resume entries
- `blog.md`: blog index page
- `_posts/`: blog content
- `_layouts/`: custom templates
- `css/style.css`: site-specific styles

## Validation checklist

Before finishing a change:

1. Start the site with `docker compose up`.
2. Verify the site at `http://localhost:4000`.
3. Run a one-off build with `docker compose run --rm jekyll jekyll build`.

## Notes for automated contributors

- Treat `_site/` as generated output from Jekyll, even if it exists in the working directory.
- If a layout or partial is not clearly referenced, verify usage before changing it.
- Prefer minimal edits that preserve the current site structure and legacy asset setup.
