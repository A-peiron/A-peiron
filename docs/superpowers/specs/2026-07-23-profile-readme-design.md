# GitHub Profile README Design

## Purpose

Create a concise, personal GitHub profile README for Elliot Ji. It should introduce a real person and their evolving interests, rather than imitate a resume, a project catalogue, or an AI product landing page.

The profile README is independent of the personal website. It must not link to a website until a deployed URL exists.

## Voice and visual direction

- English-first copy, with the Chinese name `季骏` beside `Elliot Ji`.
- Quiet editorial technology style: black and white, careful whitespace, thin rules, and no decorative AI diagrams.
- The headline is the visual anchor: `Where perception becomes understanding, and understanding becomes action.`
- The name appears once, below the headline and above the factual index. It is modestly larger than body labels but does not compete with the headline.
- Render the name as a local, theme-aware static title image using refined serif typography. All remaining content stays as selectable GitHub Markdown text.
- No cyberpunk treatment, neon, generic illustrations, skill charts, badges, counters, follower/star displays, typing effects, snakes, or achievement walls.

GitHub Markdown does not provide reliable custom font control. Local images are supported and can be selected by theme through a `picture` element; SVG scripting and animation are not used.

## Content architecture

The README has one editorial header, two factual index rows, three body sections, and one restrained live activity image.

### Header

1. Headline.
2. `Elliot Ji · 季骏` title image.
3. `EXPLORATIONS` row:
   `Agentic systems · multimodal perception · graph intelligence · multi-agent learning · embodied intelligence · quantitative research`
4. `BACKGROUND` row, formatted as two independent resume-like lines:
   - `M.Sc. in Computer Science, The University of Hong Kong` — `SEP 2026 — PRESENT`
   - `B.Eng. in Computer Science and Technology, Shanghai University` — `SEP 2022 — JUN 2026`

No professional position belongs in the header.

### About

Use a personal, grounded paragraph covering philosophy, literary fiction, history, training, meditation, solo travel, student leadership, and campus hosting. It should communicate personality without listing authors, private hobbies, or unsupported claims.

### Experience & Interests

Use one short paragraph connecting prior work in edge vision, multi-camera tracking, graph-and-agent applications, and multi-agent learning to the recurring interest in systems that perceive, reason, and act. Link only public work within the sentence:

- `AcadVex`
- `Pose-MTMC`
- `FPGCL`
- the AICCC '25 DOI paper

Do not create project cards, rankings, outcomes, or a standalone project section.

### Now

Use one short, anonymized paragraph:

- Elliot is a summer `AI Agent Engineering Intern` at Nippon Paint (China).
- The work concerns multimodal design and recognition workflows, coordinating language, vision, and generative models with review steps.
- Elliot is also a part-time WorldQuant BRAIN Research Consultant and is exploring agentic workflows for quantitative research and personal systems.

Do not publish company data, model configurations, prompts, internal APIs, sample assets, business metrics, customer data, alpha expressions, strategies, performance data, or private repository names.

### Activity

Place one low-key, live GitHub public-activity graph after the prose. It is the only dynamic component. It must show no visitor count, stars, followers, trophies, contribution snake, or unrelated metric panels.

## Asset and implementation constraints

- Keep profile-specific assets in `assets/` and reference them relatively from `README.md`.
- Use light and dark variants of the name title image through a `picture` element; include useful alt text.
- Use GitHub Markdown/HTML only; do not depend on custom CSS or JavaScript in the README.
- Keep all external links limited to the public repositories, the paper DOI, and `github-readme-activity-graph.vercel.app` for the one public-activity image.
- Keep the initial README compact: prose-led and scannable, without an embedded CV timeline.

## Verification

- Check Markdown rendering locally where possible and inspect the GitHub-rendered result after publishing.
- Verify light and dark title-image selection, alt text, relative asset paths, public repository links, and the paper DOI.
- Scan the final copy for company-sensitive details, unverified performance claims, investment claims, and unsupported project status claims.
- Confirm the activity image renders without introducing additional dashboard-like widgets.
