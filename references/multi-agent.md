# Perspectives and multi-agent operation

## The perspective pool

Six roles. Each is a stance with its own question, not a mood.

1. **Advocate.** What is the strongest case for this, made by someone who would stake something on it?
2. **Opponent.** What is the strongest case against, made by someone competent and unpersuaded?
3. **Historian.** Has this been tried? By whom, and what happened? Which pattern is repeating?
4. **Practitioner.** What happens when someone actually does this on a Tuesday morning, with the constraints they really have?
5. **Economist.** What does this cost, what is traded away, and what are the second-order effects at scale?
6. **Outsider.** What would someone with no stake and no context find obvious, or absurd?

## Selection rule

Per cycle, select three under three constraints:

- At least one from {Advocate, Opponent}.
- At least one from {Historian, Practitioner, Economist, Outsider}.
- No perspective repeats from the immediately preceding cycle on related work.

Coverage check: across any four consecutive cycles all six must have appeared. If one has not, it is forced into the next selection. This is checkable against `cycle-log.md`, which random assignment is not.

Record the three used in the cycle log. That record is what makes the rule enforceable rather than aspirational.

## Single-agent operation

Without subagents, hold the three sequentially. Write each one out under its label before moving to the next, and do not let the previous perspective's conclusion leak into the next one's framing. A perspective written after you already know the answer is not a perspective.

## Multi-agent operation

With subagents, one perspective per agent is stronger than one agent performing three, because a specialised agent goes deeper and cannot see the others' output.

Every spawned subagent must receive, in its context: the pattern sentence, the relevant slice of the user pattern cache, the relevant catalog entries, and its assigned perspective. A subagent without these produces work that fails the fit check and has to be redone.

No subagent reports completion without evidence. Not "the file is written" but "the file is written, here is what running it produced". This is the verification half of Forge and it is not optional in delegated work, where the parent cannot see what happened.

The parent synthesises. Subagents hold perspectives; they do not choose. The parent checks the output rather than trusting the report.

## Failure catalog across agents

One shared file, append-only. Every entry stamped with agent identifier and timestamp. Nobody rewrites or reorders existing entries; conflicts are avoided by never editing what is already there rather than by locking.

Reads are cheap and unrestricted: read the whole file, filter by domain tag. Shared beats per-agent because a failure by one agent should make every other agent smarter, which is the only mechanism in Forge that compounds.

If a runtime cannot write persistently, entries are held in-session and handed to the user as text at the end. Silently skipping the catalog is the failure mode this rule exists to prevent.
