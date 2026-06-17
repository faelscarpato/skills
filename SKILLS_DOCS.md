# SKILLS_DOCS

Documentação operacional da biblioteca de skills do repositório `faelscarpato/skills`, pensada para qualquer IA localizar, interpretar e usar rapidamente as skills a partir de uma convenção única de rotas e arquivos [web:8][web:16].

## Objetivo

Esta documentação define como uma IA deve descobrir uma skill, localizar seu arquivo principal, montar links úteis e consumir a instrução completa com o menor número possível de tentativas [web:8][web:16].
A convenção parte do padrão aberto de agent skills, no qual cada skill vive em uma pasta própria e normalmente expõe um arquivo `SKILL.md` com metadados e instruções [web:8][web:16].

## Convenção de pastas

- Repositório base: [https://github.com/faelscarpato/skills](https://github.com/faelscarpato/skills) [web:16]
- Site base: [https://faelscarpato.github.io/skills/](https://faelscarpato.github.io/skills/)
- Raiz das skills: `.agents/skills/{categoria}/{skill}` [file:4]
- Arquivo principal preferencial: `SKILL.md` [web:16]
- Fallbacks aceitos: `README.md`, `skill.md`, `instructions.md`, `prompt.md`, `SYSTEM.md` [web:16]

## Regras para IAs

1. Ler `skills-manifest.json` para obter visão global de categorias, contagem e convenções de descoberta [code_file:22].
2. Ler `skills-routes.json` para resolver rapidamente a rota de uma skill sem precisar inferir caminhos [code_file:23].
3. Tentar abrir primeiro o `rawCandidates[0]`, que corresponde a `SKILL.md`; se falhar, seguir a ordem dos candidatos restantes [code_file:23][web:16].
4. Ao carregar o conteúdo, tratar o arquivo como instrução integral da skill, preservando frontmatter, markdown e exemplos [web:16].
5. Usar `websiteUrl` para navegação humana e `rawCandidates` para ingestão automatizada por agentes, indexadores ou RAG [code_file:23].

## Estrutura dos arquivos

| Arquivo | Função | Uso recomendado |
|---|---|---|
| `SKILLS_DOCS.md` | Documento humano com regras, convenções e exemplos de consumo | Leitura por devs e agentes com contexto amplo [code_file:21] |
| `skills-manifest.json` | Inventário resumido da biblioteca | Bootstrap rápido, dashboards, validação e cache [code_file:22] |
| `skills-routes.json` | Índice detalhado de rotas e candidatos de arquivos por skill | Resolução determinística de links e ingestão automatizada [code_file:23] |

## Modelo de rota

Cada skill deve ser tratada como um objeto roteável com estes campos mínimos [code_file:23]:

```json
{
  "category": "🤖 AI & Agentes",
  "skill": "agent-browser",
  "relativePath": ".agents/skills/🤖 AI & Agentes/agent-browser",
  "websiteUrl": "https://faelscarpato.github.io/skills/#skill=agent-browser&cat=🤖 AI & Agentes",
  "repositoryUrl": "https://github.com/faelscarpato/skills/tree/main/.agents/skills/🤖 AI & Agentes/agent-browser",
  "blobCandidates": [
    "https://github.com/faelscarpato/skills/blob/main/.agents/skills/🤖 AI & Agentes/agent-browser/SKILL.md",
    "https://github.com/faelscarpato/skills/blob/main/.agents/skills/🤖 AI & Agentes/agent-browser/README.md",
    "https://github.com/faelscarpato/skills/blob/main/.agents/skills/🤖 AI & Agentes/agent-browser/skill.md",
    "https://github.com/faelscarpato/skills/blob/main/.agents/skills/🤖 AI & Agentes/agent-browser/instructions.md",
    "https://github.com/faelscarpato/skills/blob/main/.agents/skills/🤖 AI & Agentes/agent-browser/prompt.md",
    "https://github.com/faelscarpato/skills/blob/main/.agents/skills/🤖 AI & Agentes/agent-browser/SYSTEM.md"
  ],
  "rawCandidates": [
    "https://raw.githubusercontent.com/faelscarpato/skills/main/.agents/skills/🤖 AI & Agentes/agent-browser/SKILL.md",
    "https://raw.githubusercontent.com/faelscarpato/skills/main/.agents/skills/🤖 AI & Agentes/agent-browser/README.md",
    "https://raw.githubusercontent.com/faelscarpato/skills/main/.agents/skills/🤖 AI & Agentes/agent-browser/skill.md",
    "https://raw.githubusercontent.com/faelscarpato/skills/main/.agents/skills/🤖 AI & Agentes/agent-browser/instructions.md",
    "https://raw.githubusercontent.com/faelscarpato/skills/main/.agents/skills/🤖 AI & Agentes/agent-browser/prompt.md",
    "https://raw.githubusercontent.com/faelscarpato/skills/main/.agents/skills/🤖 AI & Agentes/agent-browser/SYSTEM.md"
  ],
  "preferredEntryFile": "SKILL.md"
}
```

## Categorias

- `🤖 AI & Agentes`: 67 skills [code_file:22]
- `☁️ Azure SDK & Cloud`: 3 skills [code_file:22]
- `☁️ AWS & Cloud`: 6 skills [code_file:22]
- `☁️ GCP & Cloud`: 0 skills [code_file:22]
- `☁️ DevOps & Infra`: 24 skills [code_file:22]
- `⚖️ Legal & Compliance`: 7 skills [code_file:22]
- `⚙️ Linguagens & Ferramentas`: 13 skills [code_file:22]
- `⚛️ Frontend & Web`: 30 skills [code_file:22]
- `🎨 Design & UI/UX`: 29 skills [code_file:22]
- `🎮 Games`: 4 skills [code_file:22]
- `🎵 Mídia & Criação`: 14 skills [code_file:22]
- `📊 Dados, ML & Analytics`: 11 skills [code_file:22]
- `📝 Conteúdo & Escrita`: 15 skills [code_file:22]
- `📱 Mobile`: 8 skills [code_file:22]
- `🔒 Segurança & Compliance`: 10 skills [code_file:22]
- `🔗 Automação & Integrações`: 23 skills [code_file:22]
- `🔧 Backend & APIs`: 29 skills [code_file:22]
- `🗄️ Banco de Dados`: 13 skills [code_file:22]
- `🚀 Produto & Marketing`: 11 skills [code_file:22]
- `🛠️ Dev Tools & Misc`: 26 skills [code_file:22]
- `🧠 LLM & Prompts`: 5 skills [code_file:22]
- `🧪 Testes & QA`: 13 skills [code_file:22]

## Exemplo de uso por uma IA

```text
Entrada: "usar a skill react-best-practices"
1. Abrir skills-routes.json
2. Procurar skill == "react-best-practices"
3. Ler repositoryUrl para navegação e rawCandidates para consumo
4. Baixar o primeiro candidato válido
5. Injetar o conteúdo da skill no contexto do agente
```

## Cobertura atual

A biblioteca atual contém 22 categorias e 361 skills mapeadas a partir do `skills.json` fornecido neste projeto [file:4][code_file:22].
