<!-- Copilot / AI agent instructions for contributors -->
# AI contributor notes — alexanderhuth.github.io

Purpose: give an AI coding agent the minimal, actionable context to be productive in this repo.

- Project type: Jekyll static site (GitHub Pages). Source files live here and are rendered by Jekyll.
- Main build tool: Bundler + Jekyll (see `Gemfile` and `_config.yml`).

Quick local commands

- Install deps: `bundle install`
- Build once: `bundle exec jekyll build`
- Serve locally with live reload: `bundle exec jekyll serve --livereload`

Key files and directories

- `_config.yml` — primary site config (baseurl, plugins, collections).
- `_includes/` — reusable partials: `header.html`, `footer.html`, `contact.html`.
- `_layouts/` — page templates: `default.html`, `home.html`, `post.html`.
- `_sass/` and `assets/css/main.scss` — SCSS source; edit these for styling changes.
-- `assets/js/search.js` and `search.html` — client-side search implementation (REMOVED).
-- `assets/img/lhits.xml` — search index used by `search.js` (CLEARED).
- `Gemfile` — Ruby dependencies; GitHub Pages compatibility is handled here.
- `CNAME` — custom domain for GitHub Pages.

Conventions & patterns observed (do not invent new ones without asking)

- Pages and posts use YAML front matter; set `layout: page` or `layout: post` as appropriate.
- Reuse partials in `_includes/` instead of duplicating markup across layouts.
- Keep SCSS in `_sass/` and import from `assets/css/main.scss` — editing the compiled CSS is not recommended.
Search removal note

- The site previously included a client-side search (`assets/js/search.js`, `search.html`, `assets/img/lhits.xml`).
- Search has been removed: the header no longer renders the search form and `search.html` shows a disabled message. `assets/js/search.js` was stubbed and the index file was cleared.

Gems & local-build note

- During maintenance I updated project gems to be compatible with the system Ruby (no Ruby version changes were made).
- If you run into gem version conflicts locally, prefer updating gems with `bundle update` rather than changing the system Ruby.

Quick troubleshooting

- If `bundle install` fails due to old locked versions, run:

  bundle update
  bundle install
  bundle exec jekyll build

- Images and static assets live under `assets/` (use `assets/img/` for images).
- Images and static assets live under `assets/` (use `assets/img/` for images).

Editing guidance / examples

- To add a new page: create `newpage.md` at repo root with front matter

  ---
  layout: page
  title: "New Page"
  ---

- To change site header: edit `_includes/header.html` and preview locally via `jekyll serve`.
- To change styles: modify files in `_sass/` or `assets/css/main.scss`, then reload the local server.

Build & PR workflow

- Always run `bundle exec jekyll build` locally to catch Liquid or config errors before opening a PR.
- For visual checks use `bundle exec jekyll serve --livereload` and test in a browser.
- There are no automated tests in this repo; rely on manual preview for verification.

Limitations & assumptions

- This repository is a static Jekyll site with no backend services.
- No test harness, CI scripts, or task runners were found — focus on safe, minimal changes.

If anything in this doc looks incorrect or incomplete, ask for the specific file or behaviour to inspect.
