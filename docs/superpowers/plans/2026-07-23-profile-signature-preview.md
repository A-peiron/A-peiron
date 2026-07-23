# Profile Signature Simplification and Preview Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use `superpowers:subagent-driven-development` to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the decorative profile-name SVG with a compact, ordinary-font signature and provide a local GitHub-style rendering preview.

**Architecture:** The committed profile remains GitHub Markdown plus two static theme-aware SVG name assets. A temporary, ignored HTML page renders the final README content in GitHub-like light and dark panels solely for visual review; it is not part of the profile repository.

**Tech Stack:** GitHub-flavoured Markdown, static SVG, HTML, and CSS.

## Global Constraints

- Keep the approved README copy, header order, background rows, link set, and activity graph unchanged.
- Keep local light/dark SVG assets, but make them transparent, ordinary sans-serif, without lines or decoration, and display them at 240px wide.
- Do not add a website link, a dashboard component, custom GitHub CSS, JavaScript to the README, or new external dependencies.
- The preview exists only below ignored `.superpowers/` and must not be committed.

---

### Task 1: Simplify the signature assets and README usage

**Files:**
- Modify: `assets/elliot-ji-light.svg`
- Modify: `assets/elliot-ji-dark.svg`
- Modify: `README.md`
- Modify: `docs/profile-readme-brief.md`

**Interfaces:**
- `README.md` continues to load `./assets/elliot-ji-light.svg` and `./assets/elliot-ji-dark.svg` through the existing `picture` element.
- Each asset is a transparent `280 × 48` static SVG with title `Elliot Ji · 季骏`.

- [ ] **Step 1: Replace the light signature SVG with the compact ordinary-font variant**

Set `assets/elliot-ji-light.svg` to:

```svg
<svg xmlns="http://www.w3.org/2000/svg" width="280" height="48" viewBox="0 0 280 48" role="img" aria-labelledby="title">
  <title id="title">Elliot Ji · 季骏</title>
  <text x="0" y="31" fill="#1f2328" font-family="Arial, Helvetica, sans-serif" font-size="24" font-weight="400">Elliot Ji</text>
  <text x="101" y="31" fill="#1f2328" font-family="Arial, Helvetica, sans-serif" font-size="18" font-weight="400">· 季骏</text>
</svg>
```

- [ ] **Step 2: Replace the dark signature SVG with the matching compact variant**

Set `assets/elliot-ji-dark.svg` to the same geometry and typography as the light asset, replacing only the text fill with `#f0f6fc`.

- [ ] **Step 3: Shrink the rendered README name and align the maintenance brief**

In `README.md`, change only the signature image width from `520` to `240`. In `docs/profile-readme-brief.md`, document that the name asset is compact, transparent, ordinary sans-serif, without a rule or decorative treatment.

- [ ] **Step 4: Validate the committed profile files**

Run:

```powershell
[xml](Get-Content assets/elliot-ji-light.svg -Raw) | Out-Null
[xml](Get-Content assets/elliot-ji-dark.svg -Raw) | Out-Null
git diff --check
rg -n "Georgia|Songti|SimSun|<rect|<line|width=\"520\"" assets README.md
```

Expected: both SVGs parse; no whitespace errors; the final scan has no matches.

- [ ] **Step 5: Commit the signature task**

```powershell
git add assets/elliot-ji-light.svg assets/elliot-ji-dark.svg README.md docs/profile-readme-brief.md
git commit -m "style: simplify profile signature"
```

### Task 2: Create and inspect the temporary GitHub-style preview

**Files:**
- Create: `.superpowers/profile-preview/index.html` (ignored; do not commit)

**Interfaces:**
- The preview page reads the final visible profile content and loads `../../assets/elliot-ji-light.svg` and `../../assets/elliot-ji-dark.svg` relative to its own path.
- The local preview server serves the worktree root on port `62700`.

- [ ] **Step 1: Create a static two-theme preview page**

Create `.superpowers/profile-preview/index.html` with two responsive panels labelled `GitHub light theme` and `GitHub dark theme`. Each panel must show the headline, compact matching signature asset, explorations/background rows, ABOUT, expanded EXPERIENCE & INTERESTS, CURRENTLY, and an understated activity-graph placeholder. Use CSS only inside this ignored preview page; do not copy that CSS into the README.

- [ ] **Step 2: Serve the preview locally and inspect it**

Run the server in the background:

```powershell
Start-Process -WindowStyle Hidden -FilePath py -ArgumentList '-m','http.server','62700','--directory','C:\Users\lenovo\Desktop\personal-brand\.worktrees\A-peiron-profile-readme'
```

Open:

```text
http://127.0.0.1:62700/.superpowers/profile-preview/index.html
```

Expected: both panels load their respective compact name assets, and no asset path returns a browser error.

- [ ] **Step 3: Confirm preview isolation**

Run:

```powershell
git check-ignore .superpowers/profile-preview/index.html
git status --short
```

Expected: the preview path is ignored and no preview file is staged or committed.
