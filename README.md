# 🎩 Mafia Claude Skills

Een verzameling Claude Skills om je AI-workflows te verbeteren.

![Mafia Claude Skills](mafia_claude_skills.png)

[![Licentie](https://img.shields.io/badge/Licentie-Apache%202.0-blue.svg)](LICENSE)
[![Bijdragen Welkom](https://img.shields.io/badge/Bijdragen-Welkom-brightgreen.svg)](CONTRIBUTING.md)

---

## 📖 Wat zijn Claude Skills?

**Skills** zijn mappen met instructies, scripts en bronnen die Claude dynamisch laadt om zijn prestaties bij gespecialiseerde taken te verbeteren. Een skill leert Claude hoe hij specifieke taken op een herhaalbare en nauwkeurige manier kan uitvoeren.

Voorbeelden van wat skills kunnen doen:
- 📊 Gegevens analyseren volgens specifieke workflows
- 📝 Documenten maken met de stijlgidsen van je bedrijf
- 🔢 Nauwkeurige berekeningen uitvoeren met Python-scripts
- 🤖 Aangepaste taken automatiseren

**Meer officiële informatie:**
- [Wat zijn skills? Spaanse gids](https://aimafia.substack.com/p/skills-ia)
- [Officiële Claude skills documentatie](https://support.claude.com/en/articles/12512176-what-are-skills)
- [Skills gebruiken in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [Aangepaste skills maken](https://support.claude.com/en/articles/12512198-creating-custom-skills)

---

## 📋 Skills Index

| Skill | Beschrijving | Categorie |
|-------|--------------|-----------|
| [**Gestor Autónomos**](./skills/gestor-autonomos/) | Boekhoudkundig en fiscaal beheer voor zzp'ers in Spanje. Berekening van BTW, inkomstenbelasting (IRPF), Stripe/Substack verwerking. | 💼 Financiën |
| [**Landing Page Mastery**](./skills/landing-page-mastery/) | Expertsysteem voor het maken en optimaliseren van high-converting landingspagina's (SaaS, cursussen, ebooks). | 🎨 Marketing |
| [**Vercel React Best Practices**](./skills/vercel-react-best-practices/) | Prestatie-optimalisatiegidsen voor React en Next.js onderhouden door Vercel. (Gesynchroniseerde externe skill) | ⚡ Ontwikkeling |
| [**Frontend Design**](./skills/frontend-design/) | Creëert onderscheidende, productieklare frontend-interfaces met een hoge ontwerpkwaliteit. (Skill van Anthropic) | 🎨 Ontwerp |
| [**Frontier Plan OpenCode Executor**](./skills/frontier-plan-opencode-executor/) | Voert implementatieplannen van frontier AI veilig en gestructureerd uit. *(Gesynchroniseerde externe skill)* | 🤖 Agenten |
| [**Agent Browser**](./skills/agent-browser/) | Browserautomatisering voor interactie met websites, gegevensextractie en testen. | 🌐 Web |
| [**Audio Transcriber**](./skills/audio-transcriber/) | Zet audio-opnames om in Markdown-documentatie met samenvattingen. *(Bron: community)* | 🎙️ Audio |
| [**Decision Toolkit**](./skills/decision-toolkit/) | Hulpmiddelen voor besluitvorming, stapsgewijze gidsen en scenarioverkenning. | 🧠 Productiviteit |
| [**Deep Research**](./skills/deep-research/) | Diepgaand onderzoek naar elk onderwerp met zoekopdrachten op het web en uitgebreide analyse. | 🔍 Onderzoek |
| [**Fact Checker**](./skills/fact-checker/) | Verifieert gegevens, feiten en beweringen om de nauwkeurigheid van de informatie te garanderen. | ✅ Verificatie |
| [**File Organizer**](./skills/file-organizer/) | Organiseert bestanden, verwijdert duplicaten en stelt betere mappenstructuren voor. | 📁 Hulpprogramma's |
| [**Find Skills**](./skills/find-skills/) | Ontdekt en installeert nieuwe agent skills in antwoord op gebruikersbehoeften. | ⚙️ Hulpprogramma's |
| [**Frontend Slides**](./skills/frontend-slides/) | Maakt geanimeerde HTML-presentaties of converteert PowerPoint-bestanden. *(Bron: ECC)* | 📊 Presentaties |
| [**Humanizer**](./skills/humanizer/) | Transformeert en humaniseert de toon van door AI gegenereerde teksten zodat ze natuurlijk klinken. | ✍️ Copywriting |
| [**MCP Builder**](./skills/mcp-builder/) | Gids voor het bouwen van MCP (Model Context Protocol) servers in Python en TypeScript. | 🛠️ Ontwikkeling |
| [**OpenRouter**](./skills/openrouter/) | Uniforme integratie met de OpenRouter API om meer dan 400 AI-modellen te gebruiken. | 🔌 API |
| [**Process Interviewer**](./skills/process-interviewer/) | Deskundige interviewer die concrete plannen uit het hoofd van de gebruiker haalt voordat deze gaat bouwen. | 📝 Planning |
| [**Prompt Master**](./skills/prompt-master/) | Genereert ultra-geoptimaliseerde prompts voor elke AI-tool of -model. | 💬 Prompts |

---

## 🚀 Hoe de Skills te gebruiken

### In Claude.ai

1. Ga naar **Settings** → **Skills**
2. Klik op **"Add skill"**
3. Je kunt:
   - **Handmatig uploaden**: Download de skill-map en upload deze
   - **Via URL**: Gebruik de URL van het `SKILL.md` bestand op GitHub

### In Claude Code

```bash
# Kloon de repository
git clone https://github.com/alexdcd/Mafia-Claude-Skills.git

# Voeg de skill toe aan je project
claude skill add ./Mafia-Claude-Skills/skills/gestor-autonomos
```

### Via Claude API

Neem de inhoud van de skill op in de system prompt of als extra context in je API-aanroep.

---

## 📂 Repository Structuur

```
Mafia-Claude-Skills/
├── .github/                   # Issue en Pull Request templates
├── skills/                    # Hoofdmap die alle skills bevat
│   ├── naam-van-de-skill/     # Individuele map voor elke skill
│   │   ├── SKILL.md           # Verplicht bestand met instructies (YAML + Markdown)
│   │   ├── scripts/           # (Optioneel) Ondersteunende scripts (Python, etc.)
│   │   └── references/        # (Optioneel) Referentiedocumentatie
├── README.md                  # Hoofddocumentatie
├── CONTRIBUTING.md            # Gids voor bijdragers
└── LICENSE                    # Projectlicentie
```

---

## 🔧 Beschikbare Skills

### 💼 Gestor Autónomos España (Zzp'er Beheerder Spanje)

> **Boekhoudkundig en fiscaal beheer voor zzp'ers (autónomos) in Spanje.**

Een complete skill voor het beheren de boekhouding en belastingen van zzp'ers met wiskundig nauwkeurige berekeningen.

> [!CAUTION]
> **WAARSCHUWING**: Deze skill is een hulpmiddel en is geen vervanging voor professioneel advies. De gegenereerde berekeningen en suggesties moeten worden gecontroleerd door een accountant of gekwalificeerde professional. Het gebruik van dit hulpmiddel is uitsluitend de verantwoordelijkheid van de gebruiker. Mafia Claude Skills en de bijdragers zijn niet verantwoordelijk voor fouten in belastingaangiften of boetes die voortvloeien uit het gebruik ervan.

**Kenmerken:**

| Functie | Beschrijving |
|---------|--------------|
| 📊 Model 303 (BTW/IVA) | Automatische berekening van kwartaal-BTW |
| 📈 Model 130 (IRPF) | Berekening van voorlopige inkomstenbelasting |
| 🧾 Facturen | Verwerking en validatie van facturen |
| 💳 Stripe/Substack | Verwerking van digitale inkomsten |
| 📚 Boekhoudboek | Genereren van inkomsten/uitgavenboek |
| 📖 Regelgeving | Referentie naar Spaanse belastingwetgeving |

**Gebruiksvoorbeeld:**

```
Gebruiker: Ik moet de BTW berekenen voor Q3 2024. 
         Ik heb € 12.000 gefactureerd en heb € 3.500 aan aftrekbare kosten.

Claude: [Gebruikt Gestor Autónomos] Berekening uitvoeren...

📊 MODEL 303 - Q3 2024
━━━━━━━━━━━━━━━━━━━━━━
Belastbare grondslag: 12.000,00 €
Berekende BTW:         2.520,00 € (21%)

Aftrekbare kosten:     3.500,00 €
Voorbelasting BTW:       735,00 € (21%)

━━━━━━━━━━━━━━━━━━━━━━
💰 BTW TE BETALEN:     1.785,00 €

📅 Deadline: 1-20 Oktober 2024
```

**Skill structuur:**

```
gestor-autonomos/
├── SKILL.md           # Instructies en fiscale logica
├── scripts/           # Berekeningslogica in Python
│   ├── calcular_iva.py
│   ├── calcular_irpf.py
│   ├── procesar_facturas.py
│   ├── procesar_stripe.py
│   └── generar_libro.py
└── references/        # Documentatie van de belastingdienst (AEAT)
    └── normativa_fiscal.md
```

➡️ [Bekijk volledige documentatie](./skills/gestor-autonomos/SKILL.md)

---

### 🎨 Landing Page Mastery

> **Expertsysteem voor het maken en optimaliseren van high-converting landingspagina's.**

Een skill ontworpen voor marketeers en oprichters die effectieve verkooppagina's moeten maken of bestaande pagina's moeten verbeteren op basis van data en gebruikerspsychologie.

**Kenmerken:**

| Functie | Beschrijving |
|---------|--------------|
| 🏗️ Structuren | Bewezen sjablonen voor SaaS, Cursussen, Ebooks en Nieuwsbrieven |
| ✍️ Copywriting | Genereren van teksten met frameworks (PAS, AIDA, STAR) |
| 🔍 Audit | 100-punten checklist om conversies te optimaliseren |
| 🎨 Ontwerp | UX/UI, kleur- en typografiegidsen gericht op conversie |
| 📊 Benchmarks | Vergelijking met marktstatistieken (2026) |

**Use cases:**
- Een landingspagina vanaf nul maken voor een nieuwe SaaS.
- Een pagina auditen die niet goed converteert.
- Verkoopteksten schrijven.

**Skill structuur:**

```
landing-page-mastery/
├── SKILL.md           # Instructies en workflows
└── references/        # Expert kennisbank
    ├── structures.md      # Structuren per producttype
    ├── copywriting.md     # Copywriting formules
    ├── design.md          # Visuele gidsen
    ├── audit-checklist.md # Stapsgewijze audit
    └── conversion-elements.md # Conversie-elementen
```

➡️ [Bekijk volledige documentatie](./skills/landing-page-mastery/SKILL.md)

---

### 🎨 Frontend Design

> **Creëert onderscheidende, productieklare frontend-interfaces met een hoge ontwerpkwaliteit.**

Een skill van Anthropic ontworpen om de creatie van interfaces te sturen die generieke AI-esthetiek vermijden en kiezen voor gedurfde, gedenkwaardige en verfijnde ontwerpen.

**Kenmerken:**

| Functie | Beschrijving |
|---------|--------------|
| 🖋️ Typografie | Selectie van unieke en karaktervolle lettertypen |
| 🎨 Kleur en Thema's | Cohesieve paletten en gedefinieerde accenten |
| ✨ Animatie | Micro-interacties en high-impact bewegingen |
| 📐 Compositie | Onverwachte lay-outs en creatief gebruik van ruimte |
| 🌫️ Texturen | Achtergronden met diepte en moderne visuele effecten |

**Wanneer deze skill te gebruiken:**
- Bij het bouwen van webcomponenten, landingspagina's of dashboards.
- Om een bestaande interface te "verfraaien".
- Wanneer je op zoek bent naar een premium ontwerp dat niet door AI gegenereerd lijkt te zijn.

**Skill structuur:**

```
frontend-design/
├── SKILL.md           # Instructies en ontwerpprincipes
└── LICENSE.txt        # Apache 2.0 Licentie
```

➡️ [Bekijk volledige documentatie](./skills/frontend-design/SKILL.md)

---

### 🤖 Frontier Plan OpenCode Executor

> **Voert implementatieplannen van frontier AI veilig en gestructureerd uit in OpenCode.**

Een gesynchroniseerde externe skill om complexe plannen van modellen zoals Claude Opus stapsgewijs te valideren en uit te voeren, waarbij continue verificatie tegen de daadwerkelijke repository wordt afgedwongen.

**Kenmerken:**

| Functie | Beschrijving |
|---------|--------------|
| 🔎 Validatie | Controleert de status van de repository voor uitvoering |
| 🛡️ Beveiliging | Voorkomt destructieve commando's en ongewenste installaties |
| 🔄 Stapsgewijze Uitvoering | Dwingt het model om stap voor stap uit te voeren en te verifiëren |
| 👀 Diffs Inspectie | Beoordeelt de werkelijke grootte en reikwijdte van elke wijziging |

**Wanneer deze skill te gebruiken:**
- Bij ontvangst van een gedetailleerd implementatieplan van een groot model (bijv. Claude Opus/GPT-5).
- Om kleinere modellen te dwingen gedisciplineerd en veilig te werken.

**Skill structuur:**

```
frontier-plan-opencode-executor/
├── SKILL.md           # Workflow, verificaties en instructies
└── README.md          # Algemene documentatie van de skill
```

➡️ [Bekijk volledige documentatie](./skills/frontier-plan-opencode-executor/SKILL.md)

---

### 🌐 Agent Browser
> **Browserautomatisering voor interactie met websites en gegevensextractie.**

Communiceert met webpagina's, vult formulieren in, maakt screenshots en voert geautomatiseerd webtesten uit.
➡️ [Bekijk volledige documentatie](./skills/agent-browser/SKILL.md)

---

### 🎙️ Audio Transcriber
> **Zet opnames om in professionele Markdown-documentatie.** *(Bron: community)*

Verwerkt audio om gestructureerde transcripties en intelligente samenvattingen te genereren via LLM's.
➡️ [Bekijk volledige documentatie](./skills/audio-transcriber/SKILL.md)

---

### 🧠 Decision Toolkit
> **Gestructureerde hulpmiddelen voor besluitvorming.**

Genereert stapsgewijze gidsen, bias-detectoren en scenario-verkenningen om belangrijke opties systematisch te analyseren.
➡️ [Bekijk volledige documentatie](./skills/decision-toolkit/SKILL.md)

---

### 🔍 Deep Research
> **Uitgebreid onderzoek naar elk onderwerp met behulp van de Deep Research API.**

Automatiseert de verbetering van zoekprompts en voert diepgaande analyses uit met webtoegang.
➡️ [Bekijk volledige documentatie](./skills/deep-research/SKILL.md)

---

### ✅ Fact Checker
> **Verifieert feiten en beweringen.**

Controleert gegevens en informatie om hun waarheid en nauwkeurigheid te garanderen voorafgaand aan publicatie of gebruik.
➡️ [Bekijk volledige documentatie](./skills/fact-checker/SKILL.md)

---

### 📁 File Organizer
> **Slimme bestands- en directory-organisator.**

Begrijpt de context van je bestanden, vindt duplicaten en stelt geordende structuren voor je digitale werkruimte voor.
➡️ [Bekijk volledige documentatie](./skills/file-organizer/SKILL.md)

---

### ⚙️ Find Skills
> **Ontdekken en installeren van nieuwe vaardigheden (skills).**

Maakt het mogelijk om dynamisch skills te zoeken en te installeren wanneer je vraagt hoe je een specifieke taak met agenten moet uitvoeren.
➡️ [Bekijk volledige documentatie](./skills/find-skills/SKILL.md)

---

### 📊 Frontend Slides
> **Maken van animatie-rijke HTML presentaties.** *(Bron: ECC)*

Bouwt dia's vanaf nul op of converteert PowerPoint-presentaties eenvoudig naar het web.
➡️ [Bekijk volledige documentatie](./skills/frontend-slides/SKILL.md)

---

### ✍️ Humanizer
> **Geef je teksten een menselijk tintje.**

Past en verbetert door AI gegenereerde tekst aan om de "robotstem" te elimineren en het persoonlijker en natuurlijker te maken.
➡️ [Bekijk volledige documentatie](./skills/humanizer/SKILL.md)

---

### 🛠️ MCP Builder
> **Gids voor het maken van hoogwaardige Model Context Protocol (MCP) servers.**

Helpt bij de ontwikkeling van MCP-tools met Python (FastMCP) of TypeScript/Node om externe API's te integreren met LLM's.
➡️ [Bekijk volledige documentatie](./skills/mcp-builder/SKILL.md)

---

### 🔌 OpenRouter
> **Uniforme toegang tot AI-modellen via OpenRouter.**

Communiceer met een enorme verscheidenheid aan modellen (meer dan 400) door de OpenRouter API eenvoudig te integreren.
➡️ [Bekijk volledige documentatie](./skills/openrouter/SKILL.md)

---

### 📝 Process Interviewer
> **Meedogenloze interviewer om plannen te extraheren en te concretiseren.**

Voordat je gaat bouwen, interviewt deze agent je om je ideeën te verduidelijken, dubbelzinnigheden weg te nemen en een robuust actieplan te genereren.
➡️ [Bekijk volledige documentatie](./skills/process-interviewer/SKILL.md)

---

### 💬 Prompt Master
> **Geoptimaliseerde promptgenerator voor elke AI-tool.**

Maakt of past perfecte prompts aan voor ChatGPT, Cursor, Midjourney, videotools en elke LLM of agent.
➡️ [Bekijk volledige documentatie](./skills/prompt-master/SKILL.md)

---

## 🤝 Bijdragen

Bijdragen zijn welkom! Dit is een open source project en we zouden het leuk vinden als je je eigen skills deelt.

### Manieren om bij te dragen:

1. **🐛 Bugs melden**: Open een [issue](https://github.com/alexdcd/Mafia-Claude-Skills/issues) waarin je het probleem beschrijft
2. **💡 Verbeteringen voorstellen**: Stel nieuwe functies of skills voor
3. **🔧 Pull Requests sturen**: Verbeter bestaande skills of voeg nieuwe toe
4. **📝 Documentatie verbeteren**: Help om instructies duidelijker te maken

### Hoe voeg je een nieuwe skill toe:

```bash
# 1. Fork en kloon de repo
git clone https://github.com/alexdcd/Mafia-Claude-Skills.git

# 2. Maak een nieuwe map aan voor je skill
mkdir -p skills/mijn-nieuwe-skill

# 3. Voeg de vereiste bestanden toe
touch skills/mijn-nieuwe-skill/SKILL.md

# 4. Maak een PR aan
```

Lees de [bijdragegids](CONTRIBUTING.md) voor meer details.

### Hoe externe skills te synchroniseren:

Deze repository bevat een systeem om skills uit andere repositories te synchroniseren (zoals Vercel Best Practices).

1. **Configuratie**: Externe skills worden gedefinieerd in `data/external-skills.json`.
2. **Synchronisatie**: Om deze skills bij te werken of te installeren, voer je uit:

```bash
# Vereist Python 3
python3 scripts/sync_skills.py
```

Dit downloadt de nieuwste versie van de skills die in het JSON-bestand zijn gedefinieerd. Je kunt dit mechanisme gebruiken om je repository up-to-date te houden met best practices in de industrie.

---

## 📏 Skill Sjabloon

Gebruik dit sjabloon om nieuwe skills te maken:

```markdown
---
name: naam-van-mijn-skill
description: >
  Duidelijke beschrijving van wat deze skill doet en wanneer je deze moet gebruiken.
  Wees specifiek over de use cases.
---

# Naam van Mijn Skill

Gedetailleerde beschrijving van de skill en zijn mogelijkheden.

## Wanneer deze skill te gebruiken

- Use case 1
- Use case 2
- Use case 3

## Instructies

[Gedetailleerde instructies voor Claude over hoe deze skill moet worden uitgevoerd]

## Voorbeelden

[Echte voorbeelden die de skill in actie laten zien]
```

---

## 📚 Bronnen

### Officiële documentatie
- [Anthropic - Skills Repository](https://github.com/anthropics/skills)
- [Claude Help Center](https://support.claude.com)
- [Claude API](https://docs.anthropic.com)

### Community
- [La Mafia IA](https://aimafia.substack.com/)

---

## 📄 Licentie

Dit project is gelicentieerd onder de [Apache 2.0 Licentie](LICENSE).

De inbegrepen skills zijn vrij te gebruiken voor persoonlijke en commerciële doeleinden, onderworpen aan de voorwaarden van de licentie.

---

## ✨ Gemaakt door

**MAFIA IA** - Het creëren van nuttige tools voor de Spaanstalige (en nu ook Nederlandstalige) AI-gemeenschap.

---

<div align="center">

**Vond je het nuttig?** ⭐ Geef de repository een ster

[Meld een Bug](https://github.com/alexdcd/Mafia-Claude-Skills/issues/new?template=bug-report.md) · [Stel een Skill voor](https://github.com/alexdcd/Mafia-Claude-Skills/issues/new?template=nueva-skill.md) · [Bijdragen](CONTRIBUTING.md)

</div>
