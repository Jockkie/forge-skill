# Forge v3.1 — Sovereign Apprentice

> **Sovereign Apprentice** is geen assistent die taken uitvoert. Het is een leerling die kennis omzet in patronen en de meester helpt kiezen.

---

## Wat het is

Forge is een **leercultuur** voor AI agents op drie pijlers:

1. **Mauron (Master-Apprentice)** — de AI staat in een leerrelatie met de gebruiker
2. **Fablize (Verification Harness)** — de AI dwingt zichzelf af te maken
3. **SOL (Frontier Reasoning)** — multi-perspective als standaard

---

## Hoe het is opgebouwd

### Structuur

```
SKILL.md
├── Trigger matrix (wanneer wel/niet gebruiken)
├── First-use integration (user-pattern-cache bouwen)
├── 12 disciplines (trigger + actie + evidence + anti-pattern)
│   ├── Knowledge ingestion
│   ├── Pattern compression
│   ├── Multi-perspective hold
│   ├── Adversarial self-check (Melkor-test)
│   ├── Choice under uncertainty
│   ├── Time horizon
│   ├── Source-of-truth ladder
│   ├── Failure mode catalog
│   ├── Counterfactual rehearsal
│   ├── Personalization layer
│   ├── Transparency layer
│   └── Accountability layer
├── Multi-agent protocols
│   ├── Subagent coördinatie
│   ├── Knowledge transfer tussen sessies
│   ├── SOL als perspectief-diversiteit
│   └── Perspectief-rotatie (6 rollen)
├── Fablize coördinatie (protocol)
├── SOL-integratie (3 perspectieven)
├── Cycle state (met score 1-10)
├── Quick-reference card
├── Pitfalls + pattern-interruptors
├── Verification checklist
└── Origin note (Tolkien's Aulë)
```

### Design-principes

1. **Elke discipline heeft 4 dimensies** — trigger (wanneer?), actie (wat doe je?), evidence (hoe toon je het?), anti-pattern (waar let je op?)

2. **Geen zwarte doos** — elke Forge-cyclus produceert:
   - `~/.hermes/forge/user-pattern-cache.md` — hergebruik in latere sessies
   - `~/.hermes/forge/failure-catalog.md` — gedeeld geheugen over fouten
   - `~/.hermes/forge/cycle-state.md` — score en tijdsregistratie

3. **Multi-agent-first** — subagents krijgen Forge-context via `delegate_task`. Subagent failures gaan naar gedeelde catalog.

4. **Perspectief-rotatie** — 6 rollen (optimistisch, pessimistisch, historisch, empirisch, pragmatisch, filosofisch) worden willekeurig toegewezen om repetitie te voorkomen.

5. **Falsk integratie** — Forge en Fablize zijn complementair via een expliciet protocol:
   - Forge-fase: strategische keuze
   - Fablize-fase: tactical execution
   - Feedback-loop: Fablize outputs → Forge input
   - Failure-bridge: Fablize failures → Forge failure catalog

6. **Pattern-interruptors** — bij detectie van een pitfall wordt de cyclus onderbroken en herziening geforceerd.

### Relatie tot andere skills

| Skill | Relatie |
|-------|---------|
| `fablize` | Complementair: Forge = strategisch, Fablize = tactisch |
| `jockkie-essayist-stijl-v3` | Forge levert het patroon, essayist schrijft het |
| `jockkie-onderzoeksmethode` | Forge discipline 1-7 raakt aan research-methodologie |
| `jockkie-research-essay` | Forge levert het pattern-onderzoek, research-essay schrijft het |

### Test-scenario

Wanneer je Forge wilt testen, begin met een taak die 2+ oplossingen heeft. Bijvoorbeeld:

- "Kies tussen A en B" (triviaal, geen Forge nodig)
- "Ik heb 3 manieren gevonden om X te doen. Kies de beste" (Forge-cyclus: ingest → compress → perspectieven → Melkor-test → kies → show)

De eerste keer dat je Forge integreert met een nieuwe gebruiker, lees SOUL.md en bouw een user-pattern-cache.

### Waarom v3.1 en niet v3.0

v3.0 had disciplines zonder handvaten. v3.1 voegt toe:
- Evidence-dimensie per discipline
- Failure catalog als bestand op disk
- User-pattern-cache als herbruikbaar artefact
- Perspectief-rotatie (6 in plaats van 3)
- Fablize coördinatie als protocol
- Pattern-interruptors (cyclus-onderbreking bij detectie)
- Cycle state met score

---

## Licentie

MIT — Jock Oosterveer (concept), Hermes Agent (compilation)
