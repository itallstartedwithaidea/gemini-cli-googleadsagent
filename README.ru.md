# Gemini CLI + Google Ads Agent

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh.md) | [Nederlands](README.nl.md) | [Русский](README.ru.md) | [한국어](README.ko.md)

> **Открытые команды управления Google Ads и навыки ИИ-агента для
> [Gemini CLI](https://github.com/google-gemini/gemini-cli).** Анализируйте эффективность
> кампаний, проводите аудит аккаунтов, оптимизируйте расходы на PPC и генерируйте GAQL-запросы —
> всё из терминала.

[![License](https://img.shields.io/github/license/google-gemini/gemini-cli)](https://github.com/google-gemini/gemini-cli/blob/main/LICENSE)
[![Version](https://img.shields.io/npm/v/@google/gemini-cli)](https://www.npmjs.com/package/@google/gemini-cli)
[![Wiki](https://img.shields.io/badge/docs-Wiki-blue)](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)
[![Advertising Hub](https://img.shields.io/badge/ecosystem-Advertising%20Hub-orange)](https://github.com/itallstartedwithaidea/advertising-hub)
[![googleadsagent.ai](https://img.shields.io/badge/site-googleadsagent.ai-green)](https://googleadsagent.ai)

**Часть экосистемы [Advertising Hub](https://github.com/itallstartedwithaidea/advertising-hub)** — 14 API рекламных платформ, 25+ ИИ-агентов, MCP-серверы |
[googleadsagent.ai](https://googleadsagent.ai) |
[MiniAgent](https://github.com/itallstartedwithaidea/MiniAgent)

---

## Какой инструмент вам нужен?

| Я использую...                    | Установить                                                                                                                                                  | Время настройки |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------- |
| **Gemini CLI** (терминал)         | [google-ads-gemini-extension](https://github.com/itallstartedwithaidea/google-ads-gemini-extension)                                                         | ~15 мин         |
| **Claude** (Desktop или Code)     | [google-ads-skills](https://github.com/itallstartedwithaidea/google-ads-skills) + [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) | ~15 мин         |
| **Cursor / Windsurf / Другой**    | [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) (Python, 29 инструментов)                                                         | ~15 мин         |
| **Просто хочу управляемый сервис** | [googleadsagent.ai](https://googleadsagent.ai) — настройка не нужна                                                                                         | 0 мин           |

> **Пошаговое руководство со скриншотами:**
> **[googleadsagent.ai/setup](https://googleadsagent.ai/setup/)**

---

## Команды Google Ads

Этот форк расширяет Gemini CLI тремя слеш-командами Google Ads и навыком доменного агента.

### `/google-ads-analyze` — Анализ эффективности кампаний

```
/google-ads-analyze Show me top spending campaigns last 30 days with declining ROAS
```

- Предлагает релевантные GAQL-запросы для извлечения данных
- Представляет результаты в наглядных таблицах
- Выявляет аномалии и возможности
- Рекомендует конкретные действия

### `/google-ads-audit` — Комплексный аудит аккаунта

```
/google-ads-audit Full audit of the Hopeworks nonprofit account
```

Охватывает 7 областей аудита с уровнями серьёзности (Критический / Высокий / Средний / Низкий):

- Структура аккаунта, стратегия ставок, распределение бюджета
- Здоровье ключевых слов, рекламные креативы, таргетинг, отслеживание конверсий

### `/google-ads-optimize` — Рекомендации по оптимизации

```
/google-ads-optimize We need to reduce CPA by 15% without losing volume
```

- Определяет 3-5 возможностей оптимизации с наибольшим воздействием
- Приоритизирует по усилию vs воздействию с уровнями риска
- Охватывает растраченный бюджет, эффективность ставок, усталость от креативов и пробелы в таргетинге

### Навык агента Google Ads

Встроенный навык (`.gemini/skills/google-ads-agent/`) автоматически активируется для любого вопроса, связанного с рекламой. Он обеспечивает:

- **Экспертиза GAQL** — знает синтаксис Google Ads Query Language, распространённые паттерны и конвертацию стоимости в микроединицы
- **Знание API v22** — текущая версия API, паттерны аутентификации, лимиты запросов
- **Анализ кампаний** — тренды, аномалии, слабые исполнители, распределение бюджета
- **Безопасность записи** — всегда показывает предложенные изменения перед выполнением

## Быстрый старт — Я просто хочу использовать

Большинство пользователей хотят этот путь. Три команды, ~15 минут:

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

Вам нужно 5 значений учётных данных из Google Ads, Google Cloud Console и OAuth Playground. **[Полное руководство по настройке](https://googleadsagent.ai/setup/)** проведёт вас через каждый шаг со скриншотами.

### Быстрый старт — Хочу внести вклад / разрабатывать

```bash
git clone https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent.git
cd gemini-cli-googleadsagent
npm install
npm run build
npm start
```

## Связанные проекты

| Проект                                                                                                | Описание                                                             |
| ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| [**advertising-hub**](https://github.com/itallstartedwithaidea/advertising-hub)                       | Единая точка для 14 API рекламных платформ, MCP-серверов и агентов   |
| [**google-ads-api-agent**](https://github.com/itallstartedwithaidea/google-ads-api-agent)             | Корпоративный агент Google Ads — 28 API-действий, чтение/запись      |
| [**google-ads-mcp**](https://github.com/itallstartedwithaidea/google-ads-mcp)                         | MCP-сервер для доступа к API Google Ads                              |
| [**google-ads-skills**](https://github.com/itallstartedwithaidea/google-ads-skills)                   | Навыки Claude Code / Codex / Gemini CLI для Google Ads               |
| [**MiniAgent**](https://github.com/itallstartedwithaidea/MiniAgent)                                   | Обучаемый рекламный ИИ с 26M параметров + 14 MCP-серверов            |
| [**google-ads-claudecodeskill**](https://github.com/itallstartedwithaidea/google-ads-claudecodeskill) | Навык Claude Code для управления Google Ads                          |

---

## Документация

Полная документация доступна на **[Wiki](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)**:

- [Начало работы](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Getting-Started)
- [Справочник команд](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Commands-Reference)
- [Навык агента Google Ads](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Google-Ads-Agent-Skill)
- [Конфигурация](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Configuration)
- [Связанные проекты](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Related-Projects)

---

## О Gemini CLI (апстрим)

Это форк [google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli) с расширениями для Google Ads.

Gemini CLI — это open-source ИИ-агент, который приносит мощь Gemini прямо в ваш терминал. Подробнее в [официальной документации](https://geminicli.com/docs/).

## Почему Gemini CLI?

- **Бесплатный уровень**: 60 запросов/мин и 1 000 запросов/день с личным аккаунтом Google.
- **Мощные модели Gemini 3**: Улучшенное рассуждение и контекстное окно в 1M токенов.
- **Встроенные инструменты**: Google Search, файловые операции, shell-команды, веб-выборка.
- **Расширяемый**: Поддержка MCP для пользовательских интеграций.
- **Терминал в первую очередь**: Создан для разработчиков, живущих в командной строке.
- **Открытый исходный код**: Лицензия Apache 2.0.

## Установка

```bash
npx @google/gemini-cli
npm install -g @google/gemini-cli
brew install gemini-cli
```

## Аутентификация

- **Вариант 1**: Вход через Google (OAuth) — бесплатно: 60 запросов/мин
- **Вариант 2**: Ключ API Gemini — `export GEMINI_API_KEY="YOUR_API_KEY"`
- **Вариант 3**: Vertex AI — для корпоративных команд

## Ссылки на документацию

- [Быстрый старт](./docs/get-started/index.md) | [Аутентификация](./docs/get-started/authentication.md) | [Конфигурация](./docs/reference/configuration.md)
- [Справочник команд](./docs/reference/commands.md) | [Пользовательские команды](./docs/cli/custom-commands.md)
- [Встроенные инструменты](./docs/reference/tools.md) | [Интеграция MCP-серверов](./docs/tools/mcp-server.md)
- [Устранение неполадок](./docs/resources/troubleshooting.md) | [FAQ](./docs/resources/faq.md)

## Участие в разработке

Вклад приветствуется! См. [Руководство по участию](./CONTRIBUTING.md).

## Юридическая информация

- **Лицензия**: [Apache License 2.0](LICENSE)
- **Условия использования**: [Условия и конфиденциальность](./docs/resources/tos-privacy.md)
- **Безопасность**: [Политика безопасности](SECURITY.md)

---

<p align="center">
  Апстрим: Создано с ❤️ Google и сообществом открытого исходного кода<br>
  Расширения Google Ads от <a href="https://github.com/itallstartedwithaidea">John Williams</a> — Team Lead, Paid Media @ Seer Interactive | <a href="https://googleadsagent.ai">googleadsagent.ai</a>
</p>
