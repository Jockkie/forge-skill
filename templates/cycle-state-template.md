# Forge Cycle State Template

Copy this file to `$FORGE_HOME/cycle-log.md` and append a new entry for each cycle.

```
## Cycle <timestamp>

- **Date:** YYYY-MM-DD HH:MM (local)
- **Agent:** <agent name / session id>
- **Depth:** light | full
- **Subject:** <one-line description of what was decided>
- **Perspective pool:** <roles used, e.g. "Skeptic, Optimist, Historicus">
- **Pattern sentence:** <the single-sentence pattern the synthesis compressed to>
- **Melkor result:** <what the attack revealed / "passed">
- **Choice:** <what was chosen>
- **Rejected options:** <1-3 lines on what was not chosen>
- **Sources consulted:** <short list with confidence levels>
- **Catalog read:** <yes/no; entries consulted>
- **Catalog written:** <new entry added, if any>
- **Score (1-10):** <only if externally assigned>
```

## File formats

### user-pattern-cache.md

```
# User Pattern Cache

## Values
<comma-separated list of core values>

## Writing style
<sentence length, formality level, preferred vocabulary>

## Anti-patterns
<things the user explicitly rejects or dislikes>

## Domain knowledge
<areas of expertise, recent interests>

## Language preference
<prefered language for internal reasoning and user-facing output>
```

### failure-catalog.md

```
# Failure Catalog (append-only)

## <timestamp> — <subject line>

**What failed:** <description>
**Root cause:** <analysis>
**Fix:** <corrective action>
**Prevention:** <how to avoid re-occurrence>
**Skill(s) involved:** <list of skills>
```