# Cycle state templates

Starting points for the three files under `FORGE_HOME`. Copy the blocks you need. If the runtime cannot write persistently, hold these in session and hand them to the user as text before the session ends.

## cycle-log.md

One line per cycle. Its purpose is to make the perspective rotation rule and the catalog check verifiable after the fact, which a self-assessed quality score cannot do.

```
# Forge cycle log

YYYY-MM-DD | <agent-id> | light|full | perspectives: <three roles> | catalog: read|none | <one-line subject>
```

For Full-depth cycles that warrant a record, expand to a block:

```
## YYYY-MM-DD HH:MM | <agent-id> | full
Subject: <what was being decided>
Perspectives: <the three roles used>
Pattern: <the single sentence the synthesis compressed to>
Melkor: <what the attack revealed, or "held">
Choice: <what was chosen>
Rejected: <what was not chosen, and why>
Sources: <short list, with confidence per source>
Catalog: read <entries> | written <entry>
```

## user-pattern-cache.md

```
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

## Language
Language for internal reasoning and user-facing output.
```

## failure-catalog.md

Append-only. Newest at the bottom. Never rewrite or reorder existing entries; that is what makes the file safe for several agents to share.

```
# Failure catalog (append-only)

## YYYY-MM-DD | <agent-id> | <domain-tag>
Discipline: <which of the twelve let it through>
Failure: <what went wrong, one or two sentences>
Correction: <what should happen instead next time>
```

Write an entry when a cycle has been shown to be wrong, not when it merely feels imperfect. A catalog full of near-misses is a catalog nobody reads, and the read is the half that compounds.
