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

The section is interest-led rather than a project list. Open with one short paragraph about the point where perception, structure, decision-making, and interaction meet; then use five distinct, substantive direction entries. Do not force every direction into an Agent framing or merge unrelated areas merely to reduce the list.

1. **Agentic Systems** — explain the interest in tool use, state, retrieval, and verification as ways to make applications more dependable around structured information.
2. **Multimodal Perception & Edge AI** — explain the interest in vision under practical constraints: multiple cameras, imperfect signals, limited compute, and outputs a larger system can use.
3. **Graph Intelligence** — explain the interest in communities, links, group structure, and relationship patterns. Do not claim that this work is inherently agentic.
4. **Multi-Agent Learning & Embodied Intelligence** — explain the interest in coordination, prediction, action, cooperation, and the connection between simulated and embodied settings.
5. **AI for Quantitative Research** — explain the interest in systematic research, structured data, and AI support for disciplined research processes, without publishing WorldQuant platform material, alpha expressions, strategies, or performance.

End with one unobtrusive sentence linking the public evidence: [AcadVex](https://github.com/A-peiron/AcadVex), [Pose-MTMC](https://github.com/A-peiron/Pose-MTMC), [FPGCL](https://github.com/A-peiron/FPGCL), and the [AICCC ’25 paper](https://doi.org/10.1145/3789982.3789990). There is no standalone project section.

Do not describe the thesis itself as open source. Its algorithmic innovation is represented by FPGCL and its engineering application by AcadVex.

### Currently

Use two short first-person paragraphs rather than a chronology:

> I am currently interning at Nippon Paint (China) as an AI Agent Engineering Intern, working on anonymised multimodal design and recognition workflows—bringing language, vision, and generative models into a more reliable loop of coordination and review.

> I also work part-time as a WorldQuant BRAIN Research Consultant. Alongside this, I keep building personal projects that explore AI applications in different contexts.

Do not display the Gold Level designation, emphasise quantitative research here, or refer to personal systems.

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
