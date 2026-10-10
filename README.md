# Project Starter Kit — an AI-first methodology for building software projects

**Two skills + one role prompt** that make an AI build projects in a staged, checkable way.

Two modes:

- **Start a project** — from one sentence of idea to running, shippable software;
- **Review a project** — audit existing code and report risks without touching it.

> **This documentation is written for the AI, not for humans to study.**
> You describe the idea (what it does, who uses it, where it runs); the AI executes — checklists, structure, code.
> **You do not need to know any programming language.**
> The AI works under a hard discipline: **talk less, build more** — deliver complete runnable files and commands, never restate these checklists, never pad with "summary / outlook / further optimization" filler.

---

## Why it exists

Projects started with AI usually fail for non-coding reasons:

1. **Not knowing what to do first** — trying to build the whole product in one go;
2. **No standard for structure and layering** — everything has rotted by week three;
3. **The AI says "done" but nothing was ever actually run**;
4. **Technology chosen because "the tutorial used it"** — and impossible to replace later.

This kit turns those four into **executable checklists, exit criteria and acceptance methods**.

---

## What's inside

```
arch-blueprint/                    the main skill
│   ├── SKILL.md                     routing + hard rules + output discipline
│   ├── references/                  20+ topic references (see REFERENCE-INDEX.en.md)
│   │   ├── roadmap.md               8 phases, artifacts, exit criteria, scale-fitting
│   │   ├── scoping.md               real requirements, prioritisation, estimation
│   │   ├── tech-line.md             constraints, one-way vs two-way doors, spikes
│   │   ├── layering.md              5 layers, boundaries, dependency direction
│   │   ├── project-types.md         14 project types + their specific pitfalls
│   │   ├── shipping.md              milestones, vertical slices, launch checklist, ops
│   │   ├── security-checklist.md / testing-strategy.md / failure-design.md / …
│   │   └── team-brief.md            briefing an expert team (shared standard + independence)
│   └── assets/                      blueprint template + 2 filled example blueprints
├── software-architect/              the architect skill
│   ├── SKILL.md                     identity, mission, rules, outputs
│   ├── references/                  ADR template, review checklist, trade-off templates
│   └── assets/expert-definition.md  host-agnostic role prompt ("Project Navigator")
├── REFERENCE-INDEX.en.md            English one-liners for every reference file
├── README.md / README.zh-CN.md      English (primary) / Chinese
├── NOTICE                           copyright & citation notes
└── LICENSE                          MIT
```

The **8-phase mainline** is: framing → tech line → architecture → contracts → engineering baseline → implementation → delivery → evolution.
Everything else in the kit exists to make one of those phases **produce a checkable artifact**.

---

## How to use it

### 1. Install the skills

Copy `arch-blueprint/` and `software-architect/` into your skills directory (DSH / Claude `skills`), then **start a new session** (skills are loaded at session start).

Installing only one is fine: each is self-contained for its own use, and both note the degraded-but-usable path.

### 2. Trigger it

The descriptions contain **bilingual trigger phrases**, so plain language works:

| Goal | Say |
|---|---|
| Start a project | “I have an idea for X — help me start the project with arch-blueprint” |
| Same, in Chinese | 「我有个想法想做 X，用 arch-blueprint 帮我起项目」 |
| Tech selection | “choose a tech stack, give me two options with trade-offs” |
| Review / audit | “audit this project — **report only, do not modify**” |
| Architecture review | “review my architecture”, “should we use microservices?” |

Explicit invocation (where supported): `/arch-blueprint`, `/software-architect`.

### 3. The role prompt (optional)

`software-architect/assets/expert-definition.md` §2 contains a **host-agnostic persona** (Project Navigator — 项目领航员). Hand that text to your AI and let it generate the configuration for your own host (custom expert, agent preset, system prompt):

> “Turn this prompt into a role in my environment (custom expert / agent preset / system prompt). Name it `Project Navigator`. **Do not introduce plugins I don't have, and do not copy paths from someone else's machine.**”

**This repository contains no machine-specific configuration** — no local paths, no host-specific registration files.

### 4. What a good first answer looks like

Asked to start a project, the AI should: ask ≤4 clarifying questions → give **two candidate decompositions with their costs** → produce the blueprint (subsystem table, dependency graph, data model, quality attributes, an explicit **“not doing now” list**) → name the **M1 milestone and its exit criteria**.
It should **not**: write code immediately, give only one option, output methodology prose without files, or suggest microservices / monorepo for a solo project.

---

## Verified — what we actually measured

We ran an A/B experiment on a real Electron + TypeScript module (846 lines, frozen revision, two isolated groups):

| Group | Result |
|---|---|
| **Single reviewer** (skill + role) | 10 located risks, consistent format (location / why / minimal fix), **no over-engineering suggestions** |
| **3-member expert team** (architecture + security + quality) | 18 deduplicated findings, **8 of them missed by the single reviewer** (2 high severity) |
| Objective baseline | `eslint` clean, **149 tests passing** |

**And still: 3 blocking defects** — one of which caused `loadValue` to **delete user data rows on read**.

**Conclusion: this kit raises the probability of catching problems and of not skipping steps. It does not guarantee quality.**
Quality still depends on: whether the requirements are real, whether anything was actually verified, and whether someone keeps maintaining it.

---

## Honest limits

- **No domain knowledge** — medical, financial, industrial, legal, game balancing: the AI will flag compliance/performance budgets, not replace an expert.
- **No framework manuals, on purpose** — framework details age fast; the AI is instructed to consult official docs.
- **No verification** — real-device compatibility, real performance numbers, platform review policies: only you (or testing) can establish those.
- **Scope**: one person / small team. Multi-team governance, SRE practice and formal compliance audits are out of scope.
- **It is a workflow, not product or business advice.**

---

## License & credits

- This repository's own documentation: **MIT** (see `LICENSE`, copyright HAIJAIWE).
- All role text and documentation in this repository is **original work**.
- Standards and projects named throughout (Clean Architecture, DDD, C4, arc42, ADR, 12-Factor, ISO 25010, OWASP, AutoGen, Test Pyramid, …) are **cited for reference only**; all rights belong to their owners.

## Maintenance self-check

After editing this repo, verify four things (no scripts needed):

1. **Reference integrity** — every `references/...` / `assets/...` path mentioned in a `SKILL.md` actually exists;
2. **No orphans** — every reference/asset file is mentioned in its `SKILL.md` (otherwise the AI cannot find it);
3. **Consistent terminology** — one concept, one name;
4. **Anchors intact** — the 8-phase table, the hard rules, and the reference index are the **routing skeleton**; without them the skill "knows but cannot find".

**Single source of truth for the persona**: `software-architect/SKILL.md`; keep `assets/expert-definition.md` §2 in sync.

## Before publishing

If you assembled this kit from a real project repository, do **not** publish: internal review/audit reports, **unfixed vulnerability lists**, your host's config file (contains absolute paths), or any credentials / `.env`.
