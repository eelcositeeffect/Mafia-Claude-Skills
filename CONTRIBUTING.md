# 🤝 Bijdragegids

Bedankt voor je interesse om bij te dragen aan Mafia Claude Skills! Dit document helpt je op weg met hoe je kunt deelnemen aan het project.

## 📋 Inhoudsopgave

- [Gedragscode](#gedragscode)
- [Hoe Bij te Dragen](#hoe-bij-te-dragen)
- [Een Nieuwe Skill Maken](#een-nieuwe-skill-maken)
- [Structuur van een Skill](#structuur-van-een-skill)
- [Best Practices](#best-practices)
- [Pull Requests](#pull-requests)

---

## 📜 Gedragscode

Dit project volgt een gedragscode gebaseerd op wederzijds respect:

- Wees respectvol en constructief
- Accepteer kritiek op een positieve manier
- Richt je op wat het beste is voor de community
- Gebruik inclusieve taal

---

## 🛠️ Hoe Bij te Dragen

### Bugs Melden

1. Controleer of de bug niet al eerder is gemeld
2. Open een [Issue](https://github.com/alexdcd/Mafia-Claude-Skills/issues/new?template=bug-report.md)
3. Voeg het volgende toe:
   - Duidelijke beschrijving van het probleem
   - Stappen om het te reproduceren
   - Verwacht vs huidig gedrag
   - Screenshots indien van toepassing

### Verbeteringen Voorstellen

1. Open een Issue met het label `enhancement`
2. Beschrijf de voorgestelde verbetering
3. Leg uit waarom het nuttig zou zijn

### Code Bijdragen

1. Fork de repository
2. Maak een branch voor je feature (`git checkout -b feature/nieuwe-skill`)
3. Commit je wijzigingen (`git commit -m 'Voeg nieuwe skill X toe'`)
4. Push naar de branch (`git push origin feature/nieuwe-skill`)
5. Open een Pull Request

---

## ✨ Een Nieuwe Skill Maken

### Stap 1: Maak de structuur

```bash
mkdir -p skills/mijn-skill-naam
touch skills/mijn-skill-naam/SKILL.md
```

### Stap 2: Vul SKILL.md in

Gebruik deze minimale sjabloon:

```markdown
---
name: mijn-skill-naam
description: >
  Duidelijke en volledige beschrijving van wat deze skill doet.
  Inclusief wanneer deze moet worden geactiveerd/gebruikt.
---

# Naam van de Skill

Gedetailleerde beschrijving.

## Wanneer Deze Skill Te Gebruiken

- Use case 1
- Use case 2

## Instructies

[Stapsgewijze instructies voor Claude]

## Voorbeelden

[Voorbeelden van echt gebruik]
```

### Stap 3: Voeg optionele bronnen toe

```
mijn-skill-naam/
├── SKILL.md           # ✅ Vereist
├── scripts/           # Optioneel: hulpscripts
├── templates/         # Optioneel: sjablonen
└── references/        # Optioneel: referentiedocumentatie
```

### Stap 4: Werk de README bij

Voeg je skill toe aan de tabel in de hoofd README.

---

## 📐 Structuur van een Skill

### SKILL.md Bestand

Het `SKILL.md` bestand is het hart van elke skill. Het bevat:

1. **YAML Frontmatter** (vereist):
   ```yaml
   ---
   name: naam-in-kleine-letters-met-streepjes
   description: >
     Volledige beschrijving op één of meerdere regels.
   ---
   ```

2. **Markdown Inhoud**:
   - Titel en beschrijving
   - Wanneer de skill te gebruiken
   - Gedetailleerde instructies voor Claude
   - Gebruiksvoorbeelden
   - Aanvullende referenties

### Scripts

Als je skill nauwkeurige berekeningen of gegevensverwerking nodig heeft:

- Gebruik **Python 3** voor scripts
- Zet `#!/usr/bin/env python3` bovenaan
- Gebruik `argparse` voor CLI-argumenten
- Voeg docstrings en opmerkingen toe
- Ondersteun JSON-uitvoer (`--json`) voor integratie

### Referenties

Voor ondersteunende documentatie:

- Gebruik **Markdown**
- Neem officiële bronnen op
- Houd de informatie up-to-date

---

## ✅ Best Practices

### Voor de SKILL.md

| ✅ Doen | ❌ Vermijden |
|---------|--------------|
| Duidelijke, stapsgewijze instructies | Vage instructies |
| Concrete voorbeelden | Alleen theorie |
| Edge cases afdekken | Uitgaan van perfecte invoer |
| Schrijven voor Claude, niet voor eindgebruikers | Doelgroepen mixen |
| Afhankelijkheden documenteren | Uitgaan van eerdere configuratie |

### Voor Scripts

```python
# ✅ Goed: Gebruik Decimal voor geld
from decimal import Decimal
prijs = Decimal('19.99')

# ❌ Fout: Float voor geld
prijs = 19.99
```

```python
# ✅ Goed: Foutafhandeling
try:
    resultaat = verwerk_gegevens(invoer)
except ValueError as e:
    print(f"Fout: {e}", file=sys.stderr)
    sys.exit(1)

# ❌ Fout: Geen foutafhandeling
resultaat = verwerk_gegevens(invoer)
```

### Voor Documentatie

- Gebruik duidelijk en beknopt Nederlands
- Voeg tabellen toe voor gestructureerde informatie
- Gebruik emoji's met mate om de leesbaarheid te verbeteren
- Houd regels kort (< 100 tekens)

---

## 🔄 Pull Requests

### Voordat je indient

- [ ] De code is getest en werkt
- [ ] SKILL.md heeft een geldige frontmatter
- [ ] Voorbeelden zijn realistisch en werken
- [ ] README.md is bijgewerkt (als je een skill toevoegt)
- [ ] Er is geen gevoelige informatie (tokens, wachtwoorden)

### Beoordelingsproces

1. Een beheerder (maintainer) zal je PR beoordelen
2. Er kunnen opmerkingen of suggesties zijn
3. Breng de nodige wijzigingen aan
4. Zodra het is goedgekeurd, wordt het gemerged

### Commit Conventie

```bash
# Voor nieuwe skills
git commit -m "feat(skill): voeg factuurbeheerskill toe"

# Voor verbeteringen
git commit -m "improve(gestor-autonomos): voeg ondersteuning toe voor formulier 390"

# Voor bugs
git commit -m "fix(scripts): corrigeer afrondingsberekening in BTW"

# Voor documentatie
git commit -m "docs: werk bijdragegids bij"
```

---

## ❓ Vragen

Als je twijfelt:

1. Bekijk de [bestaande Issues](https://github.com/alexdcd/Mafia-Claude-Skills/issues)
2. Open een nieuwe Issue met het label `question`
3. Wees specifiek over je vraag

---

## 🙏 Dankwoord

Bedankt aan iedereen die bijdraagt om dit project beter te maken. Jouw tijd en inzet worden zeer gewaardeerd.

---

*De eerste keer dat je bijdraagt aan open source? Maak je geen zorgen! We zijn hier om te helpen.*
