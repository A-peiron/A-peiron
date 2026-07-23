# GitHub Profile README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use `superpowers:subagent-driven-development` to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the initial template-like profile README with Elliot Ji’s approved, compact personal introduction.

**Architecture:** The root `README.md` is native GitHub Markdown and minimal HTML, arranged as one editorial header, three prose-led sections, and one activity graph. Two local SVG assets supply only the theme-aware name treatment; no custom CSS, JavaScript, or dashboard components are used.

**Tech Stack:** GitHub-flavoured Markdown, minimal GitHub-safe HTML, and static SVG.

## Global Constraints

- Public name: `Elliot Ji · 季骏`; GitHub username: `A-peiron`.
- Use the approved headline: `Where perception becomes understanding, and understanding becomes action.`
- Header order: headline, name, `EXPLORATIONS`, then education-only `BACKGROUND`.
- Education rows: HKU `SEP 2026 — PRESENT`; Shanghai University `SEP 2022 — JUN 2026`.
- Keep exactly three body sections: `ABOUT`, `EXPERIENCE & INTERESTS`, and `CURRENTLY`.
- Use the word `film`, never `TV` or `film and television`.
- Keep the five technical directions distinct: Agentic Systems; Multimodal Perception & Edge AI; Graph Intelligence; Multi-Agent Learning & Embodied Intelligence; AI for Quantitative Research.
- Do not link to an unfinished website, include a CV timeline, use project cards, report stars/followers/metrics, or add badges, counters, skill-icon walls, typing effects, snakes, trophies, or generic AI visuals.
- Do not publish Nippon Paint internal details or WorldQuant alpha expressions, strategies, performance, platform material, or private repository names.
- Link only public repositories, the AICCC ’25 DOI, and the one `github-readme-activity-graph.vercel.app` graph image.

---

## File Structure

- `README.md` — public profile content, links, and activity graph.
- `assets/elliot-ji-light.svg` — black typography for GitHub light mode.
- `assets/elliot-ji-dark.svg` — white typography for GitHub dark mode.
- `docs/profile-readme-brief.md` — concise maintenance reference matching the approved content architecture.

### Task 1: Create the signature assets and align the brief

**Files:**
- Create: `assets/elliot-ji-light.svg`
- Create: `assets/elliot-ji-dark.svg`
- Delete: `assets/profile-header.svg`
- Modify: `docs/profile-readme-brief.md`

**Interfaces:**
- Produces the relative asset paths used by the root README: `./assets/elliot-ji-light.svg` and `./assets/elliot-ji-dark.svg`.
- Both SVG files must be static and expose the accessible title `Elliot Ji · 季骏`.

- [ ] **Step 1: Replace the old AI-role header with a light name asset**

Create `assets/elliot-ji-light.svg` with a white background, black refined serif name, Chinese name, and one thin black rule. Use no role title, handle, abstract graphic, gradient, script, or animation. The central content must follow this shape:

```svg
<svg xmlns="http://www.w3.org/2000/svg" width="760" height="132" viewBox="0 0 760 132" role="img" aria-labelledby="title">
  <title id="title">Elliot Ji · 季骏</title>
  <rect width="760" height="132" fill="#ffffff"/>
  <text x="0" y="63" fill="#111111" font-family="Georgia, 'Times New Roman', 'Songti SC', SimSun, serif" font-size="46" font-weight="400" letter-spacing="-0.7">Elliot Ji</text>
  <text x="228" y="63" fill="#111111" font-family="'Songti SC', SimSun, serif" font-size="28" font-weight="400">· 季骏</text>
  <line x1="0" y1="103" x2="760" y2="103" stroke="#111111" stroke-width="1"/>
</svg>
```

- [ ] **Step 2: Create the matching dark name asset**

Create `assets/elliot-ji-dark.svg` with the same dimensions, title, positions, and typography. Replace the background and text/rule colours only:

```svg
<rect width="760" height="132" fill="#0d1117"/>
<text x="0" y="63" fill="#f0f6fc" font-family="Georgia, 'Times New Roman', 'Songti SC', SimSun, serif" font-size="46" font-weight="400" letter-spacing="-0.7">Elliot Ji</text>
<text x="228" y="63" fill="#f0f6fc" font-family="'Songti SC', SimSun, serif" font-size="28" font-weight="400">· 季骏</text>
<line x1="0" y1="103" x2="760" y2="103" stroke="#f0f6fc" stroke-width="1"/>
```

- [ ] **Step 3: Replace the obsolete maintenance brief**

Rewrite `docs/profile-readme-brief.md` so it records the approved header order, the exact three body headings, the five separate direction areas, the no-website-link rule, and the single activity-graph rule. Do not retain the old “AI Application Engineer,” “Selected Work,” “Research & Exploration,” or generic `Now` structure.

- [ ] **Step 4: Validate static assets and documentation**

Run:

```powershell
[xml](Get-Content assets/elliot-ji-light.svg -Raw) | Out-Null
[xml](Get-Content assets/elliot-ji-dark.svg -Raw) | Out-Null
rg -n "AI Application Engineer|Selected Work|Research & Exploration|film and television|\bTV\b" assets docs/profile-readme-brief.md
```

Expected: both XML commands succeed and the search has no matches.

- [ ] **Step 5: Commit the standalone asset task**

```powershell
git add assets/elliot-ji-light.svg assets/elliot-ji-dark.svg assets/profile-header.svg docs/profile-readme-brief.md
git commit -m "feat: add profile signature assets"
```

### Task 2: Implement the approved profile README

**Files:**
- Modify: `README.md`
- Test: `README.md` static Markdown/link checks

**Interfaces:**
- Consumes `./assets/elliot-ji-light.svg` and `./assets/elliot-ji-dark.svg` from Task 1.
- Produces the GitHub-rendered public profile page.

- [ ] **Step 1: Replace the root README header**

Replace the existing role-first header with this GitHub-safe structure:

```markdown
## Where perception becomes understanding, and understanding becomes action.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/elliot-ji-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/elliot-ji-light.svg">
  <img alt="Elliot Ji · 季骏" src="./assets/elliot-ji-light.svg" width="520">
</picture>

<sub><strong>EXPLORATIONS</strong></sub><br>
Agentic systems · multimodal perception · graph intelligence · multi-agent learning · embodied intelligence · quantitative research

<sub><strong>BACKGROUND</strong></sub><br>
M.Sc. in Computer Science, The University of Hong Kong — <code>SEP 2026 — PRESENT</code><br>
B.Eng. in Computer Science and Technology, Shanghai University — <code>SEP 2022 — JUN 2026</code>
```

- [ ] **Step 2: Add the human `ABOUT` section**

Write a brief multi-paragraph section beginning exactly with:

```markdown
## ABOUT

I’m drawn to seeing an idea move from a question, a hunch, or an observation into something that can be tested, argued with, and made to work.
```

Continue with personal but non-expert language covering ancient Greek philosophy, modern existentialism, religion, aesthetics, origins, reason, humanism, literature about self and society, history, strength training, meditation, reflection, film, and travelling alone. End with the student-leadership/campus-hosting thought: Elliot is comfortable both organising a room and speaking in one. Do not list authors, use `TV`, mention private hobbies, or claim specialist knowledge.

- [ ] **Step 3: Add distinct direction entries in `EXPERIENCE & INTERESTS`**

Add one introductory sentence and the following five bold direction entries as Markdown bullets. Retain all five categories; do not merge Graph Intelligence, quantitative research, or embodied intelligence into unrelated areas.

```markdown
## EXPERIENCE & INTERESTS

- **Agentic Systems.** Tool-using applications and the applied graph-and-agent work in [AcadVex](https://github.com/A-peiron/AcadVex).
- **Multimodal Perception & Edge AI.** Edge vision, multi-camera tracking, and [Pose-MTMC](https://github.com/A-peiron/Pose-MTMC).
- **Graph Intelligence.** Graph learning, community mining, link prediction, and related algorithmic work; do not describe it as inherently agentic.
- **Multi-Agent Learning & Embodied Intelligence.** Cooperative learning research, the [AICCC ’25 paper](https://doi.org/10.1145/3789982.3789990), and [FPGCL](https://github.com/A-peiron/FPGCL).
- **AI for Quantitative Research.** Systematic quantitative research, research automation, and agent-assisted financial intelligence, without platform material or performance claims.
```

- [ ] **Step 4: Add the `CURRENTLY` section and one activity graph**

Add two short paragraphs. The first must identify Elliot as a summer AI Agent Engineering Intern at Nippon Paint (China) and describe anonymised multimodal design and recognition work only at the safe high level approved in the design. The second must state WorldQuant BRAIN Research Consultant, Gold Level, and describe ongoing agentic work for quantitative research and personal systems without naming private repositories or calling work incomplete.

Finish with one low-key theme-aware activity graph:

```markdown
## GITHUB ACTIVITY

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=A-peiron&bg_color=0d1117&color=f0f6fc&line=8b949e&point=f0f6fc&area=true&hide_border=true">
  <img alt="Elliot Ji’s recent GitHub activity" src="https://github-readme-activity-graph.vercel.app/graph?username=A-peiron&bg_color=ffffff&color=24292f&line=57606a&point=24292f&area=true&hide_border=true">
</picture>
```

- [ ] **Step 5: Run content-safety and structural verification**

Run:

```powershell
git diff --check
rg -n "AI Application Engineer|Selected Work|Research & Exploration|\bNOW\b|film and television|\bTV\b|website|star|follower|visitor|snake|trophy" README.md
rg -n "https?://" README.md
```

Expected: no whitespace errors; no old sections, forbidden visual widgets, or website link; URLs are limited to `github.com/A-peiron`, the AICCC DOI, and `github-readme-activity-graph.vercel.app`.

- [ ] **Step 6: Commit the README task**

```powershell
git add README.md
git commit -m "feat: add personal GitHub profile README"
```

### Task 3: Review the rendered-profile readiness

**Files:**
- Review: `README.md`
- Review: `assets/elliot-ji-light.svg`
- Review: `assets/elliot-ji-dark.svg`

**Interfaces:**
- Consumes the completed repository state from Tasks 1 and 2.
- Produces a review-ready feature branch; publishing is deliberately separate because the GitHub CLI token previously failed validation in this environment.

- [ ] **Step 1: Inspect repository state and intended diff**

Run:

```powershell
git status --short
git log --oneline -5
git diff main...HEAD --check
git diff --stat main...HEAD
```

Expected: only profile README assets, profile documentation, and README-related changes exist on the feature branch; no whitespace error appears.

- [ ] **Step 2: Perform the factual/privacy review**

Confirm all of the following directly in the files:

```text
- The name is Elliot Ji · 季骏 and the old AI Application Engineer claim is absent.
- Header background lists education only.
- The body has exactly ABOUT, EXPERIENCE & INTERESTS, and CURRENTLY before GITHUB ACTIVITY.
- There are five distinct direction entries.
- Nippon Paint and WorldQuant content remains anonymised and public-safe.
- There is no website URL, no WorldQuant strategy/performance claim, no EI-indexing claim, and no private project name.
- The activity graph is the only dynamic image.
```

- [ ] **Step 3: Report readiness without retrying remote authentication**

Do not repeatedly run `gh auth login` or push. Report the branch, commits, verification output, and whether the user wants to inspect the local README or proceed to the normal merge/publish handoff.
