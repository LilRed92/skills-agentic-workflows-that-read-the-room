---
name: Update GitHub Info
description: Fetch recent GitHub Blog updates and open a reviewable PR for Mona.
on:
  workflow_dispatch:
  schedule: daily
engine: copilot
permissions:
  contents: read
  pull-requests: read
tools:
  edit:
  web-fetch:
network:
  allowed:
    - defaults
    - github.com
    - github.blog
    - awesome-copilot.github.com
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
---

# Update GitHub Info

## Instructions

1. Read `notes/mona-notes.md` before making any changes.
2. Web fetch `https://github.blog/latest/`, `https://github.blog/changelog/`, and `https://awesome-copilot.github.com/workflows/`.
3. Update `site/content/github-info.md` with a short, practical `Latest GitHub Updates` section.
4. Mention the GitHub Blog, GitHub Changelog, or Awesome Copilot workflows page as the source for any update that comes from those pages.
5. Use the `edit` tool to make the file changes.
6. Use `safe-outputs.create-pull-request` to open a pull request for Mona to review.
7. Do not write directly to `main` or push changes outside the safe-outputs PR flow.

## Notes

- Keep the update concise and useful for developers.
- Limit the change to the GitHub Info page unless a small supporting edit is required.
