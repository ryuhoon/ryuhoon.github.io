# AGENTS.md

Guidance for AI coding agents (OpenAI Codex, Claude Code, etc.) working in this repository.

## Project

- Personal blog served by GitHub Pages at https://ryuhoon.github.io (`ryuhoon/ryuhoon.github.io`).
- Jekyll site built on the Minimal Mistakes theme, with the theme files vendored in the repo (`_layouts`, `_includes`, `_sass`, `assets`).
- Site language is Korean (`locale: "ko"`). Write posts and UI text in Korean unless asked otherwise.

## Layout

| Path | Purpose |
| --- | --- |
| `_config.yml` | Site settings. Not hot-reloaded: restart `jekyll serve` after editing. |
| `_posts/` | Blog posts, named `YYYY-MM-DD-title.md`, with YAML front matter. |
| `_pages/` | Archive pages (category, tag, year). |
| `_data/navigation.yml`, `_data/ui-text.yml` | Navigation and UI strings. |
| `_layouts/`, `_includes/`, `_sass/` | Theme templates and styles. Change only when asked. |
| `assets/js/` | Theme JavaScript. `main.min.js` is generated; do not edit it by hand. |

## Commands

- Rebuild the minified JS after changing files under `assets/js/`: `npm install && npm run build:js`
- Local preview, if Ruby and Jekyll are available: `bundle exec jekyll serve`
- No automated tests. `.travis.yml` is leftover theme-docs config and is not used by this site.

## Conventions

- New posts: add `_posts/YYYY-MM-DD-slug.md` with front matter (`title`, `date`, `categories`, `tags`). Avoid spaces in file names (existing `first copy.md` is a leftover).
- Keep changes minimal and scoped to the request. Do not reformat unrelated files.
- Do not edit `package-lock.json` or vendored theme code unless the task requires it.
- Never commit secrets or API keys. `staticman.yml` and `_config.yml` are public.

## Workflow

- Develop on a feature branch and open a pull request against the default branch. Do not push directly to the default branch, since GitHub Pages publishes from it.
- Write short, descriptive commit messages.
