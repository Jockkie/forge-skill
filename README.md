# Forge

A decision-preparation discipline for AI agents. Forge does not decide. It reads until saturation, compresses to a pattern, holds perspectives that could reach different conclusions, attacks its own synthesis, and then hands a prepared choice to the person who has to live with it.

Most AI work fails because the model acts before it has learned. It produces a summary where a pattern was needed, picks the first option where the best one was needed, and sounds confident where it should have been accurate. Forge is the discipline against that.

**The maker chooses, not the skill.** Forge is a hammer, not a hand. It can build or break. That choice is not the skill's.

## Installation

Forge is a plain Agent Skill: a `SKILL.md` with YAML frontmatter, plus reference files loaded on demand. Copy the whole directory into your runtime's skill location.

Claude Code, personal scope: `~/.claude/skills/forge/`
Claude Code, project scope: `<project>/.claude/skills/forge/`

For other runtimes, use whatever directory that runtime scans for skills; consult its documentation. The skill makes no assumptions about which one it is running in.

Optionally set `FORGE_HOME` to control where state is written. Without it, Forge falls back to `./.forge/`, then `~/.forge/`, then session-only memory.

Nothing else is required. No dependencies, no other skills, no configuration.

## What is inside

```
forge/
├── SKILL.md                       # loaded when the skill triggers
├── FORGE-LOCAL.example.md         # optional: map your own skills to roles
├── references/
│   ├── disciplines.md             # full spec per discipline
│   ├── multi-agent.md             # perspective pool, rotation, subagents
│   └── state.md                   # file formats, coordination
└── templates/
    └── cycle-state-template.md    # starting point for the state files
```

`SKILL.md` carries the trigger conditions, the capability probe, the cycle, and the interruptors. Everything else is read only when needed, so installing Forge costs little context until it actually runs.

## Portability

Forge probes its runtime instead of assuming one. It establishes whether it can write persistent files, whether it can spawn subagents, whether a user profile exists, and whether a human is in the loop. Each answer has a defined fallback, and a degraded mode is stated to the user rather than passed over in silence.

That is the difference between a discipline and a configuration: a discipline still runs when the tooling is missing, it just runs smaller.

## Integration

Forge prepares choices. It does not execute them, and it does not ship with the skills that do. What it defines instead is the set of roles a surrounding toolchain can fill, so any installation can map its own skills onto them.

| Role | What it contributes | Required |
|---|---|---|
| Discovery | Surfaces relevant skills before Forge responds | No |
| Research | Web search, source retrieval, URL extraction | No, but the source ladder is thin without it |
| Verification | Checks load-bearing claims against primary sources | Recommended |
| Voice | Rewrites output to match the user's register | No |
| Format | Applies a house structure to the finished artefact | No |
| Gated access | Reaches sources behind login walls | No |

If a role is unfilled, Forge runs without it and says so once, in the same degraded-mode line as the capability probe. None of these are hard dependencies. An installation with every role unfilled still runs the full cycle; it simply carries less evidence.

To wire your own skills to these roles, copy `FORGE-LOCAL.example.md` to `FORGE-LOCAL.md` beside `SKILL.md` and fill in one line per role. Forge reads it when present and ignores its absence. It is gitignored by default, because that mapping is yours and not portable.

**Language.** Internal reasoning, summaries, and user-facing output follow the user's active language. Sources stay in their original language and are not translated during ingestion, because translating before compressing loses the pattern. Where the runtime exposes no language preference, follow the language of the request.

## Using it well

Run it on decisions, not on tasks. Forge on a lookup is theatre, and running it everywhere is the fastest way to make people stop running it at all. The negative trigger list in `SKILL.md` is as load-bearing as the positive one.

Use the depth gate. Most of the cost is writing evidence, not thinking. Reversible work gets the light pass.

Do not copy this as a procedure. The properties are the standard and the order is the discipline: learn first, compress to a pattern, hold perspectives, attack yourself, choose, show your work.

## Origin

Named after Aulë's Forge in Tolkien's legendarium. Mairon, the ablest of Aulë's Maiar, learned everything there before he chose, and chose badly. That is the point rather than an awkward detail: the forge grants capability, not direction.

The forge is not the work. The work is what the maker makes with what the forge produced.

## Licence

MIT. See `LICENSE`.
