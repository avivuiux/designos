# Design OS

**A multi-agent system that specs a product by reading it - its code, its docs, the real thing - and stops at human gates so a person stays in control.**

> A case-study and a working tool. Written transparently: what I built, and why each decision.
> Engineering source-of-truth: `SPEC.md`. Live proof: `runs/`.

---

## The story

When I join a new product, the part I get stuck on isn't the design - it's the **spec**: understanding, deeply, what we're actually building and why. It's also the part where AI helped me least. It was great at design variations, where I was already strong. It was useless exactly where I was weak.

So instead of solving one project, I **systematized the bottleneck.** I built a system of agents that runs the spec phase: it reads an existing product, digs out the right questions, anchors the work in real market context, synthesizes a spec, and then attacks its own spec to find what's missing. It amplifies my weakness and leaves the visual taste - my strength - in my hands.

That last part is the whole thesis: **AI as a thinking-partner at the front of the funnel, not a replacement for the designer at the end of it.**

## Two layers (it needs both)

This is what makes it a portfolio piece for AI-product design, not just an automation script:

- **Layer 1 - what the agents do:** the UX work itself. Reading, questioning, synthesizing, critiquing a spec.
- **Layer 2 - how the agent experience feels (AX):** how the human stays in control, calibrates trust, orchestrates the run, and approves at gates. Designing the *experience of working with the agents* is the harder, less-fakeable skill - and it's the one AI-product teams are actually hiring for.

## The cast (six agents)

Each agent is one mind, one job. They don't know about each other - the workflow wires them together.

| Agent | Archetype | Job |
|---|---|---|
| `context-reader` | Reader | Reads code + docs into a state-map; separates **quoted** fact from **inferred** guess, with a source on every claim |
| `goal-clarifier` | Definer | Pins the target: outcome, success metrics (with a number *and* a baseline, or it's flagged ⚠️), hard constraints |
| `background-researcher` | Scout | The only agent that looks **outward** (web): competitors, domain conventions, external benchmarks - every claim with a real URL and a freshness date |
| `depth-questioner` | Asker | Surfaces hidden assumptions as prioritized depth-questions (`must / should / nice` to know) |
| `spec-synthesizer` | Synthesizer | Turns it all into a structured spec - user stories, acceptance criteria, edge cases - with source-traceability on every line |
| `spec-critic` | Adversary | Attacks the spec: "what's missing, which assumption was never verified, what breaks this" |

## The workflow: deep-spec

A pipeline of seven agent-steps with **three human gates**, run by one orchestrator:

```text
context-reader -> 🚪 gate 1 (approve the map)
goal-clarifier -> background-researcher -> depth-questioner -> 🚪 gate 2 (approve goals + research + answer questions)
spec-synthesizer -> spec-critic -> 🚪 gate 3 (decide on each finding)
spec-synthesizer (revision pass) -> hardened spec v2
```

The gates are not a formality - **they are the product.** "One command" here does not mean push-a-button-and-walk-away. It means one command that orchestrates everything and *stops three times for a human to decide*. The whole value is that the person is the one who rules, not the machine.

You run it with one command (`/deep-spec`), or by handing the portable driver-doc (`workflows/RUN-deep-spec.md`) to any capable agent - it works outside this CLI too.

## The proof: a live run on a real product

I ran the full pipeline on **PriceMatch** (a live SaaS the agents had never seen) to spec a real, undecided feature - a "text-first" extraction engine. The whole run is in `runs/`, every intermediate artifact saved. Two moments are worth calling out, because they're the reason the *system* matters more than any single agent:

**1. The adversary caught what the synthesizer missed.** The synthesized spec confidently rested the entire feature on "text is ~10x cheaper than images." The `spec-critic` flagged it as the fatal assumption: the existing engine may *already* bill digital PDFs as text, in which case the cost-saving is illusory and the whole rationale collapses. Its fix: measure the real token cost *before* building. A confident synthesizer alone is blind to strategic risk. Only the adversary sees it.

**2. Two independent agents converged on the same truth.** Separately, `background-researcher` did real web research and confirmed it from the outside: the current cost baseline (~$0.0003/extraction) is already at the cheap end of the market - so the feature's real ROI is **privacy and local-first processing, not cost.** When two agents that don't know about each other reach the same conclusion, that's validation, not an echo. (Its sources were verified by hand before saving - no fabricated URLs. Source-discipline is the point.)

Then I ran the system **on itself** to spec Design OS, and again to spec the hero of my portfolio site after ten patch-iterations had failed. It's a tool I actually use.

## How it's built (from scratch)

Every agent is a single markdown file with a fixed anatomy (role / mission / method / input / output / rules) - not code, not a black box. The agents **run as real, separate subprocesses**, and the workflow orchestrates them. I built the whole thing from scratch, on purpose, so I'd understand the mechanism from the inside - not just use a tool.

The recurring lesson, proven twice: **the loop beats the single agent.** Synthesize, attack, fix.

## Design principles (the AX layer)

What turns a pile of prompts into a system you can trust:

- **Trust calibration** - every output shows its confidence, its *why*, and its source. You trust it the right amount, not blindly.
- **Human-in-the-loop** - approval gates; the system stops and hands decisions back to a person. It never answers for you at a gate.
- **Source-traceability** - every spec line points to its origin; every unverified assumption is marked ⚠️.
- **Quoted vs inferred** - the reader never blends fact with guess. "Not found" and "I don't know" are legitimate, respected answers.
- **Progressive disclosure** - the orchestrator doesn't dump all of its power at once; it surfaces what you need to decide, when you need to decide it.

## What's next (honest)

Adaptive method-routing (the north-star): a layer above the fixed workflow that picks the *right process for the problem* - a method-selector and a gestalt-critic. Deliberately gated until the core is demo-ready. The discipline is **depth before breadth**: excellent at one thing first, then widen. Width-first is the trap these tools die in.

---

**In one line:** *I systematized the part of my own work I was worst at. The result is a multi-agent system that learns any product from its source, keeps a human at the controls, and produces a spec you'd hand to a real client - and it runs. The proof is in `runs/`.*
