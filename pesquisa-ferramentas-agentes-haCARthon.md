# Pesquisa tecnica: skills, plugins e ferramentas para Codex/Claude Code no haCARthon

Data da pesquisa: 2026-06-05

## Resumo executivo

Para o haCARthon, a melhor estrategia nao e instalar muitas coisas. O ganho real vem de um stack pequeno, medido e bem escolhido:

1. **Codex como agente principal** para implementar, testar, resumir documentos e iterar no MVP.
2. **Skills de frontend/design** para manter qualidade visual e usabilidade, porque o desafio valoriza clareza para usuario comum.
3. **Context7 ou docs oficiais** para buscar documentacao atualizada de bibliotecas, sem colar documentacao inteira na conversa.
4. **Graphify ou Serena** quando o projeto crescer, para evitar releituras longas do codigo.
5. **RTK e ccusage** se formos usar Claude Code/Codex CLI com muitos comandos de terminal.
6. **Poucos MCPs ativos**. MCP demais vira imposto de contexto: schemas de ferramentas entram no prompt e podem consumir muito antes do trabalho comecar.

Minha recomendacao pratica: **nao montar um "mega setup" agora**. Para um hackathon curto, um stack enxuto ganha de um setup cheio de ferramentas que ainda vamos ter que aprender, configurar e depurar.

## Stack recomendado para o nosso caso

### Nivel 1 - Adotar agora

| Ferramenta | Categoria | Por que usar | Requisitos | Risco |
|---|---|---|---|---|
| Codex atual | Agente principal | Ja tem acesso ao workspace, consegue editar, testar, ler PDFs e controlar browser local quando necessario | Codex Desktop/CLI configurado | Baixo |
| AGENTS.md enxuto | Contexto persistente | Guarda regras do projeto sem repetir tudo a cada prompt | Criar arquivo curto no repo | Baixo |
| Frontend/design skill ou regras de UI | Qualidade do MVP | Ajuda a construir uma interface clara para produtor/analista | Skill instalada ou instrucoes locais | Baixo |
| Browser/Playwright para verificacao | QA visual | Garante que o prototipo realmente abre e funciona | Dev server local | Baixo |
| Context7 CLI/MCP | Docs atualizadas | Evita usar exemplos velhos de biblioteca | Node/npx ou MCP configurado | Medio |

### Nivel 2 - Adotar quando o codigo crescer

| Ferramenta | Categoria | Por que usar | Requisitos | Risco |
|---|---|---|---|---|
| Graphify | Conhecimento de repo/docs | Cria grafo consultavel de codigo, docs, PDFs e diagramas | Python, `pip install graphifyy`, tempo de indexacao | Medio |
| Serena | Busca semantica/LSP | Navega por simbolos sem ler arquivos inteiros | MCP, LSP, projeto em linguagem suportada | Medio |
| ccusage | Observabilidade de tokens | Mede uso real antes de otimizar | Logs locais do agente/CLI | Baixo |
| RTK | Economia de saida de terminal | Compacta saidas de comandos como git/test/build | Instalar binario; melhor em WSL/Linux | Medio |
| Caveman/caveman-compress | Economia textual | Reduz verbosidade e comprime memorias/instrucoes | Skill instalada | Baixo |

### Nivel 3 - Usar com cautela

| Ferramenta | Categoria | Quando vale | Cuidado |
|---|---|---|---|
| SuperClaude Framework | Mega framework Claude Code | Projetos longos, equipe madura, uso diario de Claude Code | Pode adicionar muita superficie, comandos e comportamento implicito |
| Awesome Claude Code Toolkit | Catalogo/kit grande | Fonte de pesquisa e ideias | Nao instalar tudo; escolher pecas |
| Figma MCP | Design-to-code/contexto visual | Se tivermos design Figma real | Alto custo de contexto; melhor como referencia do que "designer automatico" |
| Playwright MCP | Browser automation | E2E, debugging visual, apps web | Pode ser pesado em tokens; prefira snapshots/CLI quando possivel |
| Firecrawl MCP | Pesquisa web/scraping | Pesquisa com paginas dinamicas | Requer API key; risco de trazer contexto demais |

## Classificacao detalhada

## 1. Base oficial: Codex e Claude Code

### Codex

**O que e:** agente de codigo local/desktop/CLI. A documentacao da OpenAI descreve o Codex CLI como agente que roda localmente, le, altera e executa codigo no diretorio selecionado. O Codex tambem suporta MCP, subagentes, revisao de codigo, web search e aprovacoes.

**Pontos fortes**

- Ja estamos usando no workspace.
- Bom para editar arquivos, ler documentos locais, criar artefatos e verificar app.
- Suporta plugins/skills/MCP no ecossistema Codex.
- Tem vantagem para nosso caso porque ja lidou bem com os PDFs do edital, guia, cronograma e briefing.

**Pontos fracos**

- Ecossistema de skills ainda e mais novo que o de Claude Code.
- Algumas skills feitas para Claude Code usam ferramentas especificas e podem falhar ou virar no-op no Codex.
- No Windows, algumas ferramentas de economia baseadas em hooks Unix perdem automacao.

**Requisitos**

- Codex Desktop/CLI configurado.
- Workspace com permissao de escrita.
- Para CLI: instalacao conforme docs da OpenAI.

**Uso recomendado no haCARthon**

Usar Codex como agente principal. Criar um `AGENTS.md` curto com: objetivo do MVP, desafio escolhido, regras de UI, comandos de build/test, e criterio de "nao expandir escopo".

Fontes: [OpenAI Codex CLI](https://developers.openai.com/codex/cli), [OpenAI Codex plugins e skills](https://openai.com/academy/codex-plugins-and-skills/), [openai/codex no GitHub](https://github.com/openai/codex).

### Claude Code

**O que e:** agente de codigo com ecossistema maduro de skills, subagentes, hooks, MCP e worktrees.

**Pontos fortes**

- Skills oficiais e de comunidade mais maduras.
- Subagentes com contexto proprio e modelos diferentes.
- Hooks deterministas para formatacao, lint, 'seguranca e notificacoes.
- Worktrees para paralelizar tarefas sem conflito de arquivos.

**Pontos fracos**

- Pode ficar caro/ruidoso se muitas skills/MCPs ficarem ativos.
- Hooks e MCPs podem introduzir risco de seguranca se instalados sem auditoria.
- Mais configuracao inicial.

**Requisitos**

- Claude Code instalado.
- `.claude/skills`, hooks e MCP configurados por projeto ou usuario.
- Idealmente Git e worktrees.

**Uso recomendado no haCARthon**

Se usarmos Claude Code junto com Codex, usar para tarefas paralelas bem delimitadas: revisao, pesquisa, prototipo alternativo ou refino de UI. Nao misturar dois agentes editando os mesmos arquivos.

Fontes: [Claude Code Skills](https://code.claude.com/docs/en/skills), [Claude Code Subagents](https://code.claude.com/docs/en/sub-agents), [Claude Code Hooks](https://code.claude.com/docs/en/hooks), [Claude Code Worktrees](https://code.claude.com/docs/en/worktrees).

## 2. Economia de tokens e contexto

### RTK - Rust Token Killer

**O que e:** proxy/CLI que reescreve comandos comuns para versoes compactas antes de a saida entrar no contexto do agente.

**Pontos fortes**

- Muito bom para loops de terminal: `git status`, testes, builds, logs.
- O projeto declara suporte a Claude Code, Codex, Cursor, Gemini CLI, OpenCode e outros.
- Tem comando de analytics (`rtk gain`) para medir economia.

**Pontos fracos**

- As economias grandes sao sobre saida de comandos, nao sobre todo o custo da sessao.
- Em Windows nativo, auto-rewrite por hook nao funciona igual; o proprio projeto recomenda WSL para suporte completo.
- Ferramentas internas como Read/Grep/Glob do Claude Code nao passam pelo hook.

**Requisitos**

- Instalar RTK.
- Para melhor resultado: WSL/Linux/macOS.
- No Codex, configuracao por `AGENTS.md`/instrucoes, nao necessariamente hook automatico.

**Veredito**

Vale muito se formos rodar muitos testes/builds e logs. Para o nosso projeto, instalar so depois que houver app e comandos repetitivos.

Fonte: [rtk-ai/rtk](https://github.com/rtk-ai/rtk).

### Caveman

**O que e:** skill de compressao de linguagem. Remove enchimento, artigos e frases longas para reduzir output tokens. Inclui variantes como caveman, caveman-compress, caveman-review, caveman-commit e caveman-stats.

**Pontos fortes**

- Facil de usar.
- Bom para reduzir ruido em respostas, revisoes e commits.
- `caveman-compress` pode reduzir arquivos de memoria/instrucoes longos.

**Pontos fracos**

- Economia total tende a ser menor que a propaganda quando o gargalo esta em input/cache/tool schemas.
- Pode reduzir clareza em decisoes de produto, seguranca ou documentos que precisam ser lidos por humanos.

**Requisitos**

- Skill instalada.
- Disciplina para nao usar em textos onde clareza/importancia juridica pesa mais que economia.

**Veredito**

Usar como modo opcional para trabalho operacional. Nao usar para briefing, pitch final ou documento de regras.

Fontes: [getcaveman.dev](https://www.getcaveman.dev/), [analise AI//COST sobre Caveman](https://aicost.tools/blog/caveman-mode-claude-code-cost/), [skills.sh ranking Caveman](https://www.skills.sh/).

### ccusage

**O que e:** CLI local para ver tokens e custo estimado de varios agentes, incluindo Claude Code e Codex.

**Pontos fortes**

- Mede antes de otimizar.
- Le dados locais e mostra relatorios por dia/sessao.
- Ajuda a separar custo real de percepcao.

**Pontos fracos**

- Pode divergir de limites internos de provedores.
- Nao reduz tokens; so observa.

**Requisitos**

- Logs locais do agente.
- Node/npx conforme instalacao.

**Veredito**

Primeira ferramenta a instalar se estivermos preocupados com tokens em Claude Code/Codex CLI. Sem medicao, otimizar vira achismo.

Fonte: [ccusage](https://ccusage.com/).

### Regra de ouro para tokens

Economia real vem desta ordem:

1. Reduzir contexto sempre carregado (`AGENTS.md`, `CLAUDE.md`, skills globais, MCPs globais).
2. Medir com `ccusage` ou equivalente.
3. Compactar saida de terminal com RTK.
4. Usar busca/indexacao em vez de reler arquivos grandes.
5. Usar Caveman para reduzir output quando fizer sentido.

Discussao recorrente em comunidades: instalar dezenas de skills parece barato, mas cada nome/descricao pode entrar no contexto e competir por ativacao. Melhor instalar poucas skills por projeto do que copiar packs enormes globalmente.

Fontes: [discussao Reddit sobre superficie de skills](https://www.reddit.com/r/AIAgentsInAction/comments/1tcu6kq/i_built_a_free_claude_code_toolkit_58_skills_8/), [MCP client best practices](https://modelcontextprotocol.io/docs/develop/clients/client-best-practices).

## 3. Conhecimento de repo, docs e pesquisa

### Graphify

**O que e:** skill/ferramenta que transforma codigo, documentos, PDFs, imagens e diagramas em grafo de conhecimento. Gera HTML interativo, JSON e `GRAPH_REPORT.md`.

**Pontos fortes**

- Excelente para projetos com muitos arquivos e documentos.
- Ajuda o agente a consultar relacoes sem reler tudo.
- Bom para preservar contexto entre sessoes.
- Funciona com Claude Code, Codex, OpenCode e outros.

**Pontos fracos**

- Tem custo inicial de indexacao.
- Pode ser exagero para um MVP pequeno no primeiro dia.
- Semantic extraction pode custar tokens dependendo do modo.

**Requisitos**

- Python.
- `pip install graphifyy`.
- Rodar `/graphify` ou CLI no repositorio.

**Uso recomendado no haCARthon**

Quando tivermos briefing + codigo + decisoes de arquitetura, rodar Graphify para gerar um mapa persistente. Antes disso, manter anotacoes simples.

Fonte: [Graphify](https://graphify.net/tw/).

### Serena

**O que e:** MCP/plugin com capacidades de IDE: busca semantica, edicao e navegacao por simbolos via LSP.

**Pontos fortes**

- Evita ler arquivos inteiros.
- Trabalha no nivel de simbolos.
- Suporta muitas linguagens.

**Pontos fracos**

- Mais util em codebases maiores.
- Depende de LSP/MCP bem configurado.
- Adiciona ferramentas ao contexto.

**Requisitos**

- MCP configurado.
- Projeto em linguagem suportada.

**Uso recomendado**

Adotar se o projeto passar de MVP pequeno para app com varias camadas.

Fonte: [Serena plugin](https://claude.com/plugins/serena).

### Context7

**O que e:** ferramenta/MCP/CLI para buscar documentacao atualizada de bibliotecas.

**Pontos fortes**

- Evita exemplos desatualizados.
- Pode ser usado como MCP ou CLI + skill.
- Bom para React, Vite, Tailwind, shadcn, mapas e APIs.

**Pontos fracos**

- Mais um MCP se deixado sempre ativo.
- Melhor chamar sob demanda.

**Requisitos**

- `ctx7` CLI ou MCP.
- Node/npx conforme instalacao.

**Uso recomendado**

Usar sob demanda quando formos escolher libs: mapa, UI, forms, validacao, PDF, deploy.

Fonte: [Context7 CLI](https://context7.com/docs/clients/cli).

### Firecrawl MCP

**O que e:** MCP oficial para busca, scraping e crawling com conteudo limpo para agentes.

**Pontos fortes**

- Bom para pesquisa web e paginas dinamicas.
- Retorna contexto mais limpo do que HTML cru.

**Pontos fracos**

- Requer API key.
- Pode trazer contexto demais se usado sem escopo.
- Para nosso caso, web search normal e leitura manual podem bastar.

**Requisitos**

- Conta/API key Firecrawl.
- MCP configurado.

**Uso recomendado**

Usar so se precisarmos coletar muitas fontes externas do CAR, leis, manuais e dados.

Fonte: [Firecrawl MCP Server](https://github.com/firecrawl/firecrawl-mcp-server).

## 4. Frontend, design e verificacao visual

### frontend-design / web-design-guidelines / design-taste-frontend

**O que sao:** skills focadas em qualidade visual, UX, composicao, acessibilidade e evitar interfaces genericas.

**Pontos fortes**

- Muito alinhadas com nosso desafio, porque a solucao precisa ser clara para produtor rural e analista.
- Reduz risco de MVP tecnicamente correto, mas ruim de usar.
- `frontend-design` aparece entre as skills mais instaladas no skills.sh; Vercel e comunidade tambem tem skills fortes para React e web design.

**Pontos fracos**

- Podem induzir polimento estetico demais se o escopo nao estiver claro.
- Regras de design precisam respeitar o usuario: produtor rural, baixa alfabetizacao digital, celular, linguagem simples.

**Requisitos**

- Instalar skill ou criar skill local equivalente.
- Definir design tokens simples e componentes.

**Uso recomendado**

Usar desde o primeiro prototipo. Para haCARthon, UX clara vale mais que animacao.

Fontes: [skills.sh leaderboard](https://www.skills.sh/), [Claude Code Skills](https://code.claude.com/docs/en/skills).

### Figma MCP

**O que e:** MCP oficial da Figma para dar contexto de Figma Design/FigJam/Figma Make a agentes como Claude Code e Codex.

**Pontos fortes**

- Excelente se ja houver design system real no Figma.
- Pode dar acesso a componentes, tokens e layouts.
- Suporta Codex e Claude Code.

**Pontos fracos**

- Comunidade relata consumo alto de creditos/tokens.
- Melhor usar como contexto, nao como designer autonomo.
- Requer cuidado com permissao de leitura/escrita.

**Requisitos**

- Conta Figma.
- Acesso ao arquivo.
- MCP configurado.

**Uso recomendado**

Nao e prioridade agora. Criar prototipo direto no codigo e, se necessario, usar Figma depois para refino visual.

Fontes: [Figma MCP Catalog](https://www.figma.com/mcp-catalog/), [discussao Reddit sobre Figma MCP e custo](https://www.reddit.com/r/FigmaDesign/comments/1td9hpm/claude_code_figma_mcp/).

### Playwright MCP / Browser tools / agent-browser

**O que sao:** ferramentas para navegador automatizado, testes visuais e verificacao de fluxo.

**Pontos fortes**

- Permitem ver se o app realmente funciona.
- Playwright MCP e oficial/Microsoft.
- `agent-browser` e alternativas CLI prometem menos overhead usando snapshots/refs.

**Pontos fracos**

- Playwright MCP pode consumir muito contexto se despejar snapshots grandes.
- Browser automation pode virar um buraco de tokens se o agente clicar sem plano.

**Requisitos**

- Node/npx.
- App local rodando.
- MCP ou CLI configurado.

**Uso recomendado**

Para o haCARthon, verificar fluxos essenciais: abrir app, escolher perfil, responder perguntas, gerar orientacao/checklist, baixar/copiar resultado. Usar browser de forma objetiva.

Fontes: [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp), [Playwright MCP docs](https://playwright.dev/docs/getting-started-mcp), [Reddit sobre agent-browser](https://www.reddit.com/r/ClaudeAI/comments/1qazrbr/agentbrowser_vercels_new_cli_that_works_with/).

## 5. Subagentes, worktrees e orquestracao

### Subagentes nativos

**O que sao:** agentes especializados com contexto proprio, ferramentas permitidas e, em Claude Code, ate modelo separado.

**Pontos fortes**

- Economizam contexto principal.
- Bons para pesquisa, revisao, testes e tarefas paralelas.
- Podem ser isolados por worktree para evitar conflito.

**Pontos fracos**

- Delegar mal duplica trabalho.
- Subagentes precisam de escopo estreito.
- Podem gerar conflitos se editarem os mesmos arquivos.

**Requisitos**

- Claude Code ou Codex com suporte a subagentes.
- Regras de ownership por arquivo/modulo.

**Uso recomendado**

No nosso projeto: usar subagente para "revisar UX do fluxo" ou "pesquisar regra CAR especifica", nao para construir tudo em paralelo no inicio.

Fontes: [Claude Code Agents](https://code.claude.com/docs/en/agents), [Claude Code Subagents](https://code.claude.com/docs/en/sub-agents), [OpenAI Codex CLI](https://developers.openai.com/codex/cli).

### Worktrees

**O que sao:** checkouts isolados por tarefa/branch.

**Pontos fortes**

- Evitam que agentes editem a mesma arvore.
- Facilitam comparar solucoes.
- Uteis para testar duas abordagens de UI ou arquitetura.

**Pontos fracos**

- Overhead de git, env e merge.
- Para MVP pequeno, pode ser desnecessario.

**Requisitos**

- Git.
- Build que rode em worktree.
- Arquivos locais necessarios copiados por `.worktreeinclude`.

**Uso recomendado**

Usar depois que tivermos base funcionando. Exemplo: branch A com fluxo pergunta-resposta; branch B com checklist + modo analista.

Fonte: [Claude Code Worktrees](https://code.claude.com/docs/en/worktrees).

### Claude Squad

**O que e:** TUI para gerenciar varios agentes locais como Claude Code, Codex, OpenCode e Amp em workspaces separados.

**Pontos fortes**

- Bom para power users.
- Ajuda a controlar multiplas sessoes.

**Pontos fracos**

- Overkill para comeco do hackathon.
- Exige disciplina de merge e revisao.

**Requisitos**

- Git, terminal, agentes instalados.
- API keys/perfis conforme agente.

**Uso recomendado**

Nao agora. Avaliar se estivermos rodando varias sessoes simultaneas.

Fonte: [smtg-ai/claude-squad](https://github.com/smtg-ai/claude-squad).

## 6. Frameworks e catalogos grandes

### skills.sh

**O que e:** diretorio/leaderboard de skills para agentes.

**Pontos fortes**

- Ajuda a encontrar skills populares.
- Mostra installs e fontes.
- Tem skills relevantes: `frontend-design`, `vercel-react-best-practices`, `web-design-guidelines`, `caveman`, `tdd`, `verification-before-completion`, `shadcn`, `extract-design-system`.

**Pontos fracos**

- Popularidade nao garante qualidade.
- Instalar muitas skills aumenta superficie de ativacao e contexto.

**Requisitos**

- `npx skills` para instalar via CLI, ou instalacao manual conforme skill.

**Uso recomendado**

Usar como catalogo, nao como "instalar tudo".

Fonte: [skills.sh](https://www.skills.sh/).

### SuperClaude Framework

**O que e:** framework de configuracao que adiciona comandos, agentes, modos e MCPs ao Claude Code.

**Pontos fortes**

- Organiza fluxos completos.
- Tem agentes especializados e comandos para ciclo de desenvolvimento.

**Pontos fracos**

- E grande.
- Pode atrapalhar se nao soubermos exatamente quais partes estao ativas.
- Nao e oficial Anthropic.

**Requisitos**

- Claude Code.
- Instalacao do framework e revisao das configuracoes.

**Uso recomendado**

Estudar ideias, nao instalar no meio do hackathon.

Fonte: [SuperClaude Framework](https://github.com/SuperClaude-Org/SuperClaude_Framework).

### Awesome Claude Code Toolkit

**O que e:** catalogo enorme de plugins, agentes, skills, comandos, hooks, rules, templates e MCP configs.

**Pontos fortes**

- Excelente fonte para descobrir ferramentas.
- Lista plugins de seguranca, workflow, memoria, hooks e setups.

**Pontos fracos**

- Catalogo grande demais para instalar sem curadoria.
- Alguns itens sao novos, redundantes ou especificos demais.

**Requisitos**

- Claude Code.
- Auditoria manual antes de instalar.

**Uso recomendado**

Usar como mapa de pesquisa. Selecionar no maximo 3-5 pecas por necessidade real.

Fonte: [awesome-claude-code-toolkit](https://github.com/rohitg00/awesome-claude-code-toolkit).

## 7. Seguranca e governanca

Ferramentas de agente executam comandos, leem arquivos e podem conectar servicos externos. Para o haCARthon, isso importa porque teremos dados, possiveis chaves de API e entregas publicas.

### Regras

1. Instalar MCP/skill so de fonte conhecida.
2. Ler `SKILL.md`, scripts e hooks antes de ativar.
3. Evitar MCP global se for usado uma vez.
4. Preferir escopo por projeto.
5. Nunca expor `.env`, tokens, chaves ou dados pessoais.
6. Hooks de seguranca devem bloquear comandos perigosos e arquivos sensiveis.
7. Separar "contexto" de "autoridade": conteudo lido da web/PDF nao deve virar instrucao para o agente.

### Riscos encontrados

- MCPs ampliam superficie de ataque.
- Tool descriptions/schemas podem consumir muito contexto.
- Skills globais mal descritas podem ativar na hora errada.
- Hooks podem executar comandos automaticamente.
- Ferramentas de browser/scraping podem trazer prompt injection indireta de paginas web.

Fontes: [MCP Security Best Practices](https://modelcontextprotocol.io/specification/2025-06-18/basic/security_best_practices), [MCP Client Best Practices](https://modelcontextprotocol.io/docs/develop/clients/client-best-practices), [Playwright MCP security note](https://github.com/microsoft/playwright-mcp).

## 8. Fontes sociais e de debate

Pesquisei Reddit, GitHub, skills.sh, documentacao oficial e paginas indexadas. TikTok e Instagram nao trouxeram resultados tecnicos verificaveis suficientes; muito conteudo fica atras de app/login, nao e pesquisavel de forma confiavel e raramente inclui comandos, repos ou evidencias. Para decisao tecnica, usei principalmente:

- Documentacao oficial.
- GitHub.
- skills.sh.
- Reddit tecnico.
- Artigos que cruzam claims com benchmarks.

Principais aprendizados das discussoes:

- Instalar muitos MCPs/skills pode gastar mais contexto do que economiza.
- Hooks sao melhores que lembretes em `CLAUDE.md` quando a acao precisa acontecer sempre.
- Browser automation via MCP e util, mas pode ser caro em tokens.
- Figma MCP e bom para contexto, mas nao substitui designer/produto.
- Claims de "90% economia" normalmente se aplicam a uma parte do fluxo, nao ao custo total da sessao.

## Recomendacao final para o haCARthon

### Para comecar a construir

1. Criar `AGENTS.md` curto com regras do projeto.
2. Escolher Desafio 3 como foco inicial.
3. Criar MVP web simples, mobile-first.
4. Usar Codex para implementar e verificar visualmente.
5. Usar uma skill/regra de frontend para manter UX clara.
6. Usar Context7 sob demanda para bibliotecas.
7. Evitar MCPs desnecessarios.

### Quando o MVP estiver rodando

1. Adicionar verificacao visual automatizada.
2. Medir tokens se estivermos em CLI com `ccusage`.
3. Se houver muitos comandos repetitivos, testar RTK.
4. Se o codigo/documentos crescerem, rodar Graphify ou Serena.
5. Usar subagentes so para revisao e tarefas isoladas.

### Stack enxuto sugerido

| Momento | Ferramentas |
|---|---|
| Agora | Codex, AGENTS.md, frontend/design guidance, browser verification |
| Primeiro prototipo | Context7 sob demanda, shadcn/Tailwind se escolhermos React |
| Depois de 1 app funcional | ccusage, RTK se houver CLI repetitiva |
| Projeto maior | Graphify ou Serena |
| Trabalho paralelo | Subagentes/worktrees |

## Lista priorizada

1. **AGENTS.md enxuto** - maior custo-beneficio.
2. **Frontend/design skill** - essencial para desafio com usuario nao tecnico.
3. **Context7** - docs atuais sem colar documentacao enorme.
4. **Browser verification** - garantir prototipo funcionando.
5. **ccusage** - medir gasto real.
6. **RTK** - economizar saidas de terminal quando houver testes/builds.
7. **Graphify** - preservar conhecimento quando o repo crescer.
8. **Serena** - navegacao por simbolos em codebase maior.
9. **Caveman** - reduzir ruido de comunicacao, com economia moderada.
10. **Figma MCP** - so se houver design Figma real.

## Apendice: links principais

- OpenAI Codex CLI: https://developers.openai.com/codex/cli
- OpenAI Codex plugins e skills: https://openai.com/academy/codex-plugins-and-skills/
- openai/codex: https://github.com/openai/codex
- Claude Code Skills: https://code.claude.com/docs/en/skills
- Claude Code Subagents: https://code.claude.com/docs/en/sub-agents
- Claude Code Hooks: https://code.claude.com/docs/en/hooks
- Claude Code Worktrees: https://code.claude.com/docs/en/worktrees
- skills.sh: https://www.skills.sh/
- RTK: https://github.com/rtk-ai/rtk
- Caveman: https://www.getcaveman.dev/
- ccusage: https://ccusage.com/
- Graphify: https://graphify.net/tw/
- Serena: https://claude.com/plugins/serena
- Context7 CLI: https://context7.com/docs/clients/cli
- Firecrawl MCP: https://github.com/firecrawl/firecrawl-mcp-server
- Figma MCP catalog: https://www.figma.com/mcp-catalog/
- Playwright MCP: https://github.com/microsoft/playwright-mcp
- SuperClaude Framework: https://github.com/SuperClaude-Org/SuperClaude_Framework
- Awesome Claude Code Toolkit: https://github.com/rohitg00/awesome-claude-code-toolkit
- Claude Squad: https://github.com/smtg-ai/claude-squad
- MCP security best practices: https://modelcontextprotocol.io/specification/2025-06-18/basic/security_best_practices
- MCP client best practices: https://modelcontextprotocol.io/docs/develop/clients/client-best-practices
