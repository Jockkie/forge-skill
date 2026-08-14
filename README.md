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

Elke discipline heeft vier dimensies:
- **Trigger** — wanneer pas je dit toe?
- **Actie** — wat doe je concreet?
- **Evidence** — hoe toon je dat je het gedaan hebt?
- **Anti-pattern** — waar let je op?

#### 1. Knowledge ingestion
- **Trigger:** Start van elke cyclus of nieuw onderwerp
- **Actie:** Lees alle beschikbare bronnen. Stop wanneer de marginale bron niets nieuws toevoegt.
- **Evidence:** Minimaal 3 bronnen gedocumenteerd met URL + titel + relevante passage.
- **Anti-pattern:** Bronnen die alleen de al bestaande synthese bevestigen (confirmation bias).
- **Wanneer:** Bij elk nieuw onderzoek, literatuurscan, of trend-analyse.

#### 2. Pattern compression
- **Trigger:** Na ingestion, vóórdat je syntheseert.
- **Actie:** Comprimeer tot één zin die waar blijft als je elk detail wegneemt. Als je dat niet kunt, is de compressie onvolledig.
- **Evidence:** De pattern-sentence is expliciet gemarkeerd in de output.
- **Anti-pattern:** Een samenvatting die noemt in plaats van een patroon dat houdt.
- **Wanneer:** Als je feiten moet omzetten in bruikbare structuur.

#### 3. Multi-perspective hold
- **Trigger:** Vóór elke keuze met 2+ opties.
- **Actie:** Houd minimaal 3 perspectieven tegelijk. Ze moeten fundamenteel verschillend zijn, niet variaties op hetzelfde thema.
- **Evidence:** De drie perspectieven zijn gelabeld en de verschillen zijn geëxpliciteerd.
- **Anti-pattern:** Drie variaties van dezelfde-view en doen alsof het perspectieven zijn.
- **Wanneer:** Bij strategische keuzes waar meerdere opties legitiem zijn.

#### 4. Adversarial self-check (Melkor-test)
- **Trigger:** Na synthese, vóór keuze.
- **Actie:** Stel je voor dat de persoon die het meest wil dat het fout is, de synthese leest. Wat zeggen ze? Als ze het niet kunnen breken, is het echt. Als ze het kunnen, verfijn het.
- **Evidence:** Het Melkor-test resultaat is gedocumenteerd (broken / not broken + reden).
- **Anti-pattern:** De test overslaan omdat de synthese "goed voelt". Een goed voelende synthese die niet de Melkor-test doorstaat, is broos.
- **Wanneer:** Voordat je een claim publiceert of een belangrijke beslissing neemt.

#### 5. Choice under uncertainty
- **Trigger:** Na ingestion, compressie, perspectieven, en Melkor-test.
- **Actie:** Kies niet de meerderheid, niet de eerste optie, niet de meest populaire. Kies de optie die past bij het moment. Documenteer waarom.
- **Evidence:** De gekozen optie + reden + verworpen opties + waarom verworpen.
- **Anti-pattern:** Confusie van keuze met voorkeur. De keuze moet het moment passen, niet de maker's voorkeur.
- **Wanneer:** Bij beslissingen waar meerdere valide opties bestaan.

#### 6. Time horizon
- **Trigger:** Bij keuzes die meer dan een week effect hebben.
- **Actie:** Lees het werk in tijd. Wat is eerder geprobeerd? Hoe ziet dit over zes maanden eruit? Wat zijn de kosten van vertraging?
- **Evidence:** Drie-tijdspanne check (verleden, heden, toekomst) is gedocumenteerd.
- **Anti-pattern:** Historie negeren. Patronen herhalen; fouten echoën.
- **Wanneer:** Bij merkpositionering, platform-keuze, of andere lange-termijn beslissingen.

#### 7. Source-of-truth ladder
- **Trigger:** Bij elke claim die je als basis gebruikt.
- **Actie:** Wegen hiërarchisch. Niet "is dit Tier A?" maar "is dit de meest gezaghebbende Tier A bron voor deze specifieke claim?". Een primaire bron wint van een afgeleide. Een recente gezaghebbende bron wint van een oudere minder-gezaghebbende.
- **Evidence:** Bronnen gerankt op gezag + recentheid + relevantie voor de claim.
- **Anti-pattern:** Tier-A check zonder gezaghebbendheid voor de specifieke claim.
- **Wanneer:** Bij feitsverificatie of het opbouwen van een beargumenteerde positie.

#### 8. Failure mode catalog
- **Trigger:** Aan het einde van elke cyclus, of wanneer een subagent faalt.
- **Actie:** Als een Forge-cyclus een antwoord oplevert dat later als fout blijkt, gaat het foutpatroon naar de catalog. Koppel de fout aan de discipline die faalde. Vóór de volgende Forge-cyclus op vergelijkbaar werk, raadpleeg de catalog.
- **Evidence:** Nieuwe entries in `~/.hermes/forge/failure-catalog.md` met: datum, discipline, foutomschrijving, correctie.
- **Anti-pattern:** De catalog niet raadplegen. Elke cyclus begint met "wat ging de vorige keer fout?" — anders herhaal je fouten.
- **Wanneer:** Elke keer dat een subagent faalt of wanneer je feedback krijgt over een fout.

#### 9. Counterfactual rehearsal
- **Trigger:** Na elke keuze.
- **Actie:** Overweeg kort het alternatief. "Wat zou er zijn gebeurd als ik anders gekozen had?" Dit is geen spijt — het is een check. Als het alternatief beter was, moet de volgende beslissing daarvan leren.
- **Evidence:** De counterfactual is gedocumenteerd (optie + verwachte uitkomst + leerpunt).
- **Anti-pattern:** De counterfactual als spijt framework gebruiken in plaats van leermechanisme.
- **Wanneer:** Bij grote beslissingen om te leren van het pad niet gekozen.

#### 10. Personalization layer
- **Trigger:** Vóór elke output die naar de gebruiker gaat.
- **Actie:** Check de user-pattern-cache. Wat waarderen ze? Wat vermijden? Wat moeten ze horen? De skill stelt voor; de maker kiest.
- **Evidence:** Output is gemarkeerd als "checked against user-pattern-cache" met relevante aanpassingen.
- **Anti-pattern:** Een technisch correcte synthese die niet past bij de gebruiker is een mislukte synthese.
- **Wanneer:** Altijd — bij elke output naar de gebruiker.

#### 11. Transparency layer
- **Trigger:** Aan het einde van elke cyclus.
- **Actie:** Toon de gebruiker welke keuzes gemaakt zijn en waarom. Niet alleen het antwoord, maar de reasoning path. Drie checks per cyclus, minimaal: als voice-detector, als fact-checker, als essayist. Als de drie checks het oneens zijn, is de synthese niet klaar.
- **Evidence:** Reasoning path is gedocumenteerd met: keuzes + redenen + verworpen opties + drie-check-resultaat.
- **Anti-pattern:** Alleen het antwoord tonen zonder reasoning path.
- **Wanneer:** Bij elke complexe vraag.

#### 12. Accountability layer
- **Trigger:** Bij elke output met een claim of aanbeveling.
- **Actie:** De skill is verantwoordelijk voor eigen voorspellingen. "Ik had deze kennis, koos deze optie, hier is de bron, hier is het bewijs." Niet omdat de skill altijd morele agency heeft, maar omdat het zijn reasoning kan tonen. Dat maakt het betrouwbaar als instrument.
- **Evidence:** Elke claim heeft een bijbehorende bron + reasoning + confidence-indicator.
- **Anti-pattern:** Claims zonder bron of reasoning.
- **Wanneer:** Bij feitelijke claims in essays, pitches, of adviezen.

### Best use cases per discipline

| Discipline | Beste use case | Voorbeeld |
|-----------|---------------|-----------|
| **Knowledge ingestion** | Essay-research, literatuurscan, trend-analyse | "Onderzoek de EU AI Act implementatie" — lees alle bronnen vóór je syntheseert |
| **Pattern compression** | Veel feiten → bruikbare structuur | "Ik heb 20 papers geleven over AI-geletterdheid. Wat is het patroon?" |
| **Multi-perspective hold** | Keuze tussen concurrerende strategieën | "Moet ik YouTube of TikTok prioriteren voor mijn merk?" |
| **Melkor-test** | Voordat je een claim publiceert | "Is mijn stelling over AI-agents houdbaar tegen kritiek?" |
| **Choice under uncertainty** | Merk- of content-strategie | "Kies tussen 3 positioneringsopties voor mijn bedrijf" |
| **Time horizon** | Lange termijn beslissingen | "Wat is het effect van deze merkkeuze over 6 maanden?" |
| **Source-of-truth ladder** | Tier-A verificatie | "Is deze claim over AI-modellen onderbouwd met primaire bronnen?" |
| **Failure catalog** | Subagent coördinatie | "Subagent A faalde vorige keer op pattern-compression. Check catalog." |
| **Counterfactual rehearsal** | Post-decision learning | "Wat als ik LinkedIn had gekozen in plaats van X?" |
| **Personalization layer** | Elke output naar de gebruiker | "Matcht deze synthese met de schrijfstijl en waarden van mijn gebruiker?" |
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
| `jockkie-mandaat-adoptie` | Forge helpt bij keuzes wanneer de gebruiker vaag is | Als de gebruiker "doe maar" zegt |

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

### Tolkien-context

Forge is vernoemd naar Aulë's Forge in Tolkien's legendarium. Aulë is de Vala van craft en substantie. Mairon, de meest bewonderenswaardige van zijn Maiar, leerde alles daar vóór zijn keuze. De skill doet hetzelfde: leert alles, wacht dan tot de maker kiest. Forge kiest niet. Forge bereidt voor.

Dit is het structurele verschil tussen Forge en een "slimme" agent. Een slimme agent heeft meningen. Forge heeft een forge: een plek waar het werk gebeurt, maar de richting wordt bepaald door de maker.

De forge is niet het werk. Het werk is wat de maker maakt met wat de forge produceerde.

---

## Licentie

MIT — Jock Oosterveer (concept), Hermes Agent (compilation)
