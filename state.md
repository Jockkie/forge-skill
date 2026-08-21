# State files and coordination

All three live under the resolved `FORGE_HOME` (see `SKILL.md` §5). If no persistence exists, hold them in session and hand them to the user as text before the session ends.

## user-pattern-cache.md

Built on first use from the profile file found in the search order. Four sections, each kept short enough to load on every cycle without cost.

```markdown
# User pattern cache
Built: YYYY-MM-DD | Source: <file> | Rebuild after: YYYY-MM-DD

## Values
What they optimise for, in their words where possible.

## Style
Register, format preferences, length, hard formatting rules.

## Anti-patterns
What they do not want to hear or receive. Explicit prohibitions go here.

## Expertise
Domains where they know more than the agent, and where explanation is condescension.
```

Rebuild when older than thirty days, when a fit failure is corrected, or when the source profile changes. Note the rebuild date rather than silently overwriting, so a wrong cache can be traced.

## failure-catalog.md

Append-only. One block per entry, newest at the bottom.

```markdown
## YYYY-MM-DD | <agent-id> | <domain-tag>
Discipline: <which of the twelve let it through>
Failure: <what went wrong, one or two sentences>
Correction: <what should happen instead next time>
```

The domain tag is what makes the catalog usable at scale: read the whole file, filter to the tag that matches current work. Tags are freeform but should stay stable once chosen.

An entry is written when a cycle is shown to have been wrong, not when a cycle merely feels imperfect. A catalog full of near-misses is a catalog nobody reads.

## cycle-log.md

One line per cycle. Its purpose is to make the perspective rotation rule and the catalog check enforceable after the fact.

```
YYYY-MM-DD | <agent-id> | light|full | perspectives: <three roles> | catalog: read|none | <one-line subject>
```

No quality score. A self-assigned score is written by the same process that would have skipped the discipline, so it carries no information. If a score is wanted, the user assigns it.

## Coordination with verification-style skills

Forge prepares choices. Verification harnesses (fablize and equivalents) prove that work was actually done. They are complementary, not sequential stages of one pipeline.

- Forge runs when the question is *what should be done*, and outputs a prepared choice.
- The harness runs when the question is *did this actually work*, and outputs evidence.
- Harness failures become catalog entries, tagged to the discipline that permitted them.
- Harness outputs become ingestion material for the next Forge cycle.

When both could apply, ask which question is live. A decision that has already been made does not need Forge; it needs verification. A task with no decision point needs neither.

## Coordination with domain skills

Forge produces the pattern and the choice. Writing, design, research, and storytelling skills produce the artefact. Forge does not write the essay; it decides what the essay is about and why that angle rather than another. If a domain skill is available for the artefact, hand off after the choice rather than continuing into execution.
