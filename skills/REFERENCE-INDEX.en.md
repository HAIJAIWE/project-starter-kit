# Reference Index (English)

One line per file, so a non-Chinese reader can see the whole map. The files themselves are currently written in Chinese — the AI reads them regardless of your language, and all **instructions** are language-neutral.

## `arch-blueprint` — start and review projects

| File | What it covers |
|---|---|
| `SKILL.md` | Routing + 8-phase mainline + hard rules (layers, dependency direction, contracts first, one phase at a time, no pattern for its own sake, non-negotiable floor) + **output discipline** (talk less, build more) + reference index |
| `references/roadmap.md` | Phase-by-phase detail: actions, artifacts, exit criteria, common mistakes; scale-fitting table (toy → large) |
| `references/scoping.md` | How to dig out **real** scenarios, prioritise features (value × cost), estimate effort (three-point + personal multiplier), control scope changes |
| `references/tech-line.md` | Constraints first, one-way vs two-way doors, time-boxed spikes, nine selection criteria, anti-patterns, how to stay replaceable |
| `references/layering.md` | The 5 layers defined, boundary tests, dependency rule, same-word-different-meaning traps, layer × testing × deployment, multi-system products, circular dependency detection |
| `references/project-types.md` | 14 project types: candidate subsystems, what to trim, type-specific pitfalls and compliance red lines; deployment form → decomposition; sensible default stacks |
| `references/patterns.md` | Architecture styles (layered, vertical slice, hexagonal, EDA, CQRS, microkernel, serverless, microservices) with **triggers and costs**; module communication options; code organisation; agent orchestration patterns; authoritative sources |
| `references/data-and-quality.md` | Data modelling (who writes which table = boundary), quality attributes as **numbers**, the "discovered only in production" checklist |
| `references/engineering-baseline.md` | The 16-item engineering baseline (version control, secrets separation, dependency locking, tests, CI, migrations, rollback, backups…), graded by project size |
| `references/dev-environment.md` | Reproducible environments: pinned runtimes, one-command start, seed data, cross-platform traps |
| `references/code-craft.md` | Naming, functions, comments, types vs runtime validation, pre-commit self-review |
| `references/api-contract.md` | Function- and network-level contracts, **input validation at the trust boundary**, HTTP design, versioning |
| `references/testing-strategy.md` | What to test and what not to, fakes vs stubs vs mocks, how to use coverage, minimum viable test set |
| `references/failure-design.md` | Error classification, timeouts, retries, idempotency, degradation, concurrency and transaction boundaries, partial failure |
| `references/security-checklist.md` | Authn vs authz (object ownership!), injection, XSS/CSRF/CORS, uploads, secrets, dependencies, privacy, extra items for AI projects |
| `references/perf-and-debug.md` | Measure first, common bottlenecks, caching and its failure modes, performance budgets, debugging flow, observability |
| `references/release-and-evolution.md` | Git discipline, semantic versioning, progressive delivery (flags, canary), data migration (expand–contract), refactoring and when to rewrite |
| `references/i18n-and-a11y.md` | Internationalisation and accessibility: trigger conditions, minimal practices, WCAG basics |
| `references/shipping.md` | **Landing a project**: milestones M1–M4 with exit criteria, deliverable vertical slices, integration and UAT, launch resources and compliance (domains, filing, quotas, payment, store review, privacy policy), post-launch operations, the seven causes of half-finished projects |
| `references/ai-code-acceptance.md` | The eight recurring failure modes of AI-written code (hallucinated dependencies, fake tests, leaked secrets, silent interface changes…) and how to accept it |
| `references/prompts.md` | 12 copy-paste prompt templates for steering the AI |
| `references/acceptance.md` | Blueprint scorecard, definition of done, five code quality gates, upgrade signals |
| `references/team-brief.md` | How to brief an expert team: shared standard + independent analysis, synthesis rules, when **not** to use a team |
| `assets/blueprint-template.md` | Fill-in-the-blank blueprint (14 sections) |
| `assets/examples/02-expense-tracker.md` | Worked example: personal expense tracker (real user data, backup required) |
| `assets/examples/03-cli-tool.md` | Worked example: CLI tool (toy scale, demonstrates "shrink scope, not standards") |

## `software-architect` — technical decisions and review

| File | What it covers |
|---|---|
| `SKILL.md` | Identity, five-part mission, seven rules (incl. reversibility, complexity conservation, right-sizing), citation discipline, division of labour with `arch-blueprint`, hard output requirements (two options + failure modes + ADR + numbers), when to **refuse** to answer, communication style |
| `references/adr-template.md` | ADR template, when to write one, how to store and number them, the common ways people write them wrong |
| `references/review-checklist.md` | Dependency-direction checks, fitness functions for CI, **how to sample** a large codebase, 21 review questions, fixed four-column output format, and a ready **health-check report template** |
| `references/templates.md` | Weighted technology selection matrix (and the rules for using it honestly), capacity and cost estimation (with corrected peak assumptions), change-impact and boundary evaluation tables |
| `assets/expert-definition.md` | Host-agnostic role prompt: name/division/description + full persona + how to land it in any host |
