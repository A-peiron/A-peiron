# GitHub Profile README Design

## Purpose

Create a compact, personal GitHub profile README for Elliot Ji / 季骏. It is a quiet introduction to the person behind the account—not a resume, project catalogue, AI product page, or substitute for the future personal website.

The profile README must not link to a personal website until one has been deployed.

## Voice and visual direction

- English-first copy with the Chinese name `季骏` beside `Elliot Ji`.
- Quiet editorial technology: black and white, careful whitespace, thin rules, and a small amount of purposeful movement.
- The headline is the anchor: `Where perception becomes understanding, and understanding becomes action.`
- The name appears once below the headline and before the factual index. It is larger than a body label but never competes with the headline.
- Render only the name as a local, theme-aware static title image with refined serif typography. Everything else remains selectable Markdown text.
- No cyberpunk treatment, neon, generic AI imagery, skill charts, badge walls, counters, follower/star displays, typing effects, snakes, project cards, or achievement walls.

GitHub Markdown does not provide reliable custom-font control. Local images can be selected by theme through a `picture` element; SVG scripts and animation are out of scope.

## Content architecture

The README has one editorial header, two factual index rows, three prose-led sections, and one discreet live GitHub activity image.

### Header

1. Headline.
2. `Elliot Ji · 季骏` title image.
3. `EXPLORATIONS` row:
   `Agentic systems · multimodal perception · graph intelligence · multi-agent learning · embodied intelligence · quantitative research`
4. `BACKGROUND` row, formatted as independent resume-like lines:
   - `M.Sc. in Computer Science, The University of Hong Kong` — `SEP 2026 — PRESENT`
   - `B.Eng. in Computer Science and Technology, Shanghai University` — `SEP 2022 — JUN 2026`

No professional position appears in the header.

### About

Open with a short, human introduction before moving to interests. The final copy should use this direction:

> I’m drawn to seeing an idea move from a question, a hunch, or an observation into something that can be tested, argued with, and made to work.

The rest of the section presents personal interests with warmth but without treating Elliot as an expert or listing favourite authors. It should include:

- Ancient Greek philosophy, modern existentialism, and broader questions of religion, aesthetics, origins, reason, and humanism.
- Literature that wrestles with the self and society, history, and other adjacent interests.
- Strength training, meditation, reflection, film, and travelling alone.
- Student leadership and campus hosting, framed as experience that made Elliot comfortable both organising a room and speaking in one.

Exclude private hobbies and claims of deep academic expertise in these fields.

### Experience & interests

Introduce the work in a short paragraph, then use five distinct, compact direction entries. Do not force every direction into an Agent framing or merge unrelated areas merely to reduce the list. Each direction may attach a public link naturally; there is no separate projects section.

1. **Agentic Systems** — tool-using applications and the applied graph-and-agent work in [AcadVex](https://github.com/A-peiron/AcadVex).
2. **Multimodal Perception & Edge AI** — edge vision, multi-camera tracking, and [Pose-MTMC](https://github.com/A-peiron/Pose-MTMC).
3. **Graph Intelligence** — graph learning, community mining, link prediction, and related algorithmic work. Do not claim that this work is inherently agentic.
4. **Multi-Agent Learning & Embodied Intelligence** — cooperative learning research, the [AICCC ’25 paper](https://doi.org/10.1145/3789982.3789990), and [FPGCL](https://github.com/A-peiron/FPGCL).
5. **AI for Quantitative Research** — systematic quantitative research, research automation, and agent-assisted financial intelligence, without publishing WorldQuant platform material, alpha expressions, strategies, or performance.

Do not describe the thesis itself as open source. Its algorithmic innovation is represented by FPGCL and its engineering application by AcadVex.

### Currently

Use two short paragraphs rather than a chronology:

- **Nippon Paint (China):** Elliot is a summer AI Agent Engineering Intern, working on anonymised multimodal design and recognition workflows. At a safe high level, this includes coordinating language, vision, and generative models with review steps, and preparing multimodal RAG for SKU-recognition scenarios.
- **WorldQuant BRAIN and independent work:** Elliot is a part-time WorldQuant BRAIN Research Consultant, Gold Level, and continues building towards agentic work for quantitative research and personal systems.

Do not publish internal data, model configurations, prompts, APIs, sample assets, business metrics, customer data, alpha expressions, strategies, performance data, private repository names, or claims about project completion.

### Activity

Place one low-key live GitHub public-activity graph after the prose. It is the only dynamic component. It must show no visitor count, stars, followers, trophies, contribution snake, or unrelated metric panels.

## Asset and implementation constraints

- Keep profile-specific assets in `assets/` and reference them relatively from `README.md`.
- Use light and dark variants of the name title image through a `picture` element with useful alt text.
- Use GitHub Markdown/HTML only; do not depend on custom CSS or JavaScript in the README.
- Keep external links limited to public repositories, the paper DOI, and `github-readme-activity-graph.vercel.app` for the public-activity image.
- Keep the initial README prose-led and scannable, without a CV timeline or a website link.

## Verification

- Inspect the GitHub-rendered result after publishing, including both light and dark themes.
- Verify title-image selection, alt text, relative asset paths, public repository links, and the paper DOI.
- Scan final copy for company-sensitive details, unverified performance or EI-indexing claims, investment claims, and unsupported project-status claims.
- Confirm the activity image renders without adding a dashboard-like widget.
