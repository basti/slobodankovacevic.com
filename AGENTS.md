# Agent Notes

This is a Jekyll site repository.

## Start here

- Canonical workflow: Docker only
- Preview command: `docker compose up`
- Preview URL: `http://localhost:4000`
- Validation build: `docker compose run --rm jekyll jekyll build`

## Source of truth

- `index.html`: main landing page content
- `_config.yml`: site data and structured content
- `blog.md`: blog index
- `_posts/`: blog posts
- `_layouts/`: custom layouts when referenced
- `css/style.css`: site-specific styling

## Common tasks

- Update homepage copy or sections: edit `index.html`
- Update bio, resume, or site metadata: edit `_config.yml`
- Update blog landing page: edit `blog.md`
- Add or edit a blog post: add/edit files in `_posts/`
- Adjust site styling: edit `css/style.css`

## Do not edit by default

- `_site/`
- `.jekyll-cache/`
- third-party vendor assets in `css/`, `js/`, and `fonts/`

## Working rules

- Prefer source edits over generated output.
- Do not assume host Ruby or Bundler is set up correctly.
- If a file appears generated or vendored, leave it alone unless the task explicitly requires it.

## More detail

- Project overview and quickstart: `README.md`
- Workflow and validation rules: `CONTRIBUTING.md`
- Repo structure details: `docs/repo-map.md`
