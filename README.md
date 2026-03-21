# slobodankovacevic.com

This repository contains the source for a Jekyll-based personal site.

## Canonical workflow

Use Docker for local development and validation. Do not treat host Ruby or Bundler as the canonical path for this repo.

### Prerequisites

- A running Docker-compatible daemon such as Docker Desktop or Rancher Desktop
- Port `4000` available on your machine

### Start the site

```sh
docker compose up
```

Open [http://localhost:4000](http://localhost:4000).

On the first run, startup can take longer because Docker may need to pull the `jekyll/jekyll:latest` image and install gems into the container volume.

### Build the site

Run a one-off build in Docker before finishing changes:

```sh
docker compose run --rm jekyll jekyll build
```

### Stop the site

```sh
docker compose down
```

### Live reload

While `docker compose up` is running, Jekyll watches source files and rebuilds automatically.

## Repo map

- `index.html`: main landing page content and sections
- `_config.yml`: site-level content and structured data such as `who_am_i`, `what_am_i`, and `resume`
- `_posts/`: blog posts
- `blog.md`: blog index page
- `_layouts/`: custom layouts used by the site when referenced
- `css/style.css`: site-specific styling
- `_site/`: generated output; not a source directory
- `.jekyll-cache/`: local cache; not a source directory

## Common tasks

- Update homepage copy or sections: `index.html`
- Update biography, resume entries, or site-level metadata: `_config.yml`
- Update the blog landing page: `blog.md`
- Add or edit a blog post: `_posts/`
- Adjust site styling: `css/style.css`

## Editing rules

- Prefer source edits in content, config, layouts, and site CSS.
- Never edit `_site/` or `.jekyll-cache/`.
- Do not edit third-party vendor assets by default unless the task explicitly asks for it. This includes Bootstrap bundles, old jQuery/plugins, and Font Awesome assets under `css/`, `js/`, and `fonts/`.
- Some values in `_config.yml` still come from the default Jekyll scaffold. Do not clean them up unless the task explicitly includes config cleanup.

## Additional guidance

- Contributor workflow and validation rules: [CONTRIBUTING.md](CONTRIBUTING.md)
- Agent-oriented quick rules: [AGENTS.md](AGENTS.md)
- Source-of-truth file map: [docs/repo-map.md](docs/repo-map.md)

## Troubleshooting

- If `docker compose` cannot connect to the daemon, start Docker Desktop or Rancher Desktop first.
- If startup gets stuck after dependency changes, reset the container volume and try again:

```sh
docker compose down -v
docker compose up
```
