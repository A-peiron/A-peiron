# Profile README Copy Revision Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use `superpowers:subagent-driven-development` to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Make the profile’s technical section interest-led and update the current-status copy without changing its visual or privacy boundaries.

**Architecture:** Only `README.md` changes. The header, signature assets, education display, activity graph, and link set remain untouched; the five existing direction bullets become substantive interest statements, followed by one compact public-work line.

**Tech Stack:** GitHub-flavoured Markdown and existing GitHub-safe HTML.

## Global Constraints

- Keep the header, local signature assets, education rows, activity graph, and all existing URLs unchanged.
- Preserve the exact five direction categories and their order.
- Keep the final public-work sentence limited to AcadVex, Pose-MTMC, FPGCL, and the AICCC ’25 DOI.
- Use first-person prose, `film` rather than `TV`, and no personal website link.
- The Nippon Paint description remains anonymised and high-level.
- WorldQuant appears only as `part-time WorldQuant BRAIN Research Consultant`; omit Gold Level, quantitative-research emphasis, and personal-systems language from `CURRENTLY`.

---

### Task 1: Revise the README prose and verify content boundaries

**Files:**
- Modify: `README.md`
- Test: static Markdown/content checks for `README.md`

**Interfaces:**
- Preserves the existing `picture` markup, signature assets, public links, and activity graph.
- Produces the final public profile copy.

- [ ] **Step 1: Replace the `EXPERIENCE & INTERESTS` introduction and direction bullets**

Replace the existing short introduction and five project-led bullets with this interest-led copy:

```markdown
I keep returning to problems where a model has to become part of a usable system—where perception, structure, decision-making, and interaction have to meet.

- **Agentic Systems.** I am interested in how tool use, state, retrieval, and verification can make an application more dependable, especially when it has to work with structured information rather than answer in isolation.
- **Multimodal Perception & Edge AI.** Vision interests me most when it leaves the benchmark and meets a real environment: multiple cameras, imperfect signals, limited compute, and the need to turn what is seen into something a larger system can use.
- **Graph Intelligence.** I enjoy working with relationships as a first-class part of the problem—communities, links, group structure, and the patterns that emerge when individual observations are placed in context.
- **Multi-Agent Learning & Embodied Intelligence.** I am drawn to questions of coordination, prediction, and action: how agents learn to cooperate, how they anticipate one another, and how those ideas might extend from simulated settings toward embodied ones.
- **AI for Quantitative Research.** Quantitative research gives me another setting for systematic thinking: shaping hypotheses, working with structured data, and finding ways for AI to support a disciplined research process.

A few public traces of this work are [AcadVex](https://github.com/A-peiron/AcadVex), [Pose-MTMC](https://github.com/A-peiron/Pose-MTMC), [FPGCL](https://github.com/A-peiron/FPGCL), and my [AICCC ’25 paper](https://doi.org/10.1145/3789982.3789990).
```

- [ ] **Step 2: Replace `CURRENTLY` with the approved two-paragraph wording**

Replace the two existing paragraphs with exactly:

```markdown
I am currently interning at Nippon Paint (China) as an AI Agent Engineering Intern, working on anonymised multimodal design and recognition workflows—bringing language, vision, and generative models into a more reliable loop of coordination and review.

I also work part-time as a WorldQuant BRAIN Research Consultant. Alongside this, I keep building personal projects that explore AI applications in different contexts.
```

- [ ] **Step 3: Run content and link verification**

Run:

```powershell
git diff --check
rg -n "This summer|Gold Level|personal systems|AI Application Engineer|Selected Work|Research & Exploration|film and television|\bTV\b" README.md
rg -n "https?://" README.md
```

Expected: no whitespace errors; the first scan has no matches; the URL scan reports exactly the existing three public repository URLs, the AICCC DOI, and the two activity-graph URLs.

- [ ] **Step 4: Commit the copy revision**

```powershell
git add README.md
git commit -m "docs: expand profile interests copy"
```
