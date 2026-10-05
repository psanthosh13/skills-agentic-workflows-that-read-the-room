---
name: update-github-info
description: Keep Mona's GitHub Info content current with practical updates from official GitHub sources.
on:
  schedule: daily
  workflow_dispatch:

permissions:
  contents: read

tools:
  edit:
  web-fetch:

network:
  allowed:
    - github.blog
    - github.com
    - awesome-copilot.github.com

safe-outputs:
  create-pull-request:
    draft: true
---

# Update GitHub Info

Read `notes/mona-notes.md` and follow its guidance. Also read `site/content/github-info.md` before making changes.

Use web fetch to read all of these sources:

- https://github.blog/latest/
- https://github.blog/changelog/
- https://awesome-copilot.github.com/workflows/

Identify recent updates that give developers practical guidance and fit the existing editorial angle and homepage themes in `site/content/github-info.md`. Only use details confirmed on the fetched pages.

Update `site/content/github-info.md` with short, practical additions. Avoid duplicating existing content, and mention the source (GitHub Blog, GitHub Changelog, or Awesome Copilot workflows) with a link for every addition.

If there is nothing useful to add, make no changes and do not open a pull request. Otherwise, open a pull request for Mona to review. Never write directly to `main`.
