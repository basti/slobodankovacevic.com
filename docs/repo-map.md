# Repo Map

This document identifies the source files that drive the live site.

## Content model

- `index.html` defines the main landing page sections, including the about, resume, and contact content rendered on the homepage.
- `_config.yml` contains site-level content and structured data such as `who_am_i`, `what_am_i`, and the `resume` collection used on the homepage.
- `_posts/` contains blog entries.
- `blog.md` defines the blog index page.

## Templates and styling

- `_layouts/` contains custom layouts. Verify that a layout is referenced before assuming it is active.
- `css/style.css` contains site-specific styling.
- Files under `css/`, `js/`, and `fonts/` may include vendored third-party assets. Do not change those by default unless the task explicitly requires it.

## Generated output

- `_site/` is generated output from Jekyll. It is not a source directory and should not be edited.
- `.jekyll-cache/` is local build cache data and should not be edited.

## Workflow

- Use `docker compose up` for local preview.
- Use `docker compose run --rm jekyll jekyll build` for a one-off validation build.
- Do not rely on host Ruby or Bundler as the default workflow for this repository.
