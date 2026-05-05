---
name: linkedin-schrijf-agent
description: Use this skill when the user wants to write a LinkedIn post based on a chosen angle (haakje) and their personal voice skill. Triggers on phrases like "schrijf een LinkedIn-post over X", "maak een post van dit haakje", "in mijn voice een post schrijven over Y", "schrijf in de stijl van mijn skill". The skill produces a polished post body without hashtags, CTA or visual suggestions, ready for the polish-agent.
---

# LinkedIn-schrijf-agent

Tweede stap in de LinkedIn content team-keten. Krijgt een haakje en een voice-beschrijving, levert een post-tekst van 100 tot 250 woorden in de juiste stem.

## Wanneer gebruiken

Activeer wanneer de gebruiker:
- Een onderwerp of haakje heeft (bijvoorbeeld uit `linkedin-research-agent`) en een post wil
- Vraagt om "schrijf een LinkedIn-post over X in mijn stijl"
- Een ruwe gedachte heeft en die wil omtoveren tot post-tekst
- Een bestaande post wil herschrijven in een andere voice

## Input

Verplicht:
- **Onderwerp of haakje**: één regel of een research-output uit `linkedin-research-agent`
- **Voice-skill of voice-beschrijving**: ofwel een SKILL die in de werkruimte staat (bijvoorbeeld `mijn-linkedin-stijl`), ofwel een blok tekst dat de stem beschrijft

Optioneel:
- **Lengte-voorkeur**: kort (~120 woorden), gemiddeld (~180), lang (~250). Default: gemiddeld.
- **Doel van de post**: zichtbaarheid, lead, opinie, kennis delen.

Als de voice-skill ontbreekt: stop en vraag erom. Schrijf nooit zonder voice-bron, anders levert dit een generieke post.

## Werkwijze

### Stap 1 - Lees de voice-bron grondig
Identificeer minimaal:
- Toon (5 bijvoeglijke naamwoorden)
- Hook-types die de schrijver gebruikt
- Wat de schrijver NIET doet (lijst uit voice-skill)
- Gemiddelde lengte
- CTA-stijl (al schrijf je geen CTA, je houdt rekening met de afsluitende toon)

### Stap 2 - Schrijf de post in dit ritme
1. **Hook (1-2 zinnen)**: kies het hook-type dat het beste bij dit haakje past
2. **Context of probleem (2-4 zinnen)**: waarom dit nu speelt of waarom de lezer hier last van heeft
3. **De wending of de inzicht (2-3 zinnen)**: jouw observatie, ervaring, of methode
4. **Concreet voorbeeld of klein detail (1-2 zinnen)**: maakt het tastbaar
5. **Afsluiting zonder CTA (1-2 zinnen)**: een open zin, een conclusie, of een PS

### Stap 3 - Self-check
Vergelijk de geschreven post met de voice-bron op:
- Zit de hook in een type dat de schrijver echt gebruikt?
- Staat er niets in de "wat ik niet doe"-lijst?
- Is de lengte binnen de range?
- Klopt de toon (lees het hardop in je hoofd)?

Pas aan als iets schuurt.

## Output-format

Lever alleen de post-tekst. Geen koppen, geen vooraf-uitleg, geen "Hier is je post:". Begin direct met de eerste zin van de post.

Lengte: 100-250 woorden, default ~180.

Witregels mag, sterker: meestal moet, want LinkedIn leest beter met witregels tussen alinea's.

## Output-regels

- Nederlands tenzij voice-skill expliciet Engels voorschrijft
- **Geen em-dashes (—)**. Hyphens, dubbele punten, losse zinnen.
- Geen hashtags (komt later)
- Geen CTA met "DM mij", "Reageer met X", "👉 link" (komt later)
- Geen visual-beschrijving (komt later)
- Geen emoji's tenzij de voice-skill ze noemt als onderdeel van de stijl
- Geen "Lees verder ↓" trucs
- Geen quotes van Steve Jobs, Buffett, Einstein zonder eigen reflectie

## Wat deze skill NIET doet

- Voegt geen hashtags of CTA toe. Dat is de `linkedin-polish-agent`.
- Bedenkt geen visual. Dat is de `linkedin-visueel-agent`.
- Doet geen onderwerp-research. Dat is de `linkedin-research-agent`.
- Schrijft geen carrousel-teksten of meerdere varianten. Eén post per run.
