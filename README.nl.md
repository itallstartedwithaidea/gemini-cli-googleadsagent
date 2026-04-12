# Gemini CLI + Google Ads Agent

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh.md) | [Nederlands](README.nl.md) | [Русский](README.ru.md) | [한국어](README.ko.md)

> **Open-source Google Ads-beheercommando's en AI-agentvaardigheden voor
> [Gemini CLI](https://github.com/google-gemini/gemini-cli).** Analyseer campagneprestaties,
> audit accounts, optimaliseer PPC-uitgaven en genereer GAQL-queries — allemaal vanuit je terminal.

[![License](https://img.shields.io/github/license/google-gemini/gemini-cli)](https://github.com/google-gemini/gemini-cli/blob/main/LICENSE)
[![Version](https://img.shields.io/npm/v/@google/gemini-cli)](https://www.npmjs.com/package/@google/gemini-cli)
[![Wiki](https://img.shields.io/badge/docs-Wiki-blue)](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)
[![Advertising Hub](https://img.shields.io/badge/ecosystem-Advertising%20Hub-orange)](https://github.com/itallstartedwithaidea/advertising-hub)
[![googleadsagent.ai](https://img.shields.io/badge/site-googleadsagent.ai-green)](https://googleadsagent.ai)

**Onderdeel van het [Advertising Hub](https://github.com/itallstartedwithaidea/advertising-hub) ecosysteem** — 14 advertentieplatform-API's, 25+ AI-agents, MCP-servers |
[googleadsagent.ai](https://googleadsagent.ai) |
[MiniAgent](https://github.com/itallstartedwithaidea/MiniAgent)

---

## Welk hulpmiddel heb je nodig?

| Ik gebruik...                    | Dit installeren                                                                                                                                             | Insteltijd |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| **Gemini CLI** (terminal)        | [google-ads-gemini-extension](https://github.com/itallstartedwithaidea/google-ads-gemini-extension)                                                         | ~15 min    |
| **Claude** (Desktop of Code)     | [google-ads-skills](https://github.com/itallstartedwithaidea/google-ads-skills) + [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) | ~15 min    |
| **Cursor / Windsurf / Ander**    | [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) (Python, 29 tools)                                                                | ~15 min    |
| **Ik wil het gewoon beheerd**    | [googleadsagent.ai](https://googleadsagent.ai) — geen setup nodig                                                                                           | 0 min      |

> **Stapsgewijze installatiegids met screenshots:**
> **[googleadsagent.ai/setup](https://googleadsagent.ai/setup/)** — behandelt elk pad, elke credential, elke valkuil.

---

## Google Ads-commando's

Deze fork breidt Gemini CLI uit met drie Google Ads slash-commando's en een domeinspecifieke agentvaardigheid.

### `/google-ads-analyze` — Campagneprestatie-analyse

```
/google-ads-analyze Show me top spending campaigns last 30 days with declining ROAS
```

- Stelt relevante GAQL-queries voor
- Presenteert bevindingen in overzichtelijke tabellen
- Identificeert anomalieën en kansen
- Beveelt specifieke, uitvoerbare volgende stappen aan

### `/google-ads-audit` — Uitgebreide accountaudit

```
/google-ads-audit Full audit of the Hopeworks nonprofit account
```

Dekt 7 auditgebieden met ernstniveaus (Kritiek / Hoog / Gemiddeld / Laag):

- Accountstructuur, biedstrategie, budgetallocatie
- Zoekwoordgezondheid, advertentiecreative, targeting, conversietracking

### `/google-ads-optimize` — Optimalisatieaanbevelingen

```
/google-ads-optimize We need to reduce CPA by 15% without losing volume
```

- Identificeert de top 3-5 optimalisatiekansen met de hoogste impact
- Prioriteert op inspanning vs. impact met risiconiveaus
- Behandelt verspilde uitgaven, biedefficiëntie, creative-vermoeidheid en targetinglacunes

### Google Ads Agent-vaardigheid

De meegeleverde vaardigheid (`.gemini/skills/google-ads-agent/`) wordt automatisch geactiveerd voor elke advertentiegerelateerde vraag. Het biedt:

- **GAQL-expertise** — kent Google Ads Query Language-syntaxis, veelvoorkomende patronen en kostenconversie naar micro-eenheden
- **API v22-kennis** — huidige API-versie, authenticatiepatronen, snelheidslimieten
- **Campagne-analyse** — trends, anomalieën, onderpresteerders, budgetallocatie
- **Schrijfveiligheid** — presenteert altijd voorgestelde wijzigingen vóór uitvoering

## Snelstart — Ik wil het gewoon gebruiken

De meeste gebruikers willen dit pad. Drie commando's, ~15 minuten:

```bash
# 1. Install Gemini CLI
npm install -g @google/gemini-cli

# 2. Install the Google Ads extension (MCP server + commands + skills)
gemini extensions install https://github.com/itallstartedwithaidea/google-ads-gemini-extension

# 3. Enter your Google Ads credentials (one-time setup)
gemini extensions config google-ads-agent

# 4. Start using it
gemini
> Show me my Google Ads accounts
```

Je hebt 5 credentialwaarden nodig van Google Ads, Google Cloud Console en OAuth Playground. De **[volledige installatiegids](https://googleadsagent.ai/setup/)** begeleidt je bij elke stap met screenshots.

### Snelstart — Ik wil bijdragen / ontwikkelen

```bash
git clone https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent.git
cd gemini-cli-googleadsagent
npm install
npm run build
npm start
```

Of kopieer alleen de Google Ads-commando's/vaardigheden naar elk project:

```bash
cp -r gemini-cli-googleadsagent/.gemini/commands/google-ads-*.toml your-project/.gemini/commands/
cp -r gemini-cli-googleadsagent/.gemini/skills/google-ads-agent/ your-project/.gemini/skills/
```

## Gerelateerde projecten

| Project                                                                                               | Beschrijving                                                          |
| ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| [**advertising-hub**](https://github.com/itallstartedwithaidea/advertising-hub)                       | Alles-in-één voor 14 advertentieplatform-API's, MCP-servers en agents |
| [**google-ads-api-agent**](https://github.com/itallstartedwithaidea/google-ads-api-agent)             | Enterprise Google Ads-agent — 28 API-acties, live lezen/schrijven     |
| [**google-ads-mcp**](https://github.com/itallstartedwithaidea/google-ads-mcp)                         | MCP-server voor Google Ads API-toegang                                |
| [**google-ads-skills**](https://github.com/itallstartedwithaidea/google-ads-skills)                   | Claude Code / Codex / Gemini CLI-vaardigheden voor Google Ads         |
| [**MiniAgent**](https://github.com/itallstartedwithaidea/MiniAgent)                                   | Trainbare advertentie-AI met 26M parameters + 14 MCP-servers          |
| [**google-ads-claudecodeskill**](https://github.com/itallstartedwithaidea/google-ads-claudecodeskill) | Claude Code-vaardigheid voor Google Ads-beheer                        |

---

## Documentatie

Volledige documentatie is beschikbaar op de **[Wiki](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)**:

- [Aan de slag](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Getting-Started) — Installatie, authenticatie, eerste run
- [Commandoreferentie](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Commands-Reference) — Volledige docs voor alle drie de commando's met voorbeelden
- [Google Ads Agent-vaardigheid](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Google-Ads-Agent-Skill) — GAQL-patronen, API v22-kennis, schrijfveiligheid
- [Configuratie](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Configuration) — Instellingen, omgevingsvariabelen, modelselectie
- [Gerelateerde projecten](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Related-Projects) — Volledig ecosysteemoverzicht

---

## Over Gemini CLI (upstream)

Dit is een fork van [google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli) met Google Ads-specifieke extensies.

Gemini CLI is een open-source AI-agent die de kracht van Gemini direct naar je terminal brengt. Leer alles over Gemini CLI in de [officiële documentatie](https://geminicli.com/docs/).

## Waarom Gemini CLI?

- **Gratis tier**: 60 verzoeken/min en 1.000 verzoeken/dag met een persoonlijk Google-account.
- **Krachtige Gemini 3-modellen**: Verbeterd redeneren en 1M-token contextvenster.
- **Ingebouwde tools**: Google Search, bestandsoperaties, shell-commando's, web-ophaling.
- **Uitbreidbaar**: MCP-ondersteuning (Model Context Protocol) voor aangepaste integraties.
- **Terminal-first**: Ontworpen voor ontwikkelaars die in de commandoregel leven.
- **Open source**: Apache 2.0-licentie.

## Installatie

Zie [Gemini CLI installatie, uitvoering en releases](./docs/get-started/installation.md).

### Snelle installatie

```bash
npx @google/gemini-cli
npm install -g @google/gemini-cli
brew install gemini-cli
```

## Belangrijke functies

### Code begrijpen en genereren
- Grote codebases bevragen en bewerken
- Nieuwe apps genereren vanuit PDF's, afbeeldingen of schetsen
- Problemen debuggen met natuurlijke taal

### Automatisering en integratie
- Operationele taken automatiseren
- MCP-servers gebruiken voor extra mogelijkheden
- Non-interactief uitvoeren in scripts

### Geavanceerde mogelijkheden
- Queries verankeren met ingebouwde Google Search
- Conversatiecheckpoints om complexe sessies op te slaan en te hervatten
- Aangepaste contextbestanden (GEMINI.md)

### GitHub-integratie
- Pull Request-reviews, issue-triage, on-demand hulp, aangepaste workflows

## Authenticatie-opties

- **Optie 1: Inloggen met Google** — Gratis tier: 60 verzoeken/min
- **Optie 2: Gemini API-sleutel** — `export GEMINI_API_KEY="YOUR_API_KEY"`
- **Optie 3: Vertex AI** — Voor enterprise-teams

## Documentatielinks

- [Snelstartgids](./docs/get-started/index.md) | [Authenticatie](./docs/get-started/authentication.md) | [Configuratie](./docs/reference/configuration.md)
- [Commandoreferentie](./docs/reference/commands.md) | [Aangepaste commando's](./docs/cli/custom-commands.md) | [GEMINI.md](./docs/cli/gemini-md.md)
- [Ingebouwde tools](./docs/reference/tools.md) | [MCP-serverintegratie](./docs/tools/mcp-server.md)
- [Probleemoplossing](./docs/resources/troubleshooting.md) | [FAQ](./docs/resources/faq.md)

## Bijdragen

Bijdragen zijn welkom! Zie onze [Bijdragegids](./CONTRIBUTING.md).

## Juridisch

- **Licentie**: [Apache License 2.0](LICENSE)
- **Servicevoorwaarden**: [Voorwaarden en privacy](./docs/resources/tos-privacy.md)
- **Beveiliging**: [Beveiligingsbeleid](SECURITY.md)

---

<p align="center">
  Upstream: Gebouwd met ❤️ door Google en de open-sourcecommunity<br>
  Google Ads-extensies door <a href="https://github.com/itallstartedwithaidea">John Williams</a> — Team Lead, Paid Media @ Seer Interactive | <a href="https://googleadsagent.ai">googleadsagent.ai</a>
</p>
