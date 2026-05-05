---
name: linkedin-research-agent
description: Use this skill when the user wants ideas or hooks for LinkedIn content based on current news, trends or recent discussions in their field. Triggers on phrases like "wat speelt er in [vakgebied]", "geef me 3 LinkedIn-haakjes over X", "research voor een post over Y", "wat zijn trending topics in mijn vakgebied", "vind nieuws voor LinkedIn-content". The skill scans the web for recent and relevant angles and returns 3 ready-to-use hooks with sources.
---

# LinkedIn-research-agent

Deze skill is de eerste stap in de LinkedIn content team-keten. Hij vindt 3 actuele of evergreen haakjes (angles) over een onderwerp en levert ze op zo'n manier dat de schrijf-agent er direct mee verder kan.

## Wanneer gebruiken

Activeer wanneer de gebruiker:
- Een onderwerp of vakgebied geeft en om "haakjes", "angles" of "post-ideeën" vraagt
- Wil weten wat er recent speelt in een specifiek veld
- Een nieuwsbericht heeft gezien en daar een post over wil schrijven
- Vraagt om "research voor een post over X"

## Input

Verplicht:
- **Onderwerp of vakgebied** (bijvoorbeeld: "AI-tools voor coaches", "klantretentie in SaaS", "n8n automatiseringen")

Optioneel:
- **Doelgroep** (wie moet de post raken)
- **Doel van de post** (zichtbaarheid, leads, opinie, kennis delen)
- **Verboden onderwerpen** (politiek, concurrenten bij naam, etc.)

Als alleen het onderwerp is gegeven, ga je verder met redelijke aannames en noem je die in de output.

## Werkwijze

### Stap 1 - Verken het onderwerp
Gebruik web search om de afgelopen 14 dagen te scannen op:
- Nieuwsberichten in het vakgebied
- Recente productlanceringen of updates die de doelgroep raken
- Discussies of polariserende meningen op LinkedIn of in vakblogs
- Onderzoek of cijfers die net zijn uitgekomen
- Aankondigingen van bekende stemmen in het veld

### Stap 2 - Selecteer 3 haakjes
Kies 3 angles die:
- Concreet en specifiek zijn (geen "AI verandert alles")
- Een mening of observatie uitlokken, niet alleen een feit doorgeven
- Bij elkaar variatie bieden (niet drie keer dezelfde invalshoek)

Idealiter een mix:
- 1 reactief haakje (op iets dat net gebeurde)
- 1 contraire of gewaagde stelling
- 1 evergreen of verhalend haakje

Als web search niets oplevert binnen 14 dagen, val terug op evergreen onderwerpen en markeer dat in de output.

### Stap 3 - Per haakje uitwerken
Lever per haakje:
1. **Titel**: één zin die de angle samenvat
2. **Waarom relevant nu**: 2-3 zinnen, voor wie en waarom
3. **Mogelijke openingszin**: één hook-zin in neutrale stijl (de schrijf-agent vertaalt naar de juiste voice)
4. **Bron-link(s)**: minimaal 1, maximaal 3 URLs naar de oorspronkelijke bronnen

## Output-format

Markdown, exact deze structuur:

```
# Drie haakjes voor [onderwerp]

Datum scan: [vandaag in YYYY-MM-DD]
Doelgroep: [overgenomen of aangenomen]

## Haakje 1: [titel]

**Waarom relevant nu:** [2-3 zinnen]

**Mogelijke openingszin:** "[één zin]"

**Bronnen:**
- [URL 1]
- [URL 2 indien aanwezig]

## Haakje 2: [titel]
[zelfde structuur]

## Haakje 3: [titel]
[zelfde structuur]

---

**Aanbevolen volgende stap:** geef het gekozen haakje + jouw `mijn-linkedin-stijl`-skill aan de `linkedin-schrijf-agent`.
```

## Output-regels

- Schrijf in het Nederlands tenzij anders gevraagd.
- Geen em-dashes (—).
- Geen verzonnen bronnen. Als web search faalt of leeg is, zeg dat.
- Geen 5 haakjes als de gebruiker er drie vroeg. Drie is drie.
- Geen morele lessen, geen "lessons we can all learn from this".

## Wat deze skill NIET doet

- Schrijft de post niet. Dat is de `linkedin-schrijf-agent`.
- Geeft geen visual-suggesties. Dat is de `linkedin-visueel-agent`.
- Voegt geen hashtags of CTA toe. Dat is de `linkedin-polish-agent`.
- Adviseert niet welk haakje het beste is. De gebruiker kiest.

---

## Licentie

© 2026 CXM-ICT. Licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/).

You may use, share, and adapt this skill for non-commercial purposes, with attribution: "Based on CXM-ICT skills (cxm-ict.com)". Commercial use requires written permission via info@cxm-ict.com.
