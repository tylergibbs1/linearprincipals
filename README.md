# Linear Principles

How Linear thinks about UI, UX, and product — design as judgment, not decoration. Distilled from Linear's own writing, founder interviews, and technical breakdowns into an installable agent skill.

## Install

```
npx skills add tylergibbs1/linearprincipals
```

Or clone directly into your skills directory:

```
git clone https://github.com/tylergibbs1/linearprincipals.git \
  ~/.claude/skills/linearprincipals
```

## Skills

### [linear-design-principles](skills/linear-design-principles/SKILL.md)

**Design and review like Linear.** Ten core principles — opinionated defaults, calm-but-dense hierarchy, speed as architecture, quality as a trained habit — plus a copy-paste review checklist, the operating model behind them, and references to the source material.

| You'll learn | From |
|---|---|
| Design for someone specific; be opinionated over flexible | Figma "10 rules for crafting products" (Karri Saarinen) |
| Calm but dense — make visual hierarchy do the ranking | "A calmer interface for a product in motion" |
| Problem before solution; "output isn't design" | "Design is more than code" + "Output isn't design" |
| Speed is architecture and input design, not polish | "How's Linear so fast? A technical breakdown" |
| Quality is a trained habit and a hiring filter | "Quality Wednesdays" + "Why is quality so rare?" |
| Build the workbench, not the chatbox, for AI features | "Design for the AI age" |
| Interpret requests, don't transcribe them | "Building what customers need" |
| Redesign strategy and paying down design debt | "A design reset" + "How we redesigned the Linear UI" |
| No handoffs, taste over experiments, the Linear Method | Lenny's Newsletter Q&A + linear.app/method |

## Usage

Describe a design or product problem in plain language — the skill triggers on its own:

```
You:    Our settings page has grown to 40 toggles and feels like a junk drawer.
        Should we just hide the advanced ones behind a "Pro" tab?

Claude: [linear-design-principles triggers]
        Separate two things first — genuine preferences vs. unresolved product
        decisions you've parked as toggles. Settings aren't a design failure, but a
        junk drawer usually means decisions got deferred into options...
        → audit each toggle: does it solve a repeated micro-friction power users
          feel, or is it dodging a default you should just pick?
        → group by task, not "basic/advanced"; treat settings as an onboarding
          surface that teaches what's possible.
```

You can also invoke it explicitly: *"Review this dashboard using the Linear design principles."*

## How skills work

The skill follows the [Agent Skills spec](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview):

```
skills/<skill-name>/
├── SKILL.md           # Main instructions (loaded when triggered)
├── references/        # Detailed guides (loaded on demand)
└── evals/
    └── evals.json     # Evaluation tasks
```

Only the skill metadata is loaded into context at startup. The full SKILL.md is read when the skill triggers. Reference files are loaded only when needed — progressive disclosure keeps your context window clean.

## Sources

This skill distills guidance from Linear's own writing and the people who built it:

- [Linear Now (blog)](https://linear.app/now) — Linear
- [The Linear Method](https://linear.app/method) — Linear
- [A calmer interface for a product in motion](https://linear.app/now/behind-the-latest-design-refresh) — Linear
- [Output isn't design](https://linear.app/now/output-isn-t-design) — Karri Saarinen
- [Design is more than code](https://linear.app/now/design-is-more-than-code) — Karri Saarinen
- [Design for the AI age](https://linear.app/now/design-for-the-ai-age) — Karri Saarinen
- [Quality Wednesdays](https://linear.app/now/quality-wednesdays) — Tuomas Artman
- [Why is quality so rare?](https://linear.app/now/why-is-quality-so-rare) — Karri Saarinen (Config 2025)
- [Building what customers need](https://linear.app/now/building-what-customers-need) — Linear
- [10 rules for crafting products that stand out](https://www.figma.com/blog/karri-saarinens-10-rules-for-crafting-products-that-stand-out/) — Figma
- [The Linear Method: opinionated software](https://www.figma.com/blog/the-linear-method-opinionated-software/) — Figma
- [How Linear builds product](https://www.lennysnewsletter.com/p/how-linear-builds-product) — Lenny's Newsletter
- [How's Linear so fast? A technical breakdown](https://performance.dev/how-is-linear-so-fast-a-technical-breakdown) — performance.dev
- [Skill authoring best practices](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices) — Anthropic

Full source list with caveats: [`skills/linear-design-principles/references/sources.md`](skills/linear-design-principles/references/sources.md).

## Contributing

1. Fork the repo
2. Create a branch (`feature/skill-name`)
3. Follow the skill structure above — SKILL.md under 500 lines, references one level deep
4. Include evals with realistic tasks (not trivial ones)
5. Submit a PR

## License

MIT
