# Linear Principles

An [Agent Skill](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) that teaches Claude how Linear thinks about **UI, UX, and product** — and applies it when designing, building, or reviewing interfaces and product decisions.

The throughline: design is product judgment, not decoration, and it only works when backed by structure — opinionated defaults, near-zero latency, trained quality, and small teams that own problems end to end.

## Structure

```
linearprincipals/
├── README.md
├── .claude-plugin/
│   └── plugin.json
└── skills/
    └── linear-design-principles/
        ├── SKILL.md                  # Overview + the core principles (loaded on trigger)
        ├── references/
        │   ├── ui-ux-craft.md        # The 10 Linear blog posts and their lessons
        │   ├── operating-model.md    # Org, decisions, speed-as-architecture, the Method, hiring
        │   └── sources.md            # Citations and sourcing caveats
        └── evals/
            └── evals.json            # Realistic evaluation scenarios
```

Only skill metadata is loaded at startup. The full `SKILL.md` is read when the skill triggers, and reference files load only when needed — progressive disclosure keeps the context window clean.

## What it covers

- **UI/UX craft** — calm-but-dense hierarchy, pruning visual noise, redesign strategy and design debt, why "output isn't design," designing for the AI age, quality rituals, settings, dashboards.
- **Product judgment** — design for someone specific, opinionated defaults over flexibility, plain language, interpreting requests vs. transcribing them, problem-before-solution.
- **Operating model** — no handoffs, taste over experiments, speed as architecture, the Linear Method, hiring via work trials.

## Sources

Built from Linear's own writing (`linear.app/now`, `linear.app/method`), founder interviews (Karri Saarinen, Nan Yu, Jori Lallo, Tuomas Artman), and third-party technical breakdowns. Full list with caveats in [`skills/linear-design-principles/references/sources.md`](skills/linear-design-principles/references/sources.md).

## Format

This skill follows the [Agent Skills authoring best practices](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices) and the layout convention from [agentsbestpractices](https://github.com/tylergibbs1/agentsbestpractices).
