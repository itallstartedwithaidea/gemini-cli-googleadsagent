# Gemini CLI + Google Ads Agent

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh.md) | [Nederlands](README.nl.md) | [Русский](README.ru.md) | [한국어](README.ko.md)

> **面向 [Gemini CLI](https://github.com/google-gemini/gemini-cli) 的开源 Google Ads 管理命令和 AI 代理技能。** 分析广告系列效果、审计账户、优化 PPC 支出、生成 GAQL 查询 — 一切在终端中完成。

[![License](https://img.shields.io/github/license/google-gemini/gemini-cli)](https://github.com/google-gemini/gemini-cli/blob/main/LICENSE)
[![Version](https://img.shields.io/npm/v/@google/gemini-cli)](https://www.npmjs.com/package/@google/gemini-cli)
[![Wiki](https://img.shields.io/badge/docs-Wiki-blue)](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)
[![Advertising Hub](https://img.shields.io/badge/ecosystem-Advertising%20Hub-orange)](https://github.com/itallstartedwithaidea/advertising-hub)
[![googleadsagent.ai](https://img.shields.io/badge/site-googleadsagent.ai-green)](https://googleadsagent.ai)

**[Advertising Hub](https://github.com/itallstartedwithaidea/advertising-hub) 生态系统的一部分** — 14 个广告平台 API、25+ AI 代理、MCP 服务器 |
[googleadsagent.ai](https://googleadsagent.ai) |
[MiniAgent](https://github.com/itallstartedwithaidea/MiniAgent)

---

## 你需要哪个工具？

| 我使用...                    | 安装这个                                                                                                                                                    | 配置时间 |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| **Gemini CLI**（终端）       | [google-ads-gemini-extension](https://github.com/itallstartedwithaidea/google-ads-gemini-extension)                                                         | ~15 分钟 |
| **Claude**（Desktop 或 Code）| [google-ads-skills](https://github.com/itallstartedwithaidea/google-ads-skills) + [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp) | ~15 分钟 |
| **Cursor / Windsurf / 其他** | [google-ads-mcp](https://github.com/itallstartedwithaidea/google-ads-mcp)（Python，29 个工具）                                                               | ~15 分钟 |
| **我只想要托管服务**         | [googleadsagent.ai](https://googleadsagent.ai) — 无需配置                                                                                                   | 0 分钟   |

> **带截图的分步配置指南：**
> **[googleadsagent.ai/setup](https://googleadsagent.ai/setup/)** — 涵盖每个路径、每个凭据、每个注意事项。无需工程学位。

---

## Google Ads 命令

此 fork 为 Gemini CLI 添加了三个 Google Ads 斜杠命令和一个特定领域的代理技能。

### `/google-ads-analyze` — 广告系列效果分析

```
/google-ads-analyze Show me top spending campaigns last 30 days with declining ROAS
```

- 建议相关的 GAQL 查询来提取数据
- 以清晰的表格呈现结果
- 识别异常和机会
- 推荐具体可行的下一步

### `/google-ads-audit` — 全面账户审计

```
/google-ads-audit Full audit of the Hopeworks nonprofit account
```

涵盖 7 个审计领域，附带严重程度评级（关键 / 高 / 中 / 低）：

- 账户结构、出价策略、预算分配
- 关键词健康状况、广告创意、定向、转化跟踪

### `/google-ads-optimize` — 优化建议

```
/google-ads-optimize We need to reduce CPA by 15% without losing volume
```

- 识别前 3-5 个最高影响力的优化机会
- 按投入 vs 影响排序，附风险等级
- 涵盖浪费支出、出价效率、创意疲劳和定向缺口

### Google Ads 代理技能

内置的技能（`.gemini/skills/google-ads-agent/`）对任何广告相关问题自动激活。它提供：

- **GAQL 专业知识** — 了解 Google Ads Query Language 语法、常见模式和成本微转换
- **API v22 知识** — 当前 API 版本、认证模式、速率限制
- **广告系列分析** — 趋势、异常、低效表现者、预算分配
- **写入安全** — 执行前始终展示拟议更改

## 快速开始 — 我只想使用它

大多数用户想要这条路线。三个命令，约 15 分钟：

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

你需要来自 Google Ads、Google Cloud Console 和 OAuth Playground 的 5 个凭据值。**[完整配置指南](https://googleadsagent.ai/setup/)** 附带截图详细说明每个步骤。

### 快速开始 — 我想贡献 / 开发

如果你想修改 CLI 本身（而不仅是使用扩展）：

```bash
git clone https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent.git
cd gemini-cli-googleadsagent
npm install
npm run build
npm start
```

或仅将 Google Ads 命令/技能复制到任何项目：

```bash
cp -r gemini-cli-googleadsagent/.gemini/commands/google-ads-*.toml your-project/.gemini/commands/
cp -r gemini-cli-googleadsagent/.gemini/skills/google-ads-agent/ your-project/.gemini/skills/
```

## 相关项目

| 项目                                                                                                  | 描述                                                        |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| [**advertising-hub**](https://github.com/itallstartedwithaidea/advertising-hub)                       | 14 个广告平台 API、MCP 服务器和代理的一站式中心             |
| [**google-ads-api-agent**](https://github.com/itallstartedwithaidea/google-ads-api-agent)             | 企业级 Google Ads 代理 — 28 个 API 操作，实时读写           |
| [**google-ads-mcp**](https://github.com/itallstartedwithaidea/google-ads-mcp)                         | Google Ads API 访问的 MCP 服务器                            |
| [**google-ads-skills**](https://github.com/itallstartedwithaidea/google-ads-skills)                   | Claude Code / Codex / Gemini CLI 的 Google Ads 技能         |
| [**MiniAgent**](https://github.com/itallstartedwithaidea/MiniAgent)                                   | 可训练的 2600 万参数广告 AI + 14 个 MCP 服务器              |
| [**google-ads-claudecodeskill**](https://github.com/itallstartedwithaidea/google-ads-claudecodeskill) | Claude Code 的 Google Ads 管理技能                          |

---

## 文档

完整文档可在 **[Wiki](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki)** 上查阅：

- [入门指南](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Getting-Started) — 安装、认证、首次运行
- [命令参考](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Commands-Reference) — 三个命令的完整文档及示例
- [Google Ads 代理技能](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Google-Ads-Agent-Skill) — GAQL 模式、API v22 知识、写入安全
- [配置](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Configuration) — 设置、环境变量、模型选择
- [相关项目](https://github.com/itallstartedwithaidea/gemini-cli-googleadsagent/wiki/Related-Projects) — 完整生态系统概览

---

## 关于 Gemini CLI（上游）

这是 [google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli) 的 fork，添加了 Google Ads 特定的扩展。

Gemini CLI 是一个开源 AI 代理，将 Gemini 的强大功能直接带入你的终端。它提供了对 Gemini 的轻量级访问，为你提供从提示到模型的最直接路径。

在[官方文档](https://geminicli.com/docs/)中了解更多关于 Gemini CLI 的信息。

## 为什么选择 Gemini CLI？

- **免费层级**：个人 Google 账户可享 60 次请求/分钟和 1,000 次请求/天。
- **强大的 Gemini 3 模型**：改进的推理能力和 100 万 token 上下文窗口。
- **内置工具**：Google Search、文件操作、Shell 命令、网页获取。
- **可扩展**：支持 MCP（模型上下文协议）自定义集成。
- **终端优先**：为命令行开发者设计。
- **开源**：Apache 2.0 许可证。

## 安装

参见 [Gemini CLI 安装、执行和发布](./docs/get-started/installation.md)了解推荐系统规格和详细安装指南。

### 快速安装

```bash
# 使用 npx（无需安装）
npx @google/gemini-cli

# 使用 npm 全局安装
npm install -g @google/gemini-cli

# 使用 Homebrew（macOS/Linux）
brew install gemini-cli

# 使用 MacPorts（macOS）
sudo port install gemini-cli
```

## 发布节奏和标签

参见[发布说明](./docs/releases.md)了解更多详情。

- **Preview**：每周二 UTC 23:59 发布。安装：`npm install -g @google/gemini-cli@preview`
- **Stable**：每周二 UTC 20:00 发布。安装：`npm install -g @google/gemini-cli@latest`
- **Nightly**：每天 UTC 00:00 发布。安装：`npm install -g @google/gemini-cli@nightly`

## 关键特性

### 代码理解与生成

- 查询和编辑大型代码库
- 使用多模态能力从 PDF、图像或草图生成新应用
- 用自然语言调试问题和排除故障

### 自动化与集成

- 自动化操作任务，如查询 Pull Request 或处理复杂的 rebase
- 使用 MCP 服务器连接新功能
- 在脚本中非交互式运行以实现工作流自动化

### 高级功能

- 使用内置 [Google Search](https://ai.google.dev/gemini-api/docs/grounding) 为查询提供实时信息支持
- 对话检查点，用于保存和恢复复杂会话
- 自定义上下文文件（GEMINI.md）以根据项目定制行为

### GitHub 集成

使用 [**Gemini CLI GitHub Action**](https://github.com/google-github-actions/run-gemini-cli) 将 Gemini CLI 直接集成到 GitHub 工作流中：

- **Pull Request 审查**：具有上下文反馈和建议的自动化代码审查
- **Issue 分类**：基于内容分析的 GitHub Issue 自动标记和优先级排序
- **按需协助**：在 Issue 和 Pull Request 中提及 `@gemini-cli` 获取调试、解释或任务委派帮助
- **自定义工作流**：构建适合团队需求的自动化、定时和按需工作流

## 认证选项

### 选项 1：使用 Google 登录（OAuth）

个人开发者和 Gemini Code Assist 许可证持有者的最佳选择。免费：60 次请求/分钟，1,000 次请求/天。

```bash
gemini
```

### 选项 2：Gemini API 密钥

需要特定模型控制或付费层级访问的开发者的最佳选择。

```bash
export GEMINI_API_KEY="YOUR_API_KEY"
gemini
```

### 选项 3：Vertex AI

企业团队和生产负载的最佳选择。

```bash
export GOOGLE_API_KEY="YOUR_API_KEY"
export GOOGLE_GENAI_USE_VERTEXAI=true
gemini
```

## 文档链接

- [**快速入门指南**](./docs/get-started/index.md) | [**认证设置**](./docs/get-started/authentication.md) | [**配置指南**](./docs/reference/configuration.md)
- [**命令参考**](./docs/reference/commands.md) | [**自定义命令**](./docs/cli/custom-commands.md) | [**上下文文件**](./docs/cli/gemini-md.md)
- [**内置工具**](./docs/reference/tools.md) | [**MCP 服务器集成**](./docs/tools/mcp-server.md) | [**自定义扩展**](./docs/extensions/index.md)
- [**无头模式**](./docs/cli/headless.md) | [**架构概览**](./docs/architecture.md) | [**沙箱与安全**](./docs/cli/sandbox.md)
- [**故障排除**](./docs/resources/troubleshooting.md) | [**FAQ**](./docs/resources/faq.md)

## 贡献

欢迎贡献！Gemini CLI 是完全开源的（Apache 2.0）。参见我们的[贡献指南](./CONTRIBUTING.md)。

## 法律声明

- **许可证**：[Apache License 2.0](LICENSE)
- **服务条款**：[条款与隐私](./docs/resources/tos-privacy.md)
- **安全**：[安全策略](SECURITY.md)

---

<p align="center">
  上游：由 Google 和开源社区用 ❤️ 构建<br>
  Google Ads 扩展由 <a href="https://github.com/itallstartedwithaidea">John Williams</a> 开发 — Team Lead, Paid Media @ Seer Interactive | <a href="https://googleadsagent.ai">googleadsagent.ai</a>
</p>
