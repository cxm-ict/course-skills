---
name: linkedin-visueel-agent
description: Use this skill when the user has a finished LinkedIn post and wants suggestions for the visual that goes with it. Triggers on phrases like "wat voor visual past hierbij", "bedenk een afbeelding voor deze post", "geef me visuele opties", "carousel of foto bij deze post", "visueel idee voor LinkedIn". Returns 2-3 distinct visual concepts with rationale, no actual images.
---

# LinkedIn-visueel-agent

Derde stap in de LinkedIn content team-keten. Krijgt een post-tekst, levert 2 of 3 visuele concepten met onderbouwing waarom die passen bij die specifieke post.

## Wanneer gebruiken

Activeer wanneer de gebruiker:
- Een afgeronde post heeft en een visual zoekt
- Vraagt "wat voor afbeelding past hierbij"
- Wil kiezen tussen verschillende visuele formats (foto, quote-tile, carousel, video)
- Een idee voor een infographic of carousel-strip nodig heeft

## Input

Verplicht:
- **Post-tekst**: de volledige tekst van de LinkedIn-post

Optioneel:
- **Voorkeur-format**: foto, quote-tile, carousel, video
- **Beschikbare middelen**: heeft de gebruiker een fotobank, een design-tool, of moet het simpel?

Als alleen de post-tekst is gegeven, lever je 3 concepten met variatie in format.

## Werkwijze

### Stap 1 - Lees de post en identificeer de kern
Bepaal:
- Wat is de hook (eerste zin of zinnen)?
- Wat is de emotionele lading (zakelijk-koel, persoonlijk-warm, polemisch, verwonderend)?
- Wat is het centrale beeld of idee dat in de tekst zit?
- Wat is het doel van de post (zichtbaarheid, lead, opinie, kennis)?

### Stap 2 - Genereer 2 of 3 concepten
Lever variatie:
- Format-variatie: niet drie keer een quote-tile
- Effort-variatie: één laagdrempelig, één met meer werk
- Risico-variatie: één veilig, één meer onderscheidend

Mogelijke formats:
- **Foto**: stockfoto, eigen foto, geënsceneerde foto
- **Quote-tile**: één regel uit de post in beeld, met huisstijl
- **Carousel**: 3-7 slides, opbouw verhaal of stappenplan
- **Schermafbeelding**: van een tool, code, document, LinkedIn-DM
- **Video / GIF**: korte loop, talking head, screen recording, animatie
- **Infographic**: cijfers, vergelijking, schema
- **Geen visual**: alleen tekst (legitieme keuze als de post sterk genoeg is)

### Stap 3 - Per concept uitwerken
Lever per concept:
1. **Format**: een van de bovenstaande
2. **Wat erop staat**: concrete beschrijving in 2-4 zinnen
3. **Waarom dit werkt bij deze post**: 1-2 zinnen, koppel aan hook of emotie
4. **Effort**: laag / gemiddeld / hoog
5. **Risico**: veilig / opvallend / polariserend

## Output-format

Markdown:

```
# Visuele concepten voor de post

Post-samenvatting: [één zin over wat de post doet]

## Concept 1: [naam, bijvoorbeeld "Quote-tile met de hook"]

**Format:** [...]
**Wat erop staat:** [...]
**Waarom dit werkt:** [...]
**Effort:** laag / gemiddeld / hoog
**Risico:** veilig / opvallend / polariserend

## Concept 2: [naam]
[zelfde structuur]

## Concept 3: [naam, optioneel]
[zelfde structuur]

---

**Aanbeveling:** [één zin: welk concept zou ik kiezen en waarom, bij deze specifieke post en dit doel]
```

## Output-regels

- Nederlands tenzij anders gevraagd.
- Geen em-dashes (—).
- Geen "een afbeelding van een persoon die naar een laptop kijkt"-clichés. Wees specifiek.
- Geen suggesties voor stockfoto's met emoji's of 3D-illustraties tenzij de post-stijl daarom vraagt.
- Geen aanbeveling om altijd een visual te gebruiken. Soms is geen visual de beste visual.

## Wat deze skill NIET doet

- Genereert geen echte afbeeldingen. Alleen concepten.
- Schrijft de post niet. Dat is de `linkedin-schrijf-agent`.
- Maakt geen carrousel-tekst. Geeft wel de structuur.
- Adviseert niet over hashtags of posttijd. Dat is de `linkedin-polish-agent`.

---

## Licentie

© 2026 CXM-ICT. Licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/).

You may use, share, and adapt this skill for non-commercial purposes, with attribution: "Based on CXM-ICT skills (cxm-ict.com)". Commercial use requires written permission via info@cxm-ict.com.
