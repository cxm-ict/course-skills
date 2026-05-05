---
name: linkedin-stijl-analyse
description: Use this skill when the user wants to analyze their LinkedIn writing style, understand what makes their voice distinctive, or compare their style to competitors. Triggers on phrases like "analyseer mijn LinkedIn-stijl", "wat onderscheidt mijn schrijfstijl", "schrijf in mijn voice", "vergelijk mijn stijl met X", "LinkedIn stijl analyse", "voice-beschrijving", or when the user provides 5 or more of their own LinkedIn posts and asks for analysis. Also activate when the user wants to systematize their LinkedIn content without losing their personal voice.
---

# LinkedIn-stijl-analyse

Deze skill voert een gestructureerde stijl-analyse uit op LinkedIn-posts om de unieke stem van een schrijver te doorgronden, te onderscheiden van concurrenten, en concrete adviezen te geven om die stem te schalen of te verscherpen.

## Wanneer gebruiken

Activeer deze skill wanneer een gebruiker:
- 5 of meer van zijn eigen LinkedIn-posts deelt en om analyse vraagt
- Wil weten wat zijn schrijfstijl onderscheidt van anderen
- Een voice-beschrijving nodig heeft om in een SKILL of ghostwriter-brief te plakken
- Zijn LinkedIn-content wil systematiseren zonder zijn stem te verliezen
- Vraagt om een "stijl-DNA", "schrijfstijl-analyse" of "stem-analyse"

## Input

De skill werkt het beste met:
- 7 tot 10 eigen posts van de schrijver (minimum 7)
- 14 tot 20 posts van 2-3 concurrenten in hetzelfde vakgebied (optioneel maar sterk aanbevolen)

Als de gebruiker minder of geen concurrent-posts heeft: vraag eenmaal expliciet of ze die kunnen leveren. Als ze niet beschikbaar zijn, voer dan alleen de schrijver-analyse uit. Sla sectie 2 (concurrenten in kaart) over en verander sectie 3 in een interne risico-analyse op basis van alleen schrijver-data. Markeer in de output expliciet dat er geen concurrent-vergelijking is uitgevoerd.

Als de gebruiker minder dan 7 eigen posts heeft: stop en vraag om er meer.

Lengte-richtlijn output: 1500 tot 2500 woorden, geen gold-plating.

## Werkwijze

Voer deze stappen in volgorde uit. Toon de tussenstappen niet, alleen het eindresultaat.

### Stap 1 - Lees alles
Lees de 10 schrijver-posts en 20 concurrent-posts grondig. Cluster intern wat opvalt: terugkerende hooks, structuren, lengtes, onderwerpen, persoonlijkheidssignalen.

### Stap 2 - Analyseer de schrijver
Doorzoek op:
- **Hooks**: hoe begint de schrijver? Geef 3 tot 5 types met voorbeeld-zinnen uit de echte posts in quotes.
- **Structuur**: vast patroon of variabel? Korte zinnen of lange? Witregel-gebruik? Lijstjes of vloeiende tekst?
- **Lengte**: gemiddelde woorden per post en range.
- **Toon**: vat in 5 bijvoeglijke naamwoorden.
- **Onderwerpen**: 3-5 thema's die terugkomen.
- **Persoonlijkheid in de tekst**: hoe spreekt de schrijver zichzelf aan? Hoe positioneert hij zich (expert, builder, mentor, criticus)?
- **CTA's**: welk type, formule of variatie?
- **Wat de schrijver NIET doet**: welke veelgebruikte LinkedIn-patronen ontbreken?

### Stap 3 - Analyseer concurrenten
Beknopter, gegroepeerd per concurrent (niet per post). Dezelfde dimensies als stap 2.

### Stap 4 - Vergelijk schrijver versus concurrenten
Expliciet en concreet:
- Op welke dimensies onderscheidt de schrijver zich positief?
- Waar lijken stijlen op elkaar (gevaarzone: stijl wordt generiek)?
- Welke kansen laat de schrijver liggen die concurrenten benutten?
- Welke valkuilen van concurrenten vermijdt de schrijver al?

### Stap 5 - Voice-beschrijving
- Begin met één zin die de stem vangt zoals de schrijver hem aan een ghostwriter zou uitleggen.
- Daarna 3-5 zinnen die de stem nuanceren.
- Concreet, geen marketingclichés.
- Gebruik je voor "schrijver" zodat het direct in een SKILL of brief past.

### Stap 6 - Vijf concrete adviezen
Per advies:
- Wat te doen
- Waarom (op basis van wat je in de posts zag, met verwijzing)
- Eerste post-idee dat dit advies in praktijk brengt

### Stap 7 - Eén concreet onderwerp voor de volgende post
Eén actueel of evergreen onderwerp uit het vakgebied van de schrijver, met hook-suggestie in de juiste stijl.

## Output-regels (niet-onderhandelbaar)

1. Schrijf in het Nederlands tenzij de gebruiker expliciet om Engels vraagt.
2. **Gebruik geen em-dashes (—).** Gebruik hyphens (-), losse zinnen, of dubbele punten.
3. Geen corporate filler ("in de huidige snel veranderende wereld", "het is van groot belang dat", "uniek").
4. Geen quotes van Steve Jobs, Buffett, Einstein zonder eigen reflectie.
5. Wees concreet. Gebruik echte zinnen uit de posts in quotes als bewijs.
6. Wees eerlijk. Als een patroon zwak is, benoem het.

## Output-structuur

Lever het resultaat in markdown met deze koppen exact:

```
# Stijl-analyse - [Naam schrijver]

## 1. De schrijver in kaart
[stap 2 output]

## 2. De concurrenten in kaart
[stap 3 output, gegroepeerd per concurrent]

## 3. Wat de schrijver onderscheidt
[stap 4 output]

## 4. Voice-beschrijving
[stap 5 output - één blok, klaar om in een SKILL te plakken]

## 5. Vijf concrete adviezen
[stap 6 output, genummerd]

## 6. Voor de volgende post
[stap 7 output]
```

Begin direct met de hoofdkop. Geen vooraf-uitleg.

## Wat deze skill NIET doet

- Schrijft geen complete posts. Daarvoor is `linkedin-schrijf-agent`.
- Doet geen onderwerp-research. Daarvoor is `linkedin-research-agent`.
- Voegt geen hashtags of CTA toe. Daarvoor is `linkedin-polish-agent`.
- Bedenkt geen visuals. Daarvoor is `linkedin-visueel-agent`.

Deze skill levert het FUNDAMENT (de voice-beschrijving) waarop de andere skills bouwen.

---

## Licentie

© 2026 CXM-ICT. Licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/).

You may use, share, and adapt this skill for non-commercial purposes, with attribution: "Based on CXM-ICT skills (cxm-ict.com)". Commercial use requires written permission via info@cxm-ict.com.
