---
name: linear-design-principles
description: Applies Linear's UI/UX and product philosophy — design as product judgment, not decoration — when designing, building, or reviewing interfaces and making product decisions. Use when framing a product problem, planning a redesign, deciding scope, reducing visual noise, designing AI/agent interfaces, debating customization vs. opinionated defaults, or setting up product process (handoffs, OKRs, A/B testing, design reviews). Triggers on "Linear style," "calm interface," "opinionated software," "is this the right problem," "should we add a setting," "feature request vs need," "redesign strategy," "should we set OKRs," "do we need A/B testing," "design-to-engineering handoff." Not for replicating the Linear visual aesthetic (dark mode, gradients, minimalist landing pages) — this is about product method, not the look.
---

# Linear Design Principles

Apply how Linear thinks about UI, UX, and product. The throughline: **design is product judgment, not decoration**, and it only works when backed by structure — opinionated defaults, near-zero latency, trained quality, and small teams that own problems end to end.

> [!info] Terminology trap
> "Linear design" in most search results means a generic SaaS *aesthetic* (dark mode, gradients, minimal landing pages) named after the company. That is the look, not the method. This skill is about how Linear actually works. Ignore the aesthetic literature.

## When to apply this

Reach for these principles when the task is one of:

- **Designing or reviewing an interface** → use the hierarchy + clarity rules below, then `references/ui-ux-craft.md`.
- **Framing a product problem** → "problem before solution"; interpret requests, don't transcribe them.
- **Planning a redesign or paying down design debt** → `references/ui-ux-craft.md` (redesign strategy).
- **Designing AI/agent features** → "build the workbench, not the chatbox."
- **Deciding process, org, or how decisions get made** → `references/operating-model.md`.
- **Citing or sourcing a claim** → `references/sources.md`.

> [!note] Scope
> This is about **product judgment — what to build and whether the problem is real** — not pixel-level execution. Pair it with a visual-craft/implementation skill: use this to decide what should exist, then a craft skill to execute. The interaction guidance here is **desktop- and keyboard-first** (command palette, dense lists, keyboard as primary input); defer touch/responsive/small-screen work to skills built for that. Linear hasn't published a mobile design philosophy, so don't invent one.

---

## The core principles

### 1. Design for someone specific. Be opinionated.

You cannot build something excellent for everyone. Pick a specific user and a specific use case and optimize hard for it; accept that it will be a poor fit outside that lane. Restraint is the strategy, not a limitation.

- A product needs a clear value proposition to win trust. Generic = invisible.
- Be most opinionated at the **atomic level** (what properties an issue has), more flexible at **broad containers** (how projects are structured), because every company is shaped differently.

### 2. Ship one really good way, not infinite flexibility.

Ship strong defaults that guide users toward a good workflow. Flexible software lets everyone invent their own process, which becomes chaos as teams scale.

- Sometimes the opinionated answer is **"no."** Refuse whole categories of requests that protect managers at the expense of the daily IC workflow (e.g., required fields, multiple assignees) — saying no is a feature of an opinionated tool, not a failure to satisfy it. (Interpreting the underlying need is principle 10; this is the case where, even interpreted, the right call is still to decline.)
- Default to "simple first, then powerful": simple to start, more capable as you scale.

### 3. Use plain language. No invented jargon.

Vocabulary is a design surface. Use universal units (issues, projects, teams) so nobody needs a handbook. Don't invent terms — they mean different things to different people. Write issues, not "As a user, I want…" user stories that hide the actual need.

- Extend this to **all words on screen**, not just object names: button labels, error messages, empty-state copy, and notification voice are part of the calm. Aim for terse, human, jargon-free microcopy. (Linear has no dedicated essay on voice; treat the specific tone calls as inference from the product, not a sourced rule.)

### 4. Understand the problem before drawing the screen.

The most common reason design projects drag or fail is an unclear problem. Generating the form is the easy part; knowing what should exist at all is the hard part.

- Write the problem in your own words first. Ask: is this real? What happens if we don't do it? Who defined it?
- If feedback feels contradictory, people are probably reacting to **different problem definitions**.
- Separate **problem design → conceptual solution → execution**. Decide concepts (is a "project" an issue, a label, or its own entity?) before UI details.
- **Output isn't design.** Polished AI-generated UI can have the form without the fit. Use AI for prototyping and exploration; keep human judgment responsible for problem framing.

### 5. Calm but dense: make hierarchy do the ranking.

Dense interfaces can still feel calm if hierarchy is sharp. Don't let every element compete for attention.

- Use **visual weight as a ranking system**: work content dominates; navigation and chrome recede.
- Borders, icons, backgrounds, and separators must **earn their existence**. If they don't clarify a relationship, they're clutter.
- "Structure should be felt, not seen." If most people don't consciously notice a refinement, that's a good sign.
- Test against **real app states** (full lists, empty states, long text), not isolated Dribbble-style mockups. Stress-test across browser/desktop, light/dark/custom themes, and edge cases.
- Treat **theming as a system**: derive themes from a few perceptual parameters (base color, accent, contrast in a perceptually-uniform space like LCH) plus a baked-in accessibility contrast variable — not by hand-tuning dozens of independent color values.
- For **data views and dashboards**, give every view a clear purpose and owner, and pair every metric with comparison, history, or a threshold — a raw number with no context is usually noise. (More in `references/ui-ux-craft.md`.)

### 6. Speed is architecture and input design, not polish.

"Calm, dense, fast" is not achievable with visual design alone. Linear bought the headroom for its minimal UI by making latency near zero, so the interface needs no spinners, skeletons, or progress affordances that add noise.

- Treat **latency as a UX bug**. Aim for instant (optimistic local writes, local-first data) before adding features. Eliminate spinners by having nothing to wait for.
- Speed is also an **input-model problem**: a fast backend still loses if the fastest path to an action needs a mouse and three menus. Make keyboard a primary input; a command palette should search the local object pool, not a server.

### 7. Treat quality as a trained habit and a hiring filter, not a final pass.

Craft is deliberate attention paid because it matters to the maker, not because someone is checking. It compounds through many small decisions.

- Quality is **everyone's job**, not just the designer's. Review UI as a group — different people notice different defects (misaligned pixels, animation timing, papercuts).
- Track papercuts as real work; keep fixes small enough to be sustainable. Consider a recurring quality ritual and a strict bug SLA (no permanent bug backlog).
- Trust intuition and customers over pure data. Keep MVPs internal until they're ready.

### 8. For AI features, build the workbench — not just a chatbox.

Generic chat is a weak, imprecise form for most workflows. Design structured surfaces ("workbenches") where AI operates inside clear context.

- Design the **review, approval, context, and control** surfaces, not just the prompt box.
- **Embed agents where the work already lives** — inside the issue, the triage queue, the review — not in a bolted-on chat panel. Let work auto-start from existing signals (e.g., triage) instead of requiring someone to open a separate tool.
- Make agent sessions **shared and observable**: anyone on the team can follow, redirect, or take over a run, rather than it being a private one-off. Surface the agent's reasoning, tool calls, and elicitations.
- **Keep a human accountable.** The issue stays assigned to a person — "an agent cannot be held accountable." As agents handle correctness and bug-finding, the human's job shifts up to judgment: is the work *useful*, not just correct? Unbounded AI is powerful but directionless.

### 9. Use settings for preferences, not deferred decisions.

Settings aren't automatically a sign of poor design. Use them for genuine preferences and repeated-use friction — not as a dumping ground for unresolved product decisions. Settings can also teach power users what's possible.

- Decision test: **is there a right default the product should just get right?** If yes, pick it — don't ship a toggle to avoid choosing. If it's genuine taste/habit the product shouldn't hold an opinion on, a setting is appropriate.

### 10. Build what customers need, not just what they ask for.

Treat requests as **input, not instructions**. Users describe symptoms or name a familiar solution; infer the deeper need. Don't tally feature requests blindly — research is interpretation, not transcription. (Example: users asked for "custom fields" but were really trying to track customer needs → build the purpose-built thing.)

### 11. Design for shared context, not handoffs.

As agents do more of the procedural work (Linear, 2026: coding agents in 75%+ of its enterprise workspaces, agent-completed work up 5x in three months, ~25% of new issues agent-authored), the bottleneck moves from execution to **context**. The job of the system is to capture customer feedback, decisions, strategic direction, and code in one place that both humans and agents can work from — so nothing has to be re-explained at a handoff.

- Linear's original "no handoffs, small connected teams" model is the **precursor** to this, not a contradiction: both eliminate the lossy PM→designer→engineer relay. Now the relay to eliminate also includes the human→agent one.
- Make the work the source of truth. If a decision or its "why" only lives in a chat thread or someone's head, an agent (and the next human) can't use it.
- This is *why* plain language (3), opinionated structure (2), and the workbench (8) matter more, not less, in the agent era — shared context only works if the vocabulary and structure are legible to everyone, human or machine.

---

## How decisions and teams should work (brief)

These structural facts are *why* the principles above hold. Full detail in `references/operating-model.md`.

- **No handoffs.** Small connected teams (≈1 designer + 2 engineers) own a problem end to end; design and engineering iterate toward "right" together. Quality improves when everyone understands implementation.
- **Taste decides; dogfooding and betas validate.** No OKRs, no metric goals per project, no A/B tests as decision-makers. Feature-flag to internal dogfooding within days, then optional customer beta. Senior taste applied continuously, not at checkpoints.
- **No formal design reviews.** Post early work async (e.g., a project channel) for feedback.
- **Speed is a result of competence, not corner-cutting.** Better to be decisively wrong and pivot than cautiously mediocre. Decide and move on.

---

## A working checklist

Copy this when designing or reviewing a feature:

```
Linear-style review:
- [ ] Who specifically is this for? Is it opinionated, or generically for "everyone"?
- [ ] Is the problem written clearly, in my own words? Is it the real problem or a symptom?
- [ ] Concept decided before pixels? (What is each entity, really?)
- [ ] Plain language — universal terms, no invented jargon? Is microcopy (labels, errors, empty states) terse and human?
- [ ] Does every border/icon/separator earn its place? Does chrome recede?
- [ ] Tested against real/full/empty states and light/dark/custom themes?
- [ ] If a data view: clear purpose + owner, and every metric paired with comparison, history, or a threshold?
- [ ] Any spinner that near-zero latency could remove instead?
- [ ] Is there a fast keyboard path to the primary action?
- [ ] Are we adding a setting to dodge a product decision the product should get right by default?
- [ ] Are we honoring a request literally instead of the underlying need?
- [ ] If AI: is there a structured workbench with review/approval, not just a chatbox?
- [ ] If AI/agents: is context (decisions, the "why," code) captured where humans and agents can both use it — nothing re-explained at a handoff?
```

---

## Reference files

- **`references/ui-ux-craft.md`** — The Linear blog posts worth reading (calmer interface, redesign strategy, output isn't design, design is more than code, design for the AI age, quality rituals, settings, customer needs, dashboards, plus the 2026 agent-era cluster: "issue tracking is dead," code review with Diffs, and teaching agents to do the work), each with its core lessons and link.
- **`references/operating-model.md`** — How Linear actually operates: org structure, decision-making, opinionated software, speed-as-architecture, the Linear Method, hiring, and planning mechanics.
- **`references/sources.md`** — Primary sources, interviews/profiles, technical breakdowns, and background, with sourcing caveats.
