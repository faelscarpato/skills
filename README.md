# 📚 Skills Library

> **449 AI-ready skills across 19 categories** — each skill is a complete system prompt ready to inject into any LLM.

[![Site](https://img.shields.io/badge/Library-faelscarpato.github.io%2Fskills-7c6af0?style=flat-square)](https://faelscarpato.github.io/skills/)
[![Skills](https://img.shields.io/badge/skills-449-3dd6a3?style=flat-square)](./skills.json)
[![Categories](https://img.shields.io/badge/categories-19-fdba74?style=flat-square)](./skills.json)

---

## 🚀 Quick Start

### 1. Browse the library
→ https://faelscarpato.github.io/skills/

### 2. Fetch a skill directly
```bash
# Replace {category} and {skill} with the values from the table below
curl https://raw.githubusercontent.com/faelscarpato/skills/main/.agents/skills/{category}/{skill}/SKILL.md

# Example:
curl https://raw.githubusercontent.com/faelscarpato/skills/main/.agents/skills/_ai-agentes/agent-browser/SKILL.md
```

### 3. Use with AI agents
```bash
# Load the skills manifest for AI routing
curl https://raw.githubusercontent.com/faelscarpato/skills/main/skills-manifest.json

# Or use the flat route map for instant lookup
curl https://raw.githubusercontent.com/faelscarpato/skills/main/skills-routes.json
```

---

## 📁 Skill File Format

Every skill lives at: `.agents/skills/{category}/{skill}/SKILL.md`

```yaml
---
name: skill-name
description: "Description. Use for: use cases. Triggers: keywords."
allowed-tools: Bash(*), Read, Write, WebSearch
---

# Role Title
You are an expert in...

## Instructions
...

## Rules
...

## Output Format
...
```

---

## 📂 Categories

| Category | Skills | Path | Browse |
|---|---|---|---|
| 🤖 **AI & Agentes** | 68 | `.agents/skills/_ai-agentes` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_ai-agentes) |
| 🔗 **Automação & Integrações** | 20 | `.agents/skills/_automação-integrações` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_automa%C3%A7%C3%A3o-integra%C3%A7%C3%B5es) |
| 🔧 **Backend & APIs** | 28 | `.agents/skills/_backend-apis` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_backend-apis) |
| 🗄️ **Banco de Dados** | 13 | `.agents/skills/_banco-de-dados` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_banco-de-dados) |
| ☁️ **Cloud & DevOps** | 33 | `.agents/skills/_cloud-devops` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_cloud-devops) |
| 📝 **Conteúdo & Escrita** | 15 | `.agents/skills/_conteúdo-escrita` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_conte%C3%BAdo-escrita) |
| 📊 **Dados & Analytics** | 11 | `.agents/skills/_dados-analytics` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_dados-analytics) |
| 🎨 **Design & UI/UX** | 34 | `.agents/skills/_design-ui-ux` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_design-ui-ux) |
| ⚛️ **Frontend React JS TS** | 27 | `.agents/skills/_frontend-react-js-ts` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_frontend-react-js-ts) |
| 🎮 **Games** | 4 | `.agents/skills/_games` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_games) |
| ⚖️ **Legal & Compliance** | 4 | `.agents/skills/_legal-compliance` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_legal-compliance) |
| ⚙️ **Linguagens & Ferramentas** | 13 | `.agents/skills/_linguagens-ferramentas` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_linguagens-ferramentas) |
| 🎵 **Mídia & Criação** | 14 | `.agents/skills/_mídia-criação` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_m%C3%ADdia-cria%C3%A7%C3%A3o) |
| 📱 **Mobile** | 8 | `.agents/skills/_mobile` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_mobile) |
| 🗂️ **Outros** | 120 | `.agents/skills/_outros` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_outros) |
| 🚀 **Produto & Marketing** | 11 | `.agents/skills/_produto-marketing` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_produto-marketing) |
| 🧠 **Prompts & LLM** | 4 | `.agents/skills/_prompts-llm` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_prompts-llm) |
| 🔒 **Segurança** | 10 | `.agents/skills/_segurança` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_seguran%C3%A7a) |
| 🧪 **Testes & QA** | 13 | `.agents/skills/_testes-qa` | [→](https://github.com/faelscarpato/skills/tree/main/.agents/skills/_testes-qa) |
| | **449** | | |

---

## 🤖 For AI Agents & LLM Tools

This repository is structured for AI consumption. Available indexes:

| File | Description | URL |
|---|---|---|
| `skills.json` | Category → skills index | [raw](https://raw.githubusercontent.com/faelscarpato/skills/main/skills.json) |
| `skills-manifest.json` | Full manifest with all URLs | [raw](https://raw.githubusercontent.com/faelscarpato/skills/main/skills-manifest.json) |
| `skills-routes.json` | Flat slug → URL map (449 entries) | [raw](https://raw.githubusercontent.com/faelscarpato/skills/main/skills-routes.json) |
| `llms.txt` | Standard llms.txt for AI crawlers | [raw](https://raw.githubusercontent.com/faelscarpato/skills/main/llms.txt) |
| `SKILLS_DOCS.md` | Full docs with all routes | [raw](https://raw.githubusercontent.com/faelscarpato/skills/main/SKILLS_DOCS.md) |

### How AI agents should use this library

1. **Discover** — fetch `skills-routes.json` to get all 449 skills and their raw URLs
2. **Match** — find the skill slug matching the user's task
3. **Fetch** — GET the `raw` URL from the route entry
4. **Inject** — use the SKILL.md content as system prompt or context
5. **Execute** — follow the skill's role, instructions and output format

---

## 📜 License

MIT — free to use, modify and distribute.

---

*Browse the library at → https://faelscarpato.github.io/skills/*