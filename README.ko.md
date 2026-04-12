# Gemini CLI + Google Ads Agent

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh.md) | [Nederlands](README.nl.md) | [Русский](README.ru.md) | [한국어](README.ko.md)

> **[Gemini CLI](https://github.com/google-gemini/gemini-cli)를 위한 오픈소스 Google Ads 관리 명령어 및 AI 에이전트 스킬.** 캠페인 성과 분석, 계정 감사, PPC 지출 최적화, GAQL 쿼리 생성 — 모두 터미널에서.

[![License](https://img.shields.io/github/license/google-gemini/gemini-cli)](https://github.com/google-gemini/gemini-cli/blob/main/LICENSE)
[![Version](https://img.shields.io/npm/v/@google/gemini-cli)](https://www.npmjs.com/package/@google/gemini-cli)
[![Wiki](https://img.shields.io/badge/docs-Wiki-blue)](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)
[![Advertising Hub](https://img.shields.io/badge/ecosystem-Advertising%20Hub-orange)](https://github.com/itallstartedwithaidea/advertising-hub)
[![googleadsagent.ai](https://img.shields.io/badge/site-googleadsagent.ai-green)](https://googleadsagent.ai)

**[Advertising Hub](https://github.com/itallstartedwithaidea/advertising-hub) 생태계의 일부** — 14개 광고 플랫폼 API, 25+ AI 에이전트, MCP 서버 |
[googleadsagent.ai](https://googleadsagent.ai) |
[MiniAgent](https://github.com/itallstartedwithaidea/MiniAgent)

---

## 어떤 도구가 필요한가요?

| 내가 사용하는 것...              | 이것을 설치                                                                                                                                                 | 설정 시간 |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| **Gemini CLI** (터미널)          | [google-ads-gemini-extension](https://github.com/itallstartedwithaidea/google-ads-gemini-extension)                                                         | ~15분     |
| **Claude** (Desktop 또는 Code)   | [google-ads-skills](https://github.com/itallstartedwithaidea/google-ads-skills) + [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) | ~15분     |
| **Cursor / Windsurf / 기타**     | [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) (Python, 29개 도구)                                                                | ~15분     |
| **관리형 서비스를 원합니다**     | [googleadsagent.ai](https://googleadsagent.ai) — 설정 불필요                                                                                                | 0분       |

> **스크린샷이 포함된 단계별 설정 가이드:**
> **[googleadsagent.ai/setup](https://googleadsagent.ai/setup/)**

---

## Google Ads 명령어

이 포크는 Gemini CLI에 3개의 Google Ads 슬래시 명령어와 도메인 특화 에이전트 스킬을 추가합니다.

### `/google-ads-analyze` — 캠페인 성과 분석

```
/google-ads-analyze Show me top spending campaigns last 30 days with declining ROAS
```

- 데이터 추출을 위한 관련 GAQL 쿼리 제안
- 명확한 표로 결과 제시
- 이상 징후와 기회 식별
- 구체적이고 실행 가능한 다음 단계 권장

### `/google-ads-audit` — 종합 계정 감사

```
/google-ads-audit Full audit of the Hopeworks nonprofit account
```

심각도 등급(위험 / 높음 / 중간 / 낮음)과 함께 7개 감사 영역을 다룹니다:

- 계정 구조, 입찰 전략, 예산 배분
- 키워드 건강 상태, 광고 크리에이티브, 타겟팅, 전환 추적

### `/google-ads-optimize` — 최적화 권장사항

```
/google-ads-optimize We need to reduce CPA by 15% without losing volume
```

- 영향력이 가장 높은 상위 3-5개 최적화 기회 식별
- 리스크 수준과 함께 노력 대비 영향으로 우선순위 지정
- 낭비 지출, 입찰 효율성, 크리에이티브 피로, 타겟팅 갭 포함

### Google Ads 에이전트 스킬

포함된 스킬(`.gemini/skills/google-ads-agent/`)은 광고 관련 질문에 자동으로 활성화됩니다:

- **GAQL 전문성** — Google Ads Query Language 구문, 일반 패턴, 비용 마이크로 변환 파악
- **API v22 지식** — 현재 API 버전, 인증 패턴, 속도 제한
- **캠페인 분석** — 트렌드, 이상 징후, 저성과자, 예산 배분
- **쓰기 안전성** — 실행 전 항상 제안된 변경사항 제시

## 빠른 시작 — 바로 사용하고 싶어요

대부분의 사용자가 원하는 경로입니다. 세 가지 명령어, ~15분:

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

Google Ads, Google Cloud Console, OAuth Playground에서 5개의 자격 증명 값이 필요합니다. **[전체 설정 가이드](https://googleadsagent.ai/setup/)** 에서 스크린샷과 함께 모든 단계를 안내합니다.

### 빠른 시작 — 기여/개발하고 싶어요

```bash
git clone https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent.git
cd gemini-cli-googleadsagent
npm install
npm run build
npm start
```

## 관련 프로젝트

| 프로젝트                                                                                              | 설명                                                            |
| ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| [**advertising-hub**](https://github.com/itallstartedwithaidea/advertising-hub)                       | 14개 광고 플랫폼 API, MCP 서버, 에이전트 통합 허브              |
| [**google-ads-api-agent**](https://github.com/itallstartedwithaidea/google-ads-api-agent)             | 엔터프라이즈 Google Ads 에이전트 — 28개 API 액션, 실시간 읽기/쓰기 |
| [**google-ads-mcp**](https://github.com/itallstartedwithaidea/google-ads-mcp)                         | Google Ads API 접근용 MCP 서버                                   |
| [**google-ads-skills**](https://github.com/itallstartedwithaidea/google-ads-skills)                   | Claude Code / Codex / Gemini CLI용 Google Ads 스킬               |
| [**MiniAgent**](https://github.com/itallstartedwithaidea/MiniAgent)                                   | 훈련 가능한 2600만 파라미터 광고 AI + 14개 MCP 서버              |
| [**google-ads-claudecodeskill**](https://github.com/itallstartedwithaidea/google-ads-claudecodeskill) | Google Ads 관리용 Claude Code 스킬                               |

---

## 문서

전체 문서는 **[Wiki](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)** 에서 확인할 수 있습니다:

- [시작하기](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Getting-Started) — 설치, 인증, 첫 실행
- [명령어 참조](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Commands-Reference) — 모든 명령어의 전체 문서 및 예제
- [Google Ads 에이전트 스킬](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Google-Ads-Agent-Skill) — GAQL 패턴, API v22 지식, 쓰기 안전성
- [설정](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Configuration) — 설정, 환경 변수, 모델 선택
- [관련 프로젝트](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Related-Projects) — 전체 생태계 개요

---

## Gemini CLI (업스트림) 소개

이것은 Google Ads 전용 확장이 추가된 [google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli)의 포크입니다.

Gemini CLI는 Gemini의 강력한 기능을 터미널에 직접 제공하는 오픈소스 AI 에이전트입니다. [공식 문서](https://geminicli.com/docs/)에서 자세히 알아보세요.

## 왜 Gemini CLI인가?

- **무료 티어**: 개인 Google 계정으로 60 요청/분, 1,000 요청/일.
- **강력한 Gemini 3 모델**: 향상된 추론 및 1M 토큰 컨텍스트 윈도우.
- **내장 도구**: Google Search, 파일 작업, Shell 명령어, 웹 페치.
- **확장 가능**: 커스텀 통합을 위한 MCP 지원.
- **터미널 퍼스트**: 커맨드 라인에서 작업하는 개발자를 위해 설계.
- **오픈소스**: Apache 2.0 라이선스.

## 설치

```bash
npx @google/gemini-cli
npm install -g @google/gemini-cli
brew install gemini-cli
```

## 인증 옵션

- **옵션 1**: Google로 로그인 (OAuth) — 무료: 60 요청/분
- **옵션 2**: Gemini API 키 — `export GEMINI_API_KEY="YOUR_API_KEY"`
- **옵션 3**: Vertex AI — 엔터프라이즈 팀용

## 문서 링크

- [빠른 시작 가이드](./docs/get-started/index.md) | [인증 설정](./docs/get-started/authentication.md) | [설정 가이드](./docs/reference/configuration.md)
- [명령어 참조](./docs/reference/commands.md) | [커스텀 명령어](./docs/cli/custom-commands.md) | [GEMINI.md](./docs/cli/gemini-md.md)
- [내장 도구](./docs/reference/tools.md) | [MCP 서버 통합](./docs/tools/mcp-server.md)
- [문제 해결](./docs/resources/troubleshooting.md) | [FAQ](./docs/resources/faq.md)

## 기여

기여를 환영합니다! [기여 가이드](./CONTRIBUTING.md)를 참조하세요.

## 법적 고지

- **라이선스**: [Apache License 2.0](LICENSE)
- **이용약관**: [약관 및 개인정보](./docs/resources/tos-privacy.md)
- **보안**: [보안 정책](SECURITY.md)

---

<p align="center">
  업스트림: Google과 오픈소스 커뮤니티가 ❤️로 제작<br>
  Google Ads 확장은 <a href="https://github.com/itallstartedwithaidea">John Williams</a> 제작 — Team Lead, Paid Media @ Seer Interactive | <a href="https://googleadsagent.ai">googleadsagent.ai</a>
</p>
