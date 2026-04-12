# Gemini CLI + Google Ads Agent

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh.md) | [Nederlands](README.nl.md) | [Русский](README.ru.md) | [한국어](README.ko.md)

> **Commandes open source de gestion Google Ads et compétences d'agent IA pour
> [Gemini CLI](https://github.com/google-gemini/gemini-cli).** Analysez les performances
> des campagnes, auditez les comptes, optimisez les dépenses PPC et générez des requêtes GAQL —
> le tout depuis votre terminal.

[![License](https://img.shields.io/github/license/google-gemini/gemini-cli)](https://github.com/google-gemini/gemini-cli/blob/main/LICENSE)
[![Version](https://img.shields.io/npm/v/@google/gemini-cli)](https://www.npmjs.com/package/@google/gemini-cli)
[![Wiki](https://img.shields.io/badge/docs-Wiki-blue)](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)
[![Advertising Hub](https://img.shields.io/badge/ecosystem-Advertising%20Hub-orange)](https://github.com/itallstartedwithaidea/advertising-hub)
[![googleadsagent.ai](https://img.shields.io/badge/site-googleadsagent.ai-green)](https://googleadsagent.ai)

**Fait partie de l'écosystème
[Advertising Hub](https://github.com/itallstartedwithaidea/advertising-hub)** — 14 API de plateformes publicitaires, 25+ agents IA, serveurs MCP |
[googleadsagent.ai](https://googleadsagent.ai) |
[MiniAgent](https://github.com/itallstartedwithaidea/MiniAgent)

---

## Quel outil vous faut-il ?

| J'utilise...                     | Installer ceci                                                                                                                                              | Temps de configuration |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- |
| **Gemini CLI** (terminal)        | [google-ads-gemini-extension](https://github.com/itallstartedwithaidea/google-ads-gemini-extension)                                                         | ~15 min                |
| **Claude** (Desktop ou Code)     | [google-ads-skills](https://github.com/itallstartedwithaidea/google-ads-skills) + [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) | ~15 min                |
| **Cursor / Windsurf / Autre**    | [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) (Python, 29 outils)                                                               | ~15 min                |
| **Je veux juste que ce soit géré** | [googleadsagent.ai](https://googleadsagent.ai) — aucune configuration nécessaire                                                                            | 0 min                  |

> **Guide de configuration pas à pas avec captures d'écran :**
> **[googleadsagent.ai/setup](https://googleadsagent.ai/setup/)** — couvre chaque
> chemin, chaque identifiant, chaque piège. Pas besoin d'un diplôme d'ingénieur.

---

## Commandes Google Ads

Ce fork étend Gemini CLI avec trois commandes slash Google Ads et une
compétence d'agent spécifique au domaine.

### `/google-ads-analyze` — Analyse des performances de campagne

```
/google-ads-analyze Show me top spending campaigns last 30 days with declining ROAS
```

- Suggère les requêtes GAQL pertinentes pour extraire les données
- Présente les résultats dans des tableaux clairs
- Identifie les anomalies et les opportunités
- Recommande des actions spécifiques et concrètes

### `/google-ads-audit` — Audit complet du compte

```
/google-ads-audit Full audit of the Hopeworks nonprofit account
```

Couvre 7 domaines d'audit avec des niveaux de gravité (Critique / Élevé / Moyen / Faible) :

- Structure du compte, stratégie d'enchères, allocation budgétaire
- Santé des mots-clés, créatif publicitaire, ciblage, suivi des conversions

### `/google-ads-optimize` — Recommandations d'optimisation

```
/google-ads-optimize We need to reduce CPA by 15% without losing volume
```

- Identifie les 3 à 5 opportunités d'optimisation à plus fort impact
- Priorise par effort vs impact avec niveaux de risque
- Couvre les dépenses gaspillées, l'efficacité des enchères, la fatigue créative et les lacunes de ciblage

### Compétence d'agent Google Ads

La compétence incluse (`.gemini/skills/google-ads-agent/`) s'active automatiquement
pour toute question liée à la publicité. Elle fournit :

- **Expertise GAQL** — connaît la syntaxe Google Ads Query Language, les patterns courants
  et la conversion en micro-unités de coût
- **Connaissance API v22** — version actuelle de l'API, patterns d'authentification, limites de débit
- **Analyse de campagne** — tendances, anomalies, sous-performeurs, allocation budgétaire
- **Sécurité en écriture** — présente toujours les modifications proposées avant exécution

## Démarrage rapide — Je veux juste l'utiliser

La plupart des utilisateurs veulent ce chemin. Trois commandes, ~15 minutes :

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

Vous avez besoin de 5 valeurs d'identification de Google Ads, Google Cloud Console et OAuth
Playground. Le **[guide de configuration complet](https://googleadsagent.ai/setup/)** vous accompagne
à chaque étape avec des captures d'écran.

### Démarrage rapide — Je veux contribuer / développer

Si vous souhaitez modifier le CLI lui-même (pas seulement utiliser l'extension) :

```bash
git clone https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent.git
cd gemini-cli-googleadsagent
npm install
npm run build
npm start
```

Ou copiez uniquement les commandes/compétences Google Ads dans n'importe quel projet :

```bash
cp -r gemini-cli-googleadsagent/.gemini/commands/google-ads-*.toml your-project/.gemini/commands/
cp -r gemini-cli-googleadsagent/.gemini/skills/google-ads-agent/ your-project/.gemini/skills/
```

## Projets associés

| Projet                                                                                                | Description                                                          |
| ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| [**advertising-hub**](https://github.com/itallstartedwithaidea/advertising-hub)                       | Guichet unique pour 14 API de plateformes pub, serveurs MCP et agents |
| [**google-ads-api-agent**](https://github.com/itallstartedwithaidea/google-ads-api-agent)             | Agent Google Ads entreprise — 28 actions API, lecture/écriture en direct |
| [**google-ads-mcp**](https://github.com/itallstartedwithaidea/google-ads-mcp)                         | Serveur MCP pour l'accès à l'API Google Ads                          |
| [**google-ads-skills**](https://github.com/itallstartedwithaidea/google-ads-skills)                   | Compétences Claude Code / Codex / Gemini CLI pour Google Ads         |
| [**MiniAgent**](https://github.com/itallstartedwithaidea/MiniAgent)                                   | IA publicitaire entraînable de 26M paramètres + 14 serveurs MCP     |
| [**google-ads-claudecodeskill**](https://github.com/itallstartedwithaidea/google-ads-claudecodeskill) | Compétence Claude Code pour la gestion Google Ads                    |

---

## Documentation

La documentation complète est disponible sur le
**[Wiki](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)** :

- [Pour commencer](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Getting-Started) — Installation, authentification, premier lancement
- [Référence des commandes](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Commands-Reference) — Documentation complète des trois commandes avec exemples
- [Compétence d'agent Google Ads](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Google-Ads-Agent-Skill) — Patterns GAQL, connaissance API v22, sécurité en écriture
- [Configuration](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Configuration) — Paramètres, variables d'environnement, sélection de modèle
- [Projets associés](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Related-Projects) — Vue d'ensemble complète de l'écosystème

---

## À propos de Gemini CLI (en amont)

Ceci est un fork de
[google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli) avec
des extensions spécifiques à Google Ads.

Gemini CLI est un agent IA open source qui apporte la puissance de Gemini directement
dans votre terminal. Il offre un accès léger à Gemini, vous donnant le
chemin le plus direct de votre prompt vers notre modèle.

Découvrez tout sur Gemini CLI dans la
[documentation officielle](https://geminicli.com/docs/).

## Pourquoi Gemini CLI ?

- **Niveau gratuit** : 60 requêtes/min et 1 000 requêtes/jour avec un compte Google personnel.
- **Modèles Gemini 3 puissants** : Accès à un raisonnement amélioré et une fenêtre de contexte de 1M de tokens.
- **Outils intégrés** : Recherche Google, opérations sur fichiers, commandes shell, récupération web.
- **Extensible** : Support MCP (Model Context Protocol) pour des intégrations personnalisées.
- **Terminal d'abord** : Conçu pour les développeurs qui vivent dans la ligne de commande.
- **Open source** : Licence Apache 2.0.

## Installation

Voir
[Installation, exécution et versions de Gemini CLI](./docs/get-started/installation.md)
pour les spécifications système recommandées et un guide d'installation détaillé.

### Installation rapide

#### Exécuter instantanément avec npx

```bash
# Using npx (no installation required)
npx @google/gemini-cli
```

#### Installer globalement avec npm

```bash
npm install -g @google/gemini-cli
```

#### Installer globalement avec Homebrew (macOS/Linux)

```bash
brew install gemini-cli
```

#### Installer globalement avec MacPorts (macOS)

```bash
sudo port install gemini-cli
```

#### Installer avec Anaconda (pour les environnements restreints)

```bash
# Create and activate a new environment
conda create -y -n gemini_env -c conda-forge nodejs
conda activate gemini_env

# Install Gemini CLI globally via npm (inside the environment)
npm install -g @google/gemini-cli
```

## Cadence de publication et tags

Voir [Versions](./docs/releases.md) pour plus de détails.

### Preview

De nouvelles versions preview sont publiées chaque semaine le mardi à 23h59 UTC. Ces
versions n'ont pas été entièrement vérifiées et peuvent contenir des régressions ou d'autres
problèmes en cours. Aidez-nous à tester en installant avec le tag `preview`.

```bash
npm install -g @google/gemini-cli@preview
```

### Stable

- De nouvelles versions stables sont publiées chaque semaine le mardi à 20h00 UTC,
  correspondant à la promotion complète de la version `preview` de la semaine précédente + corrections de bugs
  et validations. Utilisez le tag `latest`.

```bash
npm install -g @google/gemini-cli@latest
```

### Nightly

- De nouvelles versions sont publiées chaque jour à 00h00 UTC. Elles incluent tous les changements
  de la branche main au moment de la publication. Des validations et problèmes en attente sont à prévoir.
  Utilisez le tag `nightly`.

```bash
npm install -g @google/gemini-cli@nightly
```

## Fonctionnalités clés

### Compréhension et génération de code

- Interroger et modifier de grandes bases de code
- Générer de nouvelles applications à partir de PDF, images ou croquis grâce aux capacités multimodales
- Déboguer les problèmes et résoudre les difficultés en langage naturel

### Automatisation et intégration

- Automatiser les tâches opérationnelles comme l'interrogation de pull requests ou la gestion de rebases complexes
- Utiliser des serveurs MCP pour connecter de nouvelles capacités, y compris
  [la génération multimédia avec Imagen, Veo ou Lyria](https://github.com/GoogleCloudPlatform/vertex-ai-creative-studio/tree/main/experiments/mcp-genmedia)
- Exécuter en mode non interactif dans des scripts pour l'automatisation des workflows

### Capacités avancées

- Ancrer vos requêtes avec la
  [Recherche Google](https://ai.google.dev/gemini-api/docs/grounding) intégrée pour des informations en temps réel
- Points de sauvegarde de conversation pour sauvegarder et reprendre des sessions complexes
- Fichiers de contexte personnalisés (GEMINI.md) pour adapter le comportement à vos projets

### Intégration GitHub

Intégrez Gemini CLI directement dans vos workflows GitHub avec
[**Gemini CLI GitHub Action**](https://github.com/google-github-actions/run-gemini-cli) :

- **Revues de Pull Requests** : Revue de code automatisée avec retours contextuels et suggestions
- **Triage des issues** : Étiquetage et priorisation automatiques des issues GitHub basés sur l'analyse du contenu
- **Assistance à la demande** : Mentionnez `@gemini-cli` dans les issues et pull requests pour obtenir de l'aide en débogage, explications ou délégation de tâches
- **Workflows personnalisés** : Créez des workflows automatisés, planifiés et à la demande adaptés aux besoins de votre équipe

## Options d'authentification

Choisissez la méthode d'authentification qui correspond le mieux à vos besoins :

### Option 1 : Connexion avec Google (connexion OAuth avec votre compte Google)

**Idéal pour :** Les développeurs individuels ainsi que toute personne disposant d'une licence Gemini Code Assist. (voir
[limites de quota et conditions d'utilisation](https://cloud.google.com/gemini/docs/quotas)
pour plus de détails)

**Avantages :**

- **Niveau gratuit** : 60 requêtes/min et 1 000 requêtes/jour
- **Modèles Gemini 3** avec fenêtre de contexte de 1M de tokens
- **Pas de gestion de clé API** — connectez-vous simplement avec votre compte Google
- **Mises à jour automatiques** vers les derniers modèles

#### Lancez Gemini CLI, puis choisissez _Connexion avec Google_ et suivez le flux d'authentification dans le navigateur

```bash
gemini
```

#### Si vous utilisez une licence Code Assist payante de votre organisation, n'oubliez pas de définir le projet Google Cloud

```bash
# Set your Google Cloud Project
export GOOGLE_CLOUD_PROJECT="YOUR_PROJECT_ID"
gemini
```

### Option 2 : Clé API Gemini

**Idéal pour :** Les développeurs qui ont besoin d'un contrôle spécifique du modèle ou d'un accès au niveau payant

**Avantages :**

- **Niveau gratuit** : 1000 requêtes/jour avec Gemini 3 (mélange de flash et pro)
- **Sélection de modèle** : Choisissez des modèles Gemini spécifiques
- **Facturation à l'usage** : Mise à niveau pour des limites plus élevées si nécessaire

```bash
# Get your key from https://aistudio.google.com/apikey
export GEMINI_API_KEY="YOUR_API_KEY"
gemini
```

### Option 3 : Vertex AI

**Idéal pour :** Les équipes entreprise et les charges de production

**Avantages :**

- **Fonctionnalités entreprise** : Sécurité et conformité avancées
- **Évolutif** : Limites de débit plus élevées avec compte de facturation
- **Intégration** : Fonctionne avec l'infrastructure Google Cloud existante

```bash
# Get your key from Google Cloud Console
export GOOGLE_API_KEY="YOUR_API_KEY"
export GOOGLE_GENAI_USE_VERTEXAI=true
gemini
```

Pour les comptes Google Workspace et d'autres méthodes d'authentification, voir le
[guide d'authentification](./docs/get-started/authentication.md).

## Pour commencer

### Utilisation de base

#### Démarrer dans le répertoire courant

```bash
gemini
```

#### Inclure plusieurs répertoires

```bash
gemini --include-directories ../lib,../docs
```

#### Utiliser un modèle spécifique

```bash
gemini -m gemini-2.5-flash
```

#### Mode non interactif pour les scripts

Obtenir une réponse texte simple :

```bash
gemini -p "Explain the architecture of this codebase"
```

Pour un scripting plus avancé, y compris comment parser le JSON et gérer les erreurs, utilisez
le flag `--output-format json` pour obtenir une sortie structurée :

```bash
gemini -p "Explain the architecture of this codebase" --output-format json
```

Pour le streaming d'événements en temps réel (utile pour surveiller les opérations longues),
utilisez `--output-format stream-json` pour obtenir des événements JSON délimités par des sauts de ligne :

```bash
gemini -p "Run tests and deploy" --output-format stream-json
```

### Exemples rapides

#### Démarrer un nouveau projet

```bash
cd new-project/
gemini
> Write me a Discord bot that answers questions using a FAQ.md file I will provide
```

#### Analyser du code existant

```bash
git clone https://github.com/google-gemini/gemini-cli
cd gemini-cli
gemini
> Give me a summary of all of the changes that went in yesterday
```

## Documentation

### Pour commencer

- [**Guide de démarrage rapide**](./docs/get-started/index.md) — Être opérationnel rapidement.
- [**Configuration de l'authentification**](./docs/get-started/authentication.md) — Configuration détaillée de l'auth.
- [**Guide de configuration**](./docs/reference/configuration.md) — Paramètres et personnalisation.
- [**Raccourcis clavier**](./docs/reference/keyboard-shortcuts.md) — Conseils de productivité.

### Fonctionnalités principales

- [**Référence des commandes**](./docs/reference/commands.md) — Toutes les commandes slash (`/help`, `/chat`, etc).
- [**Commandes personnalisées**](./docs/cli/custom-commands.md) — Créez vos propres commandes réutilisables.
- [**Fichiers de contexte (GEMINI.md)**](./docs/cli/gemini-md.md) — Fournissez un contexte persistant à Gemini CLI.
- [**Points de sauvegarde**](./docs/cli/checkpointing.md) — Sauvegardez et reprenez des conversations.
- [**Mise en cache des tokens**](./docs/cli/token-caching.md) — Optimisez l'utilisation des tokens.

### Outils et extensions

- [**Vue d'ensemble des outils intégrés**](./docs/reference/tools.md)
  - [Opérations sur le système de fichiers](./docs/tools/file-system.md)
  - [Commandes shell](./docs/tools/shell.md)
  - [Récupération et recherche web](./docs/tools/web-fetch.md)
- [**Intégration serveur MCP**](./docs/tools/mcp-server.md) — Étendez avec des outils personnalisés.
- [**Extensions personnalisées**](./docs/extensions/index.md) — Créez et partagez vos propres commandes.

### Sujets avancés

- [**Mode headless (scripting)**](./docs/cli/headless.md) — Utilisez Gemini CLI dans des workflows automatisés.
- [**Vue d'ensemble de l'architecture**](./docs/architecture.md) — Comment fonctionne Gemini CLI.
- [**Intégration IDE**](./docs/ide-integration/index.md) — Compagnon VS Code.
- [**Sandboxing et sécurité**](./docs/cli/sandbox.md) — Environnements d'exécution sûrs.
- [**Dossiers de confiance**](./docs/cli/trusted-folders.md) — Contrôlez les politiques d'exécution par dossier.
- [**Guide entreprise**](./docs/cli/enterprise.md) — Déployer et gérer en environnement d'entreprise.
- [**Télémétrie et monitoring**](./docs/cli/telemetry.md) — Suivi d'utilisation.
- [**Référence des outils**](./docs/reference/tools.md) — Vue d'ensemble des outils intégrés.
- [**Développement local**](./docs/local-development.md) — Outillage de développement local.

### Dépannage et support

- [**Guide de dépannage**](./docs/resources/troubleshooting.md) — Problèmes courants et solutions.
- [**FAQ**](./docs/resources/faq.md) — Questions fréquemment posées.
- Utilisez la commande `/bug` pour signaler des problèmes directement depuis le CLI.

### Utilisation des serveurs MCP

Configurez les serveurs MCP dans `~/.gemini/settings.json` pour étendre Gemini CLI avec des outils personnalisés :

```text
> @github List my open pull requests
> @slack Send a summary of today's commits to #dev channel
> @database Run a query to find inactive users
```

Voir le [guide d'intégration des serveurs MCP](./docs/tools/mcp-server.md) pour les instructions de configuration.

## Contribuer

Les contributions sont les bienvenues ! Gemini CLI est entièrement open source (Apache 2.0), et nous encourageons la communauté à :

- Signaler des bugs et suggérer des fonctionnalités.
- Améliorer la documentation.
- Soumettre des améliorations de code.
- Partager vos serveurs MCP et extensions.

Voir notre [Guide de contribution](./CONTRIBUTING.md) pour la configuration de développement, les normes de codage et comment soumettre des pull requests.

Consultez notre [Feuille de route officielle](https://github.com/orgs/google-gemini/projects/11) pour les fonctionnalités prévues et les priorités.

## Ressources

- **[Feuille de route officielle](./ROADMAP.md)** — Découvrez les prochaines étapes.
- **[Journal des modifications](./docs/changelogs/index.md)** — Dernières mises à jour notables.
- **[Package NPM](https://www.npmjs.com/package/@google/gemini-cli)** — Registre de packages.
- **[Issues GitHub](https://github.com/google-gemini/gemini-cli/issues)** — Signaler des bugs ou demander des fonctionnalités.
- **[Avis de sécurité](https://github.com/google-gemini/gemini-cli/security/advisories)** — Mises à jour de sécurité.

### Désinstallation

Voir le [Guide de désinstallation](./docs/resources/uninstall.md) pour les instructions de suppression.

## Mentions légales

- **Licence** : [Licence Apache 2.0](LICENSE)
- **Conditions d'utilisation** : [Conditions et confidentialité](./docs/resources/tos-privacy.md)
- **Sécurité** : [Politique de sécurité](SECURITY.md)

---

<p align="center">
  En amont : Construit avec ❤️ par Google et la communauté open source<br>
  Extensions Google Ads par <a href="https://github.com/itallstartedwithaidea">John Williams</a> — Team Lead, Paid Media @ Seer Interactive | <a href="https://googleadsagent.ai">googleadsagent.ai</a>
</p>
