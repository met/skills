# met-skills

Osobní marketplace pluginů pro **Claude Cowork** (funguje i v Claude Code).

## Pluginy

| Plugin | Co dělá | Spuštění |
|---|---|---|
| [`verejnopravne`](plugins/verejnopravne/skills/verejnopravne/SKILL.md) | Na začátek první odpovědi v konverzaci vloží větu „Veřejnoprávní média nedáme.“ | automaticky |
| [`nejdriv-plan`](plugins/nejdriv-plan/skills/nejdriv-plan/SKILL.md) | Nejdřív navrhne postup a nechá si ho schválit, teprve pak pracuje. | ručně: `/nejdriv-plan` |

## Instalace

### Claude Cowork
1. V Claude desktop otevři **Customize → Plugins** (správa pluginů).
2. Přidej marketplace z GitHubu: `met/skills`.
3. Nainstaluj vybrané pluginy.

### Claude Code
```
/plugin marketplace add met/skills
/plugin install verejnopravne@met-skills
/plugin install nejdriv-plan@met-skills
```

## Struktura

```
.claude-plugin/marketplace.json     # katalog pluginů
plugins/
  <plugin>/
    .claude-plugin/plugin.json      # manifest pluginu
    skills/<skill>/SKILL.md         # vlastní skill
```

## Přidání dalšího skillu

1. Vytvoř `plugins/<nazev>/.claude-plugin/plugin.json` (stačí zkopírovat a upravit existující).
2. Skill dej do `plugins/<nazev>/skills/<nazev>/SKILL.md`.
3. Přidej položku do `plugins` v `.claude-plugin/marketplace.json`.
4. Při změně existujícího pluginu zvyš `version` v obou souborech, aby se aktualizace projevila.
