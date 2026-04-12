# Gemini CLI + Google Ads Agent

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh.md) | [Nederlands](README.nl.md) | [Русский](README.ru.md) | [한국어](README.ko.md)

> **Comandos de código abierto para la gestión de Google Ads y habilidades de agente IA para
> [Gemini CLI](https://github.com/google-gemini/gemini-cli).** Analiza el rendimiento
> de campañas, audita cuentas, optimiza el gasto PPC y genera consultas GAQL —
> todo desde tu terminal.

[![License](https://img.shields.io/github/license/google-gemini/gemini-cli)](https://github.com/google-gemini/gemini-cli/blob/main/LICENSE)
[![Version](https://img.shields.io/npm/v/@google/gemini-cli)](https://www.npmjs.com/package/@google/gemini-cli)
[![Wiki](https://img.shields.io/badge/docs-Wiki-blue)](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)
[![Advertising Hub](https://img.shields.io/badge/ecosystem-Advertising%20Hub-orange)](https://github.com/itallstartedwithaidea/advertising-hub)
[![googleadsagent.ai](https://img.shields.io/badge/site-googleadsagent.ai-green)](https://googleadsagent.ai)

**Parte del ecosistema
[Advertising Hub](https://github.com/itallstartedwithaidea/advertising-hub)** — 14 APIs de plataformas publicitarias, 25+ agentes IA, servidores MCP |
[googleadsagent.ai](https://googleadsagent.ai) |
[MiniAgent](https://github.com/itallstartedwithaidea/MiniAgent)

---

## ¿Qué herramienta necesitas?

| Yo uso...                        | Instalar esto                                                                                                                                               | Tiempo de configuración |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- |
| **Gemini CLI** (terminal)        | [google-ads-gemini-extension](https://github.com/itallstartedwithaidea/google-ads-gemini-extension)                                                         | ~15 min                 |
| **Claude** (Desktop o Code)      | [google-ads-skills](https://github.com/itallstartedwithaidea/google-ads-skills) + [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) | ~15 min                 |
| **Cursor / Windsurf / Otro**     | [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) (Python, 29 herramientas)                                                         | ~15 min                 |
| **Solo quiero que lo gestionen** | [googleadsagent.ai](https://googleadsagent.ai) — sin configuración necesaria                                                                                | 0 min                   |

> **Guía de configuración paso a paso con capturas de pantalla:**
> **[googleadsagent.ai/setup](https://googleadsagent.ai/setup/)** — cubre cada
> ruta, cada credencial, cada trampa. No se requiere título de ingeniería.

---

## Comandos de Google Ads

Este fork extiende Gemini CLI con tres comandos slash de Google Ads y una habilidad de agente específica del dominio.

### `/google-ads-analyze` — Análisis de rendimiento de campañas

```
/google-ads-analyze Show me top spending campaigns last 30 days with declining ROAS
```

- Sugiere consultas GAQL relevantes para extraer los datos
- Presenta hallazgos en tablas claras
- Identifica anomalías y oportunidades
- Recomienda próximos pasos específicos y accionables

### `/google-ads-audit` — Auditoría integral de cuenta

```
/google-ads-audit Full audit of the Hopeworks nonprofit account
```

Cubre 7 áreas de auditoría con niveles de severidad (Crítico / Alto / Medio / Bajo):

- Estructura de cuenta, estrategia de pujas, asignación de presupuesto
- Salud de palabras clave, creatividades, segmentación, seguimiento de conversiones

### `/google-ads-optimize` — Recomendaciones de optimización

```
/google-ads-optimize We need to reduce CPA by 15% without losing volume
```

- Identifica las 3 a 5 oportunidades de optimización de mayor impacto
- Prioriza por esfuerzo vs impacto con niveles de riesgo
- Cubre gasto desperdiciado, eficiencia de pujas, fatiga creativa y brechas de segmentación

### Habilidad de agente Google Ads

La habilidad incluida (`.gemini/skills/google-ads-agent/`) se activa automáticamente para cualquier pregunta relacionada con publicidad. Proporciona:

- **Experiencia GAQL** — conoce la sintaxis de Google Ads Query Language, patrones comunes y conversión de micro-unidades de coste
- **Conocimiento de API v22** — versión actual de la API, patrones de autenticación, límites de velocidad
- **Análisis de campañas** — tendencias, anomalías, bajo rendimiento, asignación de presupuesto
- **Seguridad de escritura** — siempre presenta los cambios propuestos antes de ejecutarlos

## Inicio rápido — Solo quiero usarlo

La mayoría de usuarios quieren este camino. Tres comandos, ~15 minutos:

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

Necesitas 5 valores de credenciales de Google Ads, Google Cloud Console y OAuth Playground. La **[guía de configuración completa](https://googleadsagent.ai/setup/)** te guía paso a paso con capturas de pantalla.

### Inicio rápido — Quiero contribuir / desarrollar

Si quieres modificar el CLI en sí (no solo usar la extensión):

```bash
git clone https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent.git
cd gemini-cli-googleadsagent
npm install
npm run build
npm start
```

O copia solo los comandos/habilidades de Google Ads a cualquier proyecto:

```bash
cp -r gemini-cli-googleadsagent/.gemini/commands/google-ads-*.toml your-project/.gemini/commands/
cp -r gemini-cli-googleadsagent/.gemini/skills/google-ads-agent/ your-project/.gemini/skills/
```

## Proyectos relacionados

| Proyecto                                                                                              | Descripción                                                           |
| ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| [**advertising-hub**](https://github.com/itallstartedwithaidea/advertising-hub)                       | Punto central para 14 APIs de plataformas pub, servidores MCP y agentes |
| [**google-ads-api-agent**](https://github.com/itallstartedwithaidea/google-ads-api-agent)             | Agente empresarial Google Ads — 28 acciones API, lectura/escritura en vivo |
| [**google-ads-mcp**](https://github.com/itallstartedwithaidea/google-ads-mcp)                         | Servidor MCP para acceso a la API de Google Ads                        |
| [**google-ads-skills**](https://github.com/itallstartedwithaidea/google-ads-skills)                   | Habilidades Claude Code / Codex / Gemini CLI para Google Ads           |
| [**MiniAgent**](https://github.com/itallstartedwithaidea/MiniAgent)                                   | IA publicitaria entrenable de 26M parámetros + 14 servidores MCP       |
| [**google-ads-claudecodeskill**](https://github.com/itallstartedwithaidea/google-ads-claudecodeskill) | Habilidad de Claude Code para la gestión de Google Ads                 |

---

## Documentación

La documentación completa está disponible en el **[Wiki](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)**:

- [Primeros pasos](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Getting-Started) — Instalación, autenticación, primera ejecución
- [Referencia de comandos](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Commands-Reference) — Documentación completa de los tres comandos con ejemplos
- [Habilidad de agente Google Ads](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Google-Ads-Agent-Skill) — Patrones GAQL, conocimiento API v22, seguridad de escritura
- [Configuración](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Configuration) — Ajustes, variables de entorno, selección de modelo
- [Proyectos relacionados](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Related-Projects) — Visión general completa del ecosistema

---

## Acerca de Gemini CLI (upstream)

Este es un fork de [google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli) con extensiones específicas para Google Ads.

Gemini CLI es un agente de IA de código abierto que lleva el poder de Gemini directamente a tu terminal. Proporciona acceso ligero a Gemini, dándote el camino más directo desde tu prompt hasta nuestro modelo.

Aprende todo sobre Gemini CLI en la [documentación oficial](https://geminicli.com/docs/).

## ¿Por qué Gemini CLI?

- **Nivel gratuito**: 60 solicitudes/min y 1.000 solicitudes/día con cuenta personal de Google.
- **Potentes modelos Gemini 3**: Acceso a razonamiento mejorado y ventana de contexto de 1M de tokens.
- **Herramientas integradas**: Google Search, operaciones de archivos, comandos shell, obtención web.
- **Extensible**: Soporte MCP (Model Context Protocol) para integraciones personalizadas.
- **Terminal primero**: Diseñado para desarrolladores que viven en la línea de comandos.
- **Código abierto**: Licencia Apache 2.0.

## Instalación

Ver [Instalación, ejecución y versiones de Gemini CLI](./docs/get-started/installation.md) para especificaciones del sistema recomendadas y una guía de instalación detallada.

### Instalación rápida

#### Ejecutar al instante con npx

```bash
npx @google/gemini-cli
```

#### Instalar globalmente con npm

```bash
npm install -g @google/gemini-cli
```

#### Instalar globalmente con Homebrew (macOS/Linux)

```bash
brew install gemini-cli
```

#### Instalar globalmente con MacPorts (macOS)

```bash
sudo port install gemini-cli
```

#### Instalar con Anaconda (para entornos restringidos)

```bash
conda create -y -n gemini_env -c conda-forge nodejs
conda activate gemini_env
npm install -g @google/gemini-cli
```

## Cadencia de versiones y etiquetas

Ver [Versiones](./docs/releases.md) para más detalles.

### Preview

Nuevas versiones preview se publican cada semana los martes a las 23:59 UTC. Estas versiones no han sido completamente verificadas y pueden contener regresiones u otros problemas pendientes. Ayúdanos a probar e instala con la etiqueta `preview`.

```bash
npm install -g @google/gemini-cli@preview
```

### Stable

Nuevas versiones estables se publican cada semana los martes a las 20:00 UTC, siendo la promoción completa de la versión `preview` de la semana anterior + correcciones de bugs y validaciones. Usa la etiqueta `latest`.

```bash
npm install -g @google/gemini-cli@latest
```

### Nightly

Nuevas versiones se publican cada día a las 00:00 UTC. Incluyen todos los cambios de la rama main al momento de la publicación. Se asume que hay validaciones y problemas pendientes. Usa la etiqueta `nightly`.

```bash
npm install -g @google/gemini-cli@nightly
```

## Funcionalidades clave

### Comprensión y generación de código

- Consultar y editar grandes bases de código
- Generar nuevas aplicaciones a partir de PDFs, imágenes o bocetos usando capacidades multimodales
- Depurar problemas y solucionar incidencias con lenguaje natural

### Automatización e integración

- Automatizar tareas operativas como consultar pull requests o manejar rebases complejos
- Usar servidores MCP para conectar nuevas capacidades, incluyendo [generación de medios con Imagen, Veo o Lyria](https://github.com/GoogleCloudPlatform/vertex-ai-creative-studio/tree/main/experiments/mcp-genmedia)
- Ejecutar de forma no interactiva en scripts para automatización de flujos de trabajo

### Capacidades avanzadas

- Fundamentar consultas con [Google Search](https://ai.google.dev/gemini-api/docs/grounding) integrado para información en tiempo real
- Puntos de guardado de conversaciones para guardar y reanudar sesiones complejas
- Archivos de contexto personalizados (GEMINI.md) para adaptar el comportamiento a tus proyectos

### Integración con GitHub

Integra Gemini CLI directamente en tus flujos de trabajo de GitHub con [**Gemini CLI GitHub Action**](https://github.com/google-github-actions/run-gemini-cli):

- **Revisiones de Pull Requests**: Revisión de código automatizada con comentarios contextuales y sugerencias
- **Triaje de Issues**: Etiquetado y priorización automatizados de issues de GitHub basados en análisis de contenido
- **Asistencia bajo demanda**: Menciona `@gemini-cli` en issues y pull requests para ayuda con depuración, explicaciones o delegación de tareas
- **Flujos personalizados**: Construye flujos de trabajo automatizados, programados y bajo demanda adaptados a las necesidades de tu equipo

## Opciones de autenticación

Elige el método de autenticación que mejor se adapte a tus necesidades:

### Opción 1: Iniciar sesión con Google (inicio de sesión OAuth con tu cuenta de Google)

**Ideal para:** Desarrolladores individuales y cualquier persona con licencia Gemini Code Assist.

**Beneficios:**

- **Nivel gratuito**: 60 solicitudes/min y 1.000 solicitudes/día
- **Modelos Gemini 3** con ventana de contexto de 1M de tokens
- **Sin gestión de claves API** — solo inicia sesión con tu cuenta de Google
- **Actualizaciones automáticas** a los últimos modelos

```bash
gemini
```

```bash
export GOOGLE_CLOUD_PROJECT="YOUR_PROJECT_ID"
gemini
```

### Opción 2: Clave API de Gemini

**Ideal para:** Desarrolladores que necesitan control específico del modelo o acceso al nivel de pago

```bash
export GEMINI_API_KEY="YOUR_API_KEY"
gemini
```

### Opción 3: Vertex AI

**Ideal para:** Equipos empresariales y cargas de producción

```bash
export GOOGLE_API_KEY="YOUR_API_KEY"
export GOOGLE_GENAI_USE_VERTEXAI=true
gemini
```

Para cuentas Google Workspace y otros métodos de autenticación, consulta la [guía de autenticación](./docs/get-started/authentication.md).

## Primeros pasos

### Uso básico

```bash
gemini
gemini --include-directories ../lib,../docs
gemini -m gemini-2.5-flash
gemini -p "Explain the architecture of this codebase"
gemini -p "Explain the architecture of this codebase" --output-format json
gemini -p "Run tests and deploy" --output-format stream-json
```

## Documentación

### Primeros pasos

- [**Guía de inicio rápido**](./docs/get-started/index.md)
- [**Configuración de autenticación**](./docs/get-started/authentication.md)
- [**Guía de configuración**](./docs/reference/configuration.md)
- [**Atajos de teclado**](./docs/reference/keyboard-shortcuts.md)

### Funcionalidades principales

- [**Referencia de comandos**](./docs/reference/commands.md)
- [**Comandos personalizados**](./docs/cli/custom-commands.md)
- [**Archivos de contexto (GEMINI.md)**](./docs/cli/gemini-md.md)
- [**Puntos de guardado**](./docs/cli/checkpointing.md)
- [**Caché de tokens**](./docs/cli/token-caching.md)

### Herramientas y extensiones

- [**Vista general de herramientas integradas**](./docs/reference/tools.md)
- [**Integración de servidores MCP**](./docs/tools/mcp-server.md)
- [**Extensiones personalizadas**](./docs/extensions/index.md)

### Temas avanzados

- [**Modo headless (scripting)**](./docs/cli/headless.md)
- [**Vista general de la arquitectura**](./docs/architecture.md)
- [**Integración IDE**](./docs/ide-integration/index.md)
- [**Sandbox y seguridad**](./docs/cli/sandbox.md)
- [**Carpetas de confianza**](./docs/cli/trusted-folders.md)
- [**Guía empresarial**](./docs/cli/enterprise.md)
- [**Telemetría y monitorización**](./docs/cli/telemetry.md)

### Solución de problemas y soporte

- [**Guía de solución de problemas**](./docs/resources/troubleshooting.md)
- [**FAQ**](./docs/resources/faq.md)
- Usa el comando `/bug` para reportar problemas directamente desde el CLI.

## Contribuir

¡Las contribuciones son bienvenidas! Gemini CLI es totalmente de código abierto (Apache 2.0), y animamos a la comunidad a:

- Reportar bugs y sugerir funcionalidades.
- Mejorar la documentación.
- Enviar mejoras de código.
- Compartir tus servidores MCP y extensiones.

Consulta nuestra [Guía de contribución](./CONTRIBUTING.md) para la configuración de desarrollo, estándares de codificación y cómo enviar pull requests.

## Recursos

- **[Hoja de ruta oficial](./ROADMAP.md)**
- **[Registro de cambios](./docs/changelogs/index.md)**
- **[Paquete NPM](https://www.npmjs.com/package/@google/gemini-cli)**
- **[Issues de GitHub](https://github.com/google-gemini/gemini-cli/issues)**
- **[Avisos de seguridad](https://github.com/google-gemini/gemini-cli/security/advisories)**

### Desinstalación

Ver la [Guía de desinstalación](./docs/resources/uninstall.md) para instrucciones de eliminación.

## Legal

- **Licencia**: [Licencia Apache 2.0](LICENSE)
- **Términos de servicio**: [Términos y privacidad](./docs/resources/tos-privacy.md)
- **Seguridad**: [Política de seguridad](SECURITY.md)

---

<p align="center">
  Upstream: Construido con ❤️ por Google y la comunidad de código abierto<br>
  Extensiones de Google Ads por <a href="https://github.com/itallstartedwithaidea">John Williams</a> — Team Lead, Paid Media @ Seer Interactive | <a href="https://googleadsagent.ai">googleadsagent.ai</a>
</p>
