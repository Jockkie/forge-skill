# Forge local mapping

Copy this file to `FORGE-LOCAL.md` in the same directory as `SKILL.md`. Forge reads it when present and ignores its absence entirely.

This file is where an installation connects Forge to the skills it happens to have. Nothing here is portable, which is exactly why it lives outside the skill: your mapping should never become someone else's dependency.

Fill in the skill name for any role you can fill. Delete the rest.

```
discovery:     <skill that surfaces relevant skills before responding>
research:      <skill that searches the web and retrieves sources>
verification:  <skill that checks claims against primary sources>
voice:         <skill that rewrites output into the user's register>
format:        <skill that applies a house structure to artefacts>
gated-access:  <skill that reaches sources behind login walls>
```

Optionally, override defaults:

```
language:      <language for internal reasoning and output; default is the user's active language>
default-depth: light | full        # default is light when the depth gate is ambiguous
agent-id:      <identifier written into the catalog and cycle log>
```

## Rules

A role left empty is not an error. Forge runs the corresponding discipline itself, with whatever the runtime provides, and states the gap once.

A skill named here is used after the choice, not during it. Forge produces the pattern and the decision; the mapped skills produce the artefact. A voice or format skill that runs before the choice is made will shape the reasoning, which is the failure this separation exists to prevent.

The verification role is the one worth filling first. It is the only role that changes what Forge is allowed to claim rather than how the output looks.
