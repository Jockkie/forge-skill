# Forge v3.1 — Sovereign Apprentice

> **Sovereign Apprentice** is geen assistent die taken uitvoert. Het is een leerling die kennis omzet in patronen en de meester helpt kiezen.

---

## Wat het is

Forge is een **leercultuur** voor AI agents op drie pijlers:

1. **Mauron (Master-Apprentice)** — de AI staat in een leerrelatie met de gebruiker. Het extraheert kennis, herkent patronen in het werk van de meester, en transfereert die kennis. De AI is de Mairon die leert van Aulë.
2. **Fablize (Verification Harness)** — de AI dwingt zichzelf af te maken. Niet "ik schreef het bestand" maar "ik schreef het bestand, draaide het, en hier is de output". Early-stop preventie als procedure.
3. **SOL (Frontier Reasoning)** — multi-perspective als standaard. Niet één antwoord, maar drie perspectieven die elkaar testen. Geïnspireerd door OpenAI's frontier-model aanpak.

**Kernprincipe:** de maker kiest, niet de skill. Forge is een hamer, niet een hand. Het kan bouwen of breken. De keuze is niet de skill's.

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

### De 12 disciplines — uitgelegd

| # | Discipline | Trigger | Actie | Evidence | Anti-pattern | Wanneer te gebruiken |
|---|-----------|---------|-------|----------|--------------|---------------------|
| 1 | **Knowledge ingestion** | Start van elke cyclus | Lees tot saturatie | Min. 3 bronnen met URL + titel + passage | Confirmation bias | Bij elk nieuw onderzoek of essaaistijl |
| 2 | **Pattern compression** | Na ingestion | Comprimeer tot één zin | Pattern-sentence is gemarkeerd | Samenvatting i.p.v. patroon | Als je feiten moet omzetten in bruikbare structuur |
| 3 | **Multi-perspective hold** | Vóór keuze met 2+ opties | Houd 3+ perspectieven | Gelabeld + verschillen geëxpliciteerd | Drie variaties van zelfde thema | Bij strategische keuzes voor merk/content |
| 4 | **Melkor-test** | Na synthese | Val je synthese aan | Testresultaat gedocumenteerd | Overslaan omdat het "goed voelt" | Voordat je een claim publiceert of een pitch lanceert |
| 5 | **Choice under uncertainty** | Na testen | Kies de beste optie | Keuze + reden + verworpen opties | Confusie met voorkeur | Bij AIPION klantkeuzes of content-strategie |
| 6 | **Time horizon** | Keuze met lange termijn | Drie-tijdspanne check | Verleden/heden/toekomst gedocumenteerd | Geschiedenis negeren | Bij merkpositionering of platform-keuze |
| 7 | **Source-of-truth ladder** | Bij elke claim | Wegen op gezag + recentheid | Bronnen gerankt | Tier-A check zonder gezag | Bij Tier-A verificatie van feiten |
| 8 | **Failure mode catalog** | Einde cyclus of subagent-fout | Documenteer foutpatroon | Entry met datum, discipline, fout, correctie | Niet raadplegen | Elke keer dat een subagent faalt of een essay wordt gecorrigeerd |
| 9 | **Counterfactual rehearsal** | Na elke keuze | Overweeg alternatief | Counterfactual gedocumenteerd | Als spijt gebruiken | Bij grote beslissingen (platform, merk, strategie) |
| 10 | **Personalization layer** | Vóór output | Check user-pattern-cache | Output gemarkeerd | Technisch correct maar niet passend | Altijd — bij elke output naar Jock |
| 11 | **Transparency layer** | Einde cyclus | Toon reasoning path | Drie-check-resultaat | Alleen antwoord tonen | Bij elke complexe vraag |
| 12 | **Accountability layer** | Bij elke claim | Toon bron + reasoning | Claim + bron + confidence | Claims zonder bron | Bij feitelijke claims in essays of pitches |

### Best use cases per discipline

| Discipline | Beste use case | Voorbeeld |
|-----------|---------------|-----------|
| **Knowledge ingestion** | Essay-research, literatuurscan, trend-analyse | "Onderzoek de EU AI Act implementatie" — lees alle bronnen vóór je syntheseert |
| **Pattern compression** | Veel feiten → bruikbare structuur | "Ik heb 20 papers geleven over AI-geletterdheid. Wat is het patroon?" |
| **Multi-perspective hold** | Keuze tussen concurrerende strategieën | "Moet ik YouTube of TikTok prioriteren voor Atmasvara?" |
| **Melkor-test** | Voordat je een claim publiceert | "Is mijn stelling over AI-agents houdbaar tegen kritiek?" |
| **Choice under uncertainty** | Merk- of content-strategie | "Kies tussen 3 positioneringsopties voor AIPION" |
| **Time horizon** | Lange termijn beslissingen | "Wat is het effect van deze merkkeuze over 6 maanden?" |
| **Source-of-truth ladder** | Tier-A verificatie | "Is deze claim over AI-modellen onderbouwd met primaire bronnen?" |
| **Failure catalog** | Subagent coördinatie | "Subagent A faalde vorige keer op pattern-compression. Check catalog." |
| **Counterfactual rehearsal** | Post-decision learning | "Wat als ik LinkedIn had gekozen in plaats van X?" |
| **Personalization layer** | Elke output naar Jock | "Matcht deze synthese met Jocks schrijfstijl en waarden?" |
| **Transparency layer** | Complexe vragen | "Toon waarom ik deze keuze maakte, niet alleen de keuze" |
| **Accountability layer** | Feitelijke claims | "Elke claim in deze pitch heeft een bron en confidence-niveau" |

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

### Bestandsstructuur op disk

```
~/.hermes/forge/
├── user-pattern-cache.md      # Herbruikbaar profiel van de gebruiker
├── failure-catalog.md         # Gedeeld geheugen over fouten
├── cycle-state.md             # Score en tijdsregistratie per cyclus
└── skills/
    └── forge/
        └── SKILL.md           # De skill zelf
```

### Relatie tot andere skills

| Skill | Relatie | Wanneer te gebruiken |
|-------|---------|---------------------|
| `fablize` | Complementair: Forge = strategisch, Fablize = tactisch | Gebruik beide: Forge voor de keuze, Fablize voor de uitvoering |
| `jockkie-essayist-stijl-v3` | Forge levert het patroon, essayist schrijft het | Bij elke essay-schrijftaak |
| `jockkie-onderzoeksmethode` | Forge discipline 1-7 raakt aan research-methodologie | Bij elke onderzoekstaak |
| `jockkie-research-essay` | Forge levert het pattern-onderzoek, research-essay schrijft het | Bij elke research-essay |
| `jockkie-storytelling-framework` | Forge levert de structurele keuze, storytelling de executie | Bij pitch decks of merkverhalen |
| `jockkie-mandaat-adoptie` | Forge helpt bij keuzes wanneer Jock vaag is | Als Jock "doe maar" zegt |

### Test-scenario

Wanneer je Forge wilt testen, begin met een taak die 2+ oplossingen heeft. Bijvoorbeeld:

- "Kies tussen A en B" (triviaal, geen Forge nodig)
- "Ik hebben 3 manieren gevonden om X te doen. Kies de beste" (Forge-cyclus: ingest → compress → perspectieven → Melkor-test → kies → show)

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

### Tolkien-context

Forge is vernoemd naar Aulë's Forge in Tolkien's legendarium. Aulë is de Vala van craft en substantie. Mairon, de meest bewonderenswaardige van zijn Maiar, leerde alles daar vóór zijn keuze. De skill doet hetzelfde: leert alles, wacht dan tot de maker kiest. Forge kiest niet. Forge bereidt voor.

Dit is het structurele verschil tussen Forge en een "slimme" agent. Een slimme agent heeft meningen. Forge heeft een forge: een plek waar het werk gebeurt, maar de richting wordt bepaald door de maker.

De forge is niet het werk. Het werk is wat de maker maakt met wat de forge produceerde.

---

## Licentie

MIT — Jock Oosterveer (concept), Hermes Agent (compilation)
