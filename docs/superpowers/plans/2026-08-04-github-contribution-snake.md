# GitHub Contribution Snake Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the cached activity chart with a daily generated, monochrome GitHub contribution snake animation.

**Architecture:** A GitHub Actions workflow invokes `Platane/snk/svg-only@v3` for the repository owner, then publishes two SVG assets to an `output` branch. `README.md` renders the appropriate asset with GitHub's responsive `<picture>` syntax.

**Tech Stack:** GitHub Actions, `Platane/snk/svg-only@v3`, `crazy-max/ghaction-github-pages@v3.1.0`, Markdown.

## Global Constraints

- Keep the existing profile prose and typography unchanged.
- Use restrained monochrome colours.
- Do not add badges, cards, or other decorative elements.
- The workflow must have the least permissions needed to write its generated branch.

---

### Task 1: Add the SVG generation workflow

**Files:**
- Create: `.github/workflows/generate-snake.yml`

**Interfaces:**
- Consumes: `${{ github.repository_owner }}` and `${{ secrets.GITHUB_TOKEN }}`.
- Produces: `output/github-contribution-grid-snake.svg` and `output/github-contribution-grid-snake-dark.svg`.

- [ ] **Step 1: Add the workflow with daily, manual, and `main`-push triggers**

```yaml
name: Generate contribution snake

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:
  push:
    branches: [main]

permissions:
  contents: write
```

- [ ] **Step 2: Add the generator and publisher job**

```yaml
jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 5
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      - uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

- [ ] **Step 3: Verify the local YAML structure**

Run: `Get-Content .github/workflows/generate-snake.yml -Raw`

Expected: the three triggers, `contents: write`, both SVG output names, and `output` branch are present.

- [ ] **Step 4: Commit**

```bash
git add .github/workflows/generate-snake.yml
git commit -m "feat: generate contribution snake"
```

### Task 2: Embed the generated assets in the profile README

**Files:**
- Modify: `README.md` (`GITHUB ACTIVITY` `<picture>` block)

**Interfaces:**
- Consumes: raw SVG assets committed to the `output` branch by Task 1.
- Produces: a theme-aware animated contribution grid in the rendered profile README.

- [ ] **Step 1: Replace only the current third-party graph URLs**

```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/A-peiron/A-peiron/output/github-contribution-grid-snake-dark.svg">
  <img alt="Elliot Ji's GitHub contribution snake" src="https://raw.githubusercontent.com/A-peiron/A-peiron/output/github-contribution-grid-snake.svg">
</picture>
```

- [ ] **Step 2: Verify the README has no old activity-graph URL**

Run: `rg -n "github-readme-activity-graph|github-contribution-grid-snake" README.md`

Expected: no `github-readme-activity-graph` match and two snake asset references.

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: display contribution snake"
```

### Task 3: Publish and activate the first render

**Files:**
- No local file changes.

**Interfaces:**
- Consumes: commits from Tasks 1 and 2 on `main`.
- Produces: a completed `Generate contribution snake` run and public SVG files on `output`.

- [ ] **Step 1: Push `main`**

Run: `git push origin main`

Expected: GitHub receives the workflow and README update.

- [ ] **Step 2: Manually dispatch the workflow**

Run: `gh workflow run 'Generate contribution snake' --repo A-peiron/A-peiron`

Expected: GitHub acknowledges the manual dispatch.

- [ ] **Step 3: Verify the generated assets after the run completes**

Run: `gh run list --repo A-peiron/A-peiron --workflow 'Generate contribution snake' --limit 1`

Expected: latest run has conclusion `success`; raw URLs for both SVGs return content.

- [ ] **Step 4: Confirm the profile renders the new image**

Open: `https://github.com/A-peiron`

Expected: the `GITHUB ACTIVITY` section shows an animated contribution grid instead of the line chart.
