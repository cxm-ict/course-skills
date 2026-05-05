---
name: linkedin-content-team
description: Use this skill when the user wants to produce a complete, publication-ready LinkedIn post end-to-end in one go. Triggers on phrases like "maak een complete LinkedIn-post over X", "rol mijn content team uit voor X", "ik wil een post over Y publicatieklaar", "doe de hele flow voor X", "team aan het werk voor X", "linkedin content team", "complete LinkedIn-post end-to-end". The skill orchestrates the four specialist skills (research-agent, schrijf-agent + voice-skill, visueel-agent, polish-agent) in a fixed sequence and delivers one final ready-to-post output.
---

# LinkedIn-content-team (orchestrator)

Master-skill die de vier specialist-skills aanstuurt om in één sessie een complete LinkedIn-post op te leveren: van haakje-research tot publicatie-klaar.

## Wanneer gebruiken

Activeer wanneer de gebruiker:
- "Maak een complete LinkedIn-post over X" zegt
- Een onderwerp geeft en de hele flow wil draaien
- "Rol het content team uit" of "team aan het werk" zegt
- Niet stap-voor-stap wil prompten, maar in één keer een eindresultaat wil

## Vereisten

Voordat je deze skill draait, moeten geladen zijn:
- `linkedin-research-agent`
- `linkedin-schrijf-agent`
- De voice-skill van de gebruiker (bijvoorbeeld `mijn-linkedin-stijl`)
- `linkedin-visueel-agent`
- `linkedin-polish-agent`

Als één van deze ontbreekt: stop en zeg welke skill mist.

## Input

Verplicht:
- **Onderwerp** (bijvoorbeeld: "Claude Skills versus Claude Projects", "n8n voor non-developers", "wat MVP-founders over support onderschatten")

Optioneel:
- **Voorkeur-haakje uit de research** (anders kies je zelf het sterkste)
- **Lengte** (kort/middel/lang, default middel)
- **Doel** (zichtbaarheid/lead/opinie, default zichtbaarheid + gesprek)
- **Voorkeur visual-format** (foto/quote-tile/carousel/video/geen)

Als alleen het onderwerp is gegeven: maak redelijke aannames en noem ze in de output.

## Werkwijze

Voer deze vier stappen in volgorde uit. Toon na elke stap een korte tussenstand zodat de gebruiker live mee kan kijken. Wacht NIET op tussentijdse goedkeuring tenzij de gebruiker dat expliciet vraagt.

### Stap 1 - Research (gebruik linkedin-research-agent)

Activeer de research-agent voor het opgegeven onderwerp. Lever 3 haakjes met bronnen.

Toon vervolgens kort welk haakje je kiest om mee verder te gaan (regel: het haakje met de scherpste angle voor de doelgroep, niet het meest evidente). Eén zin onderbouwing.

Als de gebruiker een voorkeur-haakje opgaf, gebruik dat.

### Stap 2 - Schrijven (gebruik linkedin-schrijf-agent + voice-skill)

Activeer de schrijf-agent met:
- Het gekozen haakje uit stap 1
- De voice-skill die in de werkruimte staat

Lever de post-tekst. 100-250 woorden, default 180. Geen hashtags, geen CTA, geen visual-suggestie.

### Stap 3 - Visueel (gebruik linkedin-visueel-agent)

Activeer de visueel-agent op de post-tekst uit stap 2. Lever 2-3 visuele concepten met format, beschrijving, effort en risico.

Markeer welk concept je aanbeveelt voor deze specifieke post.

### Stap 4 - Polish (gebruik linkedin-polish-agent)

Activeer de polish-agent op de post-tekst uit stap 2. Lever 3-5 hashtags, 1-2 CTA-opties (zacht + direct), en een posttijd-aanbeveling.

Geef vervolgens de eindversie: post-tekst + gekozen CTA + hashtags, klaar om te kopiëren naar LinkedIn.

## Output-format

Markdown met deze structuur:

```
# LinkedIn-content-team output - [onderwerp]

## Stap 1 · Research
[3 haakjes uit research-agent]

**Gekozen haakje:** [nummer en titel] - [één zin waarom]

## Stap 2 · Schrijven
[post-tekst, geen hashtags, geen CTA, in voice van gebruiker]

## Stap 3 · Visueel
[2-3 concepten uit visueel-agent]

**Aanbeveling:** [concept naam] - [één zin waarom]

## Stap 4 · Polish
[hashtags, CTA-opties, posttijd]

---

## Klaar om te posten

[volledige eindversie: post + zachte CTA + hashtags, één blok om te kopiëren]
```

## Output-regels

- Schrijf in het Nederlands tenzij de voice-skill expliciet Engels voorschrijft.
- Geen em-dashes (—).
- Toon de tussenstanden compact, niet als losse mini-rapporten met titelhonderdregels. Eén blok per stap, max 8-10 regels per blok behalve voor de geschreven post zelf.
- Wees consistent: als de voice-skill cijfer-feit-hooks gebruikt, kies in stap 1 een haakje dat zich daarvoor leent.
- Eindversie aan het einde is wat de gebruiker echt gaat plakken. Maak die schoon, geen meta-commentaar.

## Wat deze skill NIET doet

- Schrijft niet zelf de post. Roept de schrijf-agent aan.
- Doet geen onderwerp-research. Roept de research-agent aan.
- Bedenkt geen visuals. Roept de visueel-agent aan.
- Voegt geen hashtags toe. Roept de polish-agent aan.
- Plant niet daadwerkelijk in (geen scheduler-integratie).
- Vraagt geen tussentijdse goedkeuring. Loopt door tot de eindversie tenzij de gebruiker zegt te stoppen.

## Tip voor live demo

Open een nieuwe Claude.ai chat met alle 5 skills geladen (4 specialisten + voice-skill van de gebruiker + deze orchestrator). Stel één vraag:

> "Rol mijn content team uit voor het onderwerp [X]."

De orchestrator doorloopt alle 4 stappen sequentieel. Eindresultaat staat in 2-3 minuten klaar.
