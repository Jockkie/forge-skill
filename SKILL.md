---
name: "Forge"
description: "Decision-preparation discipline for non-trivial work: ingest sources to saturation, compress to a pattern rather than a summary, hold three genuinely different perspectives, attack the synthesis before shipping it, then choose and show the reasoning path. Use when two or more options compete, when facts must become structure, when a claim needs testing before commitment, when the cost of being wrong exceeds the cost of time, or when coordinating subagents. Do not use for trivial lookups, single-source facts, mechanical tasks with no decision point, or work where speed matters more than depth. Forge prepares the choice; the maker makes it."
---

# Forge

Forge is a learning stage that runs before a non-trivial action. It does not decide. It ingests, compresses, tests, and hands a prepared choice to the maker.

**Core principle: the maker chooses, not the skill.** Forge is a hammer, not a hand.

## 0. Capability probe (run once per session, before anything else)

Forge adapts to the runtime instead of assuming one. Establish four facts, pick the fallback, and state the degraded mode in one line to the user. Never skip a discipline silently.

| Probe | If yes | If no (fallback) |
|---|---|---|
| Can I write persistent files? | Resolve `FORGE_HOME` (see §5) and use the state files | Hold catalog and cycle log in-session; at the end, hand the user the entries as text to save |
| Can I spawn subagents? | Assign perspectives to separate agents | Hold perspectives sequentially in one agent, each explicitly labelled |
| Is there a user profile? | Load it (search order in §5) into a pattern cache | Work from the conversation only; say so |
| Is a human in the loop? | Confirm alignment on first use | Skip confirmation, log the assumption, proceed |

Capability names differ per runtime. Read for the capability, not the tool name: subagent spawning is `delegate_task` in Hermes, the Task/subagent tool in Claude Code, and may be absent elsewhere.

## 1. When to run

Run Forge when at least one holds: two or more competing solutions; facts must become a pattern; a claim must be tested from several angles before commitment; the answer is second-order ("why this and not that"); the cost of being wrong exceeds the cost of time; multiple agents must be coordinated.

Do not run Forge for: trivial lookups, single-source facts, mechanical tasks with no decision point, or anything where speed beats depth. Running Forge on small work is the most common way to make it useless.

## 2. Depth gate

Decide the depth before the cycle, not during it. Most of the cost of Forge is writing evidence, not thinking.

**Light** (reversible, hours-scale, low stakes): one to two sources, two perspectives, Melkor in one sentence, no written artefacts. Runs in-line.

**Full** (irreversible, weeks-scale, public, or expensive to undo): the whole cycle below with evidence written to state.

If unsure which applies, ask one question or default to Light and say so.

## 3. The cycle

**Spine — always, in order.**

1. **Ingest.** Read available sources until the marginal source adds nothing. Do not count sources that only confirm the synthesis you already have.
2. **Compress.** State the pattern in one sentence that survives the removal of every detail. If you cannot, you have not read enough. A summary lists; a pattern holds.
3. **Perspectives.** Hold at least three, fundamentally different, drawn from the pool in `references/multi-agent.md`. Three variations of one view is not three perspectives.
4. **Melkor test.** Read the synthesis as the person who most wants it to be wrong. If they break it, refine. If they cannot, it holds.
5. **Choose.** Not the majority, not the first, not the most popular. The option that fits this moment. Name the rejected options.

**Gates — only when the trigger fires.**

6. **Time horizon** (effect beyond one week): what was tried before, how this reads in six months, what delay costs.
7. **Source ladder** (any factual claim used as a basis): not "is this authoritative" but "is this the most authoritative source for this specific claim".
8. **Failure catalog** (persistence available, and similar work has run before): read before, append after. Append-only, never rewrite.
9. **Counterfactual** (decision whose outcome can later be observed): one line on the path not taken and what would signal it was better.

**Output filters — one pass over what leaves.**

10. **Fit.** Does this match the user's values, style, and stated anti-patterns? A technically correct synthesis that does not fit is a failed synthesis.
11. **Reasoning path.** Show what was chosen and what was rejected, not only the answer.
12. **Accountability.** Every claim carries its source and a confidence signal.

## 4. What is shown versus what is held

Show by default: the pattern sentence, the three perspectives in one line each, the Melkor outcome, the choice with rejected options.

Hold internally unless asked or unless an interruptor fires: full source lists with passages, the time-horizon check, the source ranking, the counterfactual, the fit check.

Full disclosure of all twelve on every cycle produces a compliance report longer than the work. That is how the discipline dies in practice.

## 5. State and paths

Resolve the working directory in this order, first hit wins: `$FORGE_HOME`, then `./.forge/` in the project, then `~/.forge/`, then session-only memory.

```
$FORGE_HOME/
├── user-pattern-cache.md    # values, style, anti-patterns, expertise
├── failure-catalog.md       # append-only, shared across agents
└── cycle-log.md             # one line per cycle: date, agent, depth, perspectives used
```

User profile search order, first hit wins: `SOUL.md`, `CLAUDE.md`, `AGENTS.md`, `USER.md`, then whatever memory the runtime provides.

Rebuild the pattern cache when it is older than thirty days, when the user corrects a fit failure, or when the source profile changes. A stale cache is worse than none, because it is trusted.

Formats for all three files: `references/state.md`.

## 6. Pattern interruptors

When one of these is detected, stop and revise rather than continuing.

| Detected | Interrupt with |
|---|---|
| Pattern needs more than one sentence | "Compression incomplete. Ingest further." |
| Perspectives differ only in tone | "These are variations. Generate three that could reach different conclusions." |
| Melkor skipped because it felt right | "Untested synthesis. Run the attack." |
| Choice matches preference, not moment | "This is preference. Re-check against the moment." |
| Output contradicts the pattern cache | "Fit failure. Revise before delivery." |
| Subagent spawned without context | "Subagent has no cache and no catalog. Pass both." |
| Similar work failed before | "Catalog has a prior failure on this. Read before proceeding." |
| Full depth chosen for reversible work | "Light is enough here. Do not instrument this." |

## 7. Reference files

Load only when needed. `references/disciplines.md` for the full trigger, action, evidence, and anti-pattern per discipline. `references/multi-agent.md` for the perspective pool, rotation rule, and subagent protocol. `references/state.md` for file formats and the coordination protocol with verification-style skills.

## Origin

Named after Aulë's Forge in Tolkien's legendarium. Mairon, the most able of Aulë's Maiar, learned everything there before he chose, and chose badly. That is the point: the forge grants capability, not direction. Forge prepares. The maker chooses.

MIT — Jock Oosterveer (concept), Hermes Agent (compilation).
