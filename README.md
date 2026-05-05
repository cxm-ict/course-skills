# course-skills

Materiaal bij de **Workshop AI & SKILLS** van CXM-ICT, 6 mei 2026 voor Twist Marketing.

Zeven skills die samen één workflow vormen: **van je eigen LinkedIn-stijl in kaart brengen tot één post in 5 minuten in plaats van 2 uur**.

---

## De zeven skills

| # | Skill | Wat het doet | Voor welk blok |
|---|-------|--------------|----------------|
| 1 | `linkedin-stijl-prompt` | Een lange prompt die jouw 10 posts + 20 concurrent-posts analyseert en je voice in kaart brengt | Blok 1 (wow-demo) |
| 2 | `linkedin-stijl-skill` | Dezelfde analyse als opgeslagen SKILL met YAML frontmatter | Blok 2 (concept) |
| 3 | `linkedin-stijl-template` | Werkblad waarmee jij in 30 minuten je eigen voice-skill bouwt | Blok 3 (zelf doen) |
| 4 | `linkedin-research-agent` | Vindt 3 actuele haakjes (angles) over een onderwerp met bronnen | Blok 4 (multi-agent) |
| 5 | `linkedin-schrijf-agent` | Schrijft post-tekst in jouw voice op basis van een haakje | Blok 4 |
| 6 | `linkedin-visueel-agent` | Bedenkt 2-3 visuele concepten bij een post | Blok 4 |
| 7 | `linkedin-polish-agent` | Voegt hashtags, CTA en posttijd toe en levert klaar-om-te-posten | Blok 4 |

---

## Snelstart

### Stap 1 - Clone deze repo

```
git clone https://github.com/cxm-ict/course-skills.git
cd course-skills
```

Of download als ZIP en pak uit waar je werkt.

### Stap 2 - Open Claude (Pro of hoger)

Je hebt **Claude Pro of hoger** nodig voor SKILLS-functionaliteit. Een gratis account werkt niet.

### Stap 3 - Installeer een skill

In de Claude desktop app of in claude.ai:

1. Ga naar **Settings → Capabilities → Skills**
2. Klik **Add Skill**
3. Upload de SKILL.md uit de map van de skill die je wilt gebruiken
4. De skill is meteen actief

Of, als je via Claude Code werkt: leg de hele map in `.claude/skills/` van je project.

### Stap 4 - Vraag iets dat de skill triggert

Voorbeeld voor `linkedin-stijl-skill`:

> "Hier zijn 10 van mijn LinkedIn-posts en 20 van twee concurrenten. Analyseer mijn stijl en geef me adviezen."

Voorbeeld voor `linkedin-schrijf-agent`:

> "Schrijf een LinkedIn-post over [haakje uit research-agent] in mijn stijl, gebruik mijn voice-skill."

---

## De aanbevolen volgorde voor de workshop

```
linkedin-stijl-prompt    ──┐
                           │  blok 1-2: jouw voice in kaart
linkedin-stijl-skill   ────┘

linkedin-stijl-template  ──── blok 3: jij bouwt je eigen skill

linkedin-research-agent  ──┐
linkedin-schrijf-agent   ──┤  blok 4: multi-agent content team
linkedin-visueel-agent   ──┤
linkedin-polish-agent    ──┘
```

---

## Mappenstructuur

```
course-skills/
├── README.md                                  ← jij bent hier
├── docs/
│   └── stappenplan.pdf                        ← take-home: zo ga je verder
└── skills/
    ├── linkedin-stijl-prompt/PROMPT.md
    ├── linkedin-stijl-skill/SKILL.md
    ├── linkedin-stijl-template/TEMPLATE.md
    ├── linkedin-research-agent/SKILL.md
    ├── linkedin-schrijf-agent/SKILL.md
    ├── linkedin-visueel-agent/SKILL.md
    └── linkedin-polish-agent/SKILL.md
```

---

## Veelgestelde vragen

**Werkt dit ook in de gratis Claude?**
Nee. SKILLS vereisen een betaald abonnement (Claude Pro of hoger).

**Werkt dit in ChatGPT?**
De skills zijn geschreven voor Claude. De prompts kun je in ChatGPT gebruiken, maar de SKILLS-functionaliteit (automatisch triggeren op basis van description) bestaat alleen in Claude.

**Mag ik deze skills aanpassen?**
Ja, sterker: je moet ze aanpassen. Vooral `linkedin-stijl-template` is bedoeld om te personaliseren. De andere zijn templates die je kunt strakker maken voor jouw vakgebied.

**Mag ik ze commercieel gebruiken?**
Ja. Geen attributie verplicht, wel waardering als je het deelt.

**Wat als een skill niet triggert?**
Check de description in de YAML frontmatter. Voeg jouw exacte trigger-zinnen toe ("schrijf in mijn voice" etc).

---

## Over CXM-ICT

CXM-ICT helpt founders die met AI een MVP hebben gebouwd om de stap naar schaalbare SaaS te maken. Pair- en review-gebaseerd, jij blijft de architect, AI bouwt uit. Inclusief security, deployment en documentatie.

Site: [cxm-ict.com](https://cxm-ict.com)
LinkedIn: [linkedin.com/in/michaeldoomen](https://linkedin.com/in/michaeldoomen)

## Gegeven door

- **Michael Doomen** - eigenaar CXM-ICT, 14+ jaar ervaring CCM/CXM, 8 jaar developer-ervaring, vibe-coder vanaf dag 1
- **Joost van der Heijden** - bouwer en vibe coder, AI-prototypes en tools

## Vragen of vastgelopen?

Stuur een DM via LinkedIn of mail info@cxm-ict.com.
