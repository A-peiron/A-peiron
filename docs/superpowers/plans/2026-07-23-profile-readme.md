# GitHub Profile README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use `superpowers:subagent-driven-development` to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create a polished, factual GitHub Profile README for Elliot Ji that establishes his AI application-engineering focus without linking an unfinished website.

**Architecture:** A root `README.md` contains concise Editorial Index content and links only to public repositories. A hand-authored monochrome header SVG provides the visual signature. The first release intentionally has no dynamic workflow, counters, or unused personal-content sections.

**Tech Stack:** GitHub-flavored Markdown and inline SVG.

## Global Constraints

- Public name: **Elliot Ji**; GitHub handle: `A-peiron`.
- Primary identity: **AI Application Engineer focused on Agentic and Intelligent Systems**.
- Education wording: `Incoming M.Sc. in Computer Science, The University of Hong Kong - From Sep 2026`; do not state a graduation date or GPA.
- Do not link to the website before a stable public deployment URL exists.
- Do not invent Reading or Screen entries.
- Do not add stars, forks, followers, visitor counters, skill-icon walls, typing animations, snakes, achievement walls, alpha formulas, strategy performance, platform code, private datasets, or client details.
- Attribute only public repositories: `AcadVex`, `Pose-MTMC`, and `MAPPO-LSTM-Trajectory`.
- Describe WorldQuant only as `WorldQuant BRAIN - Part-time Research Consultant (Gold Level)`; never imply employment by WorldQuant.

---

### Task 1: Create the profile signal and content

**Files:**
- Create: `assets/profile-header.svg`
- Create: `README.md`
- Modify: `docs/profile-readme-brief.md`

**Interfaces:**
- `README.md` embeds `assets/profile-header.svg` using `![Elliot Ji profile header](./assets/profile-header.svg)`.

- [ ] **Step 1: Add the monochrome SVG header**

Create `assets/profile-header.svg` with an accessible SVG `<title>` and a restrained black-and-white editorial layout. Include only `ELLIOT JI`, `AI APPLICATION ENGINEER`, `A-PEIRON`, and a horizontal rule; use no logos, gradients, or animation.

- [ ] **Step 2: Add the root README**

Create `README.md` with this section order:

```markdown
![Elliot Ji profile header](./assets/profile-header.svg)

AI Application Engineer focused on Agentic and Intelligent Systems.

## Focus
## Selected Work
## Research & Exploration
## Now
```

Populate it with public-safe summaries of AcadVex, Pose-MTMC, and MAPPO-LSTM-Trajectory; one AICCC '25 / DOI paper line; the Hong Kong and Shanghai education signal; and the safe WorldQuant role wording. Do not include a website URL, a personal photo, contact details, or Reading/Screen placeholders.

- [ ] **Step 3: Align the brief with the first-release scope**

Update `docs/profile-readme-brief.md` to state that Reading and Screen sections are deferred until real selections are provided, rather than leaving empty public sections.

- [ ] **Step 4: Validate Markdown and SVG locally**

Run:

```powershell
git diff --check
Select-String -Path README.md -Pattern 'http|https'
[xml](Get-Content assets/profile-header.svg -Raw) | Out-Null
```

Expected: no whitespace errors, only public repository/DOI URLs, and no XML parse error.

- [ ] **Step 5: Commit the profile content**

```powershell
git add README.md assets/profile-header.svg docs/profile-readme-brief.md
git commit -m "feat: add editorial GitHub profile"
```

### Task 2: Review and publish the static Profile README

**Files:**
- Review: `README.md`
- Review: `assets/profile-header.svg`

- [ ] **Step 1: Review factual and privacy constraints**

Confirm every project link is public; the README has no website URL, graduation date, GPA, contact details, sensitive internship details, WorldQuant strategy information, or invented personal preferences.

- [ ] **Step 2: Verify repository state**

Run:

```powershell
git status -sb
git log --oneline -3
```

Expected: intended commits only and no untracked build artifacts.

- [ ] **Step 3: Publish after authenticated remote access is available**

Run:

```powershell
git push -u origin main
```

Expected: `README.md` renders on `https://github.com/A-peiron` as a concise static profile card.
