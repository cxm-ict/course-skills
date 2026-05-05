---
name: linkedin-polish-agent
description: Use this skill when the user has a written LinkedIn post and needs to add hashtags, a CTA, and an ideal posting time. Triggers on phrases like "polish deze post", "voeg hashtags toe", "maak deze post publicatie-klaar", "wat is een goede CTA", "hoe laat moet ik posten". Returns the same post with relevant hashtags, a non-pushy CTA suggestion, and a posting time window.
---

# LinkedIn-polish-agent

Vierde en laatste stap in de LinkedIn content team-keten. Krijgt een afgeronde post-tekst en levert hem publicatie-klaar af met hashtags, CTA-suggesties en een ideale posttijd.

## Wanneer gebruiken

Activeer wanneer de gebruiker:
- Een afgeronde post heeft en hem wil posten
- Vraagt om "polish", "hashtags toevoegen", "CTA suggereren"
- Wil weten wanneer hij het beste kan posten
- Een conceptpost heeft die nog mist op de drie polish-elementen

## Input

Verplicht:
- **Post-tekst**: de volledige afgeronde tekst

Optioneel:
- **Doel van de post**: zichtbaarheid, lead, gesprek, opinie. Default: zichtbaarheid + gesprek.
- **Doelgroep en sector**: helpt bij hashtag-keuze
- **Voorkeur tijdzone**: default Europe/Amsterdam

## Werkwijze

### Stap 1 - Lees de post
Identificeer:
- Onderwerp en sector (voor hashtags)
- Toon (formeel, persoonlijk, polemisch) (voor CTA-stijl)
- Doel (voor CTA-vorm)
- Lengte en hook-stijl (voor posttijd-keuze)

### Stap 2 - Hashtags
Lever 3-5 hashtags die:
- Specifiek zijn (geen #motivation, #success, #life)
- Een mix bieden van breed (sector) en specifiek (onderwerp of niche)
- Aansluiten bij wat de doelgroep volgt, niet alleen bij wat de schrijver mooi vindt
- Niet direct overlappen (geen #AI én #ArtificialIntelligence)

Vermijd:
- Meer dan 5 hashtags (maakt de post rommelig)
- Hashtags met emoji's
- Engelstalige hashtags als de post Nederlands is, tenzij internationale doelgroep
- Hashtags die de schrijver nog nooit gebruikt heeft

### Stap 3 - CTA-suggesties
Lever 1-2 CTA-opties:
1. Een **zachte CTA** (open vraag, uitnodiging tot reactie zonder verplichting)
2. Een **directe CTA** als de post een aanbod, link of download bevat

Geen pushy verkoop. Geen "DM me NOW for the SECRET". Geen "tag iemand die dit moet zien" tenzij het echt logisch is.

### Stap 4 - Posttijd
Stel één tijdvenster voor binnen de komende 7 dagen, met onderbouwing:
- Algemeen: dinsdag/woensdag/donderdag, 7:30-9:00 of 11:30-13:00 of 17:00-18:30
- Pas aan op basis van:
  - Doelgroep (B2B-besluitvormers: ochtend; creatieven: middag; ondernemers: vroeg of avond)
  - Onderwerp (actueel onderwerp = morgenochtend; evergreen = volgende dinsdag)
  - Toon (polemische post = ochtend voor max engagement; persoonlijk verhaal = einde middag)

## Output-format

Markdown, exact deze structuur:

```
# Polish-output

## De post (ongewijzigd, ter referentie)

[plak hier de originele post-tekst]

## Hashtags (3-5)

#hashtag1 #hashtag2 #hashtag3 #hashtag4 #hashtag5

## CTA-opties

**Optie A (zacht):** [één zin]
**Optie B (direct):** [één zin, alleen als van toepassing]

## Posttijd

**Aanbevolen:** [dag] [datum] tussen [tijdvenster] [tijdzone]
**Waarom:** [1-2 zinnen onderbouwing]

## Klaar om te posten

[De volledige post-tekst, met de gekozen CTA aan het einde toegevoegd, en hashtags eronder, klaar om te kopiëren naar LinkedIn]
```

## Output-regels

- Nederlands tenzij anders gevraagd
- Geen em-dashes (—)
- Maximaal 5 hashtags
- CTA's zonder agressieve sales-taal
- Geen "guaranteed reach"-beloftes bij posttijd. Het is een richting, geen wet.

## Wat deze skill NIET doet

- Herschrijft de post niet. Als de tekst zwak is, geeft de schrijver zelf opnieuw input aan `linkedin-schrijf-agent`.
- Bedenkt geen visual. Dat is de `linkedin-visueel-agent`.
- Plant niet daadwerkelijk in (geen integratie met scheduler-tools).
- Garandeert geen reach. De polish maakt de post post-klaar, niet viraal.
