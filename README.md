# Marcus Couto

**🇧🇷 Português**

**Desenvolvedor full-stack** — sistemas corporativos em PHP há mais de 20 anos, hoje focado em
plataformas web com IA integrada: BI conversacional, agentes com _tool-use_ e geração de código _low-code_.

Construo o sistema inteiro: modelo de dados, backend, SPA, deploy em VPS e a documentação que mantém
tudo isso navegável. Trabalho tanto em greenfield quanto em legado — migrar sistema antigo sem parar
a operação é parte grande do que faço.

**🇬🇧 English**

**Full-stack developer** — 20+ years building enterprise systems in PHP, now focused on
AI-powered web platforms: conversational BI, tool-use agents and low-code generation.

I build the whole thing: data model, backend, SPA, VPS deployment and the documentation that keeps
it all navigable. I work on greenfield and legacy alike — migrating an old system without stopping
the business is a big part of what I do.

---

## 🛠 Stack

![PHP](https://img.shields.io/badge/PHP_8.3-777BB4?style=flat&logo=php&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel_13-FF2D20?style=flat&logo=laravel&logoColor=white)
![CodeIgniter](https://img.shields.io/badge/CodeIgniter_2%2F3_HMVC-EF4223?style=flat&logo=codeigniter&logoColor=white)
![Angular](https://img.shields.io/badge/Angular_21-DD0031?style=flat&logo=angular&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap_5-7952B3?style=flat&logo=bootstrap&logoColor=white)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=flat&logo=chartdotjs&logoColor=white)

![MySQL](https://img.shields.io/badge/MySQL_%2F_MariaDB-4479A1?style=flat&logo=mysql&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![Docker](https://img.shields.io/badge/Docker_Compose-2496ED?style=flat&logo=docker&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=flat&logo=caddy&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu_VPS-E95420?style=flat&logo=ubuntu&logoColor=white)
![Apache](https://img.shields.io/badge/Apache-D22128?style=flat&logo=apache&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=flat&logo=powershell&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)

| Camada · Layer | |
|---|---|
| **Backend** | PHP 8.3 · Laravel 13 (Sanctum, queues, scheduler, migrations, PHPUnit) · CodeIgniter 2/3 + HMVC · custom MVC framework (`_init`) |
| **Frontend** | Angular 21 (standalone components, Transloco, Vitest) · vanilla-JS SPA, no build step · Bootstrap 5 · Chart.js (treemap/matrix) · CodeMirror |
| **Data** | MySQL/MariaDB · PostgreSQL · SQLite · schema introspection · custom query builder · analytical SQL |
| **AI / LLM** | custom LLM gateway · SSE streaming · agent mode with tool-use · NL→SQL · versioned prompt engineering · token quotas & usage accounting |
| **Infra** | Docker + Compose · Caddy (automatic TLS) · Ubuntu VPS · Apache/mod_rewrite · Bash & PowerShell (deploy, backup, health) · CSP & hardening |
| **Integrations** | Microsoft Graph API (OAuth 2.0) · LDAP/Active Directory · SFTP · payment gateways · bank slips · PHPMailer · mPDF/TCPDF · PhpSpreadsheet · reCAPTCHA · OneSignal |

---

## 🚀 Projetos em destaque · Featured projects

### _init_bi
**BI conversacional multi-empresa · Multi-tenant conversational BI**

`Laravel 13` · `SPA vanilla JS` · `MySQL/PostgreSQL` · `Chart.js` · `multi-tenant` · `i18n` · `SSE`

🇧🇷 Plataforma de análise de dados com IA. Conecta-se a MySQL, PostgreSQL ou ficheiros JSON, responde
perguntas de negócio em linguagem natural (com **modo agente** e _tool-use_), executa SQL e converte
o resultado em painéis com gráficos partilháveis, alertas, agendamentos por email e webhooks.

🇬🇧 Data analysis platform with AI. Connects to MySQL, PostgreSQL or JSON files, answers business
questions in natural language (including **agent mode** with tool-use), runs SQL, and turns the
results into shareable dashboards with alerts, scheduled email reports and webhooks.

> 🇧🇷 Arquitetura em 3 camadas com fronteiras explícitas: o frontend nunca toca na base de dados,
> o backend nunca guarda credencial de provedor de IA. Assets servidos por manifesto único —
> individuais em debug, _bundles_ em produção.
>
> 🇬🇧 Three-layer architecture with explicit boundaries: the frontend never touches the database,
> the backend never holds the AI provider credential. Assets are served from a single manifest —
> individually in debug, bundled in production.

### chat
**Personas de IA e cenários multi-persona · AI personas and multi-persona scenarios**

`Angular 21` · `Laravel 13 + Sanctum` · `Docker/Caddy` · `VPS` · `SSE streaming`

🇧🇷 App de conversa com personagens de IA (personalidade, estilo de fala, convicções) e cenários onde
várias personas respondem ou se omitem — um passo de "diretor" decide o elenco de cada turno.
Planos de assinatura controlam LLMs disponíveis, perfis, personas por cena e chats ativos.

🇬🇧 Conversation app built around AI characters (personality, speech style, convictions) and scenarios
where several personas either answer or stay silent — a "director" step picks the cast each turn.
Subscription plans gate available LLMs, user profiles, personas per scene and active chats.

> 🇧🇷 Testes de **paridade de prompt**: o texto exato de cada prompt fica congelado em _fixtures_ —
> mudar um prompt exige atualizar o fixture no mesmo PR, justificando a mudança.
>
> 🇬🇧 **Prompt parity tests**: the exact text of every prompt is frozen in fixtures — changing a
> prompt requires updating its fixture in the same PR, with the reason stated.

### _init_ai
**Gateway de IA compartilhado · Shared AI gateway**

`PHP puro` · `contrato HTTP versionado` · `SSE` · `e2e tests` · `Docker`

🇧🇷 Serviço _stateless_ que é o único dono da credencial do provedor de LLM. Autentica cada projeto
cliente por token próprio, valida, faz streaming e normaliza erros. Nasceu da fusão de duas cópias
duplicadas do mesmo código em projetos diferentes.

🇬🇧 Stateless service that is the sole owner of the LLM provider credential. Authenticates each client
project with its own token, validates, streams and normalises errors. Born from merging two
duplicated copies of the same code living in different projects.

### _builder
**Plataforma low-code multi-tenant · Multi-tenant low-code platform**

`Angular 21` · `framework _init` · `code generation` · `multi-tenant`

🇧🇷 SaaS para desenhar bases de dados visualmente, montar telas estilo Figma e **gerar a aplicação
full-stack** (backend PHP + frontend Angular) automaticamente. Inclui _Theme Lab_ por projeto,
preview de telas em tempo real, biblioteca de imagens com URLs mascaradas, _soft delete_ e lixeira.

🇬🇧 SaaS for visually designing databases, composing screens Figma-style and **generating the full-stack
application** (PHP backend + Angular frontend) automatically. Includes a per-project Theme Lab,
real-time screen preview, an image library with masked URLs, soft delete and a trash can.

### _init
**Framework PHP próprio · My own PHP framework**

`PHP` · `MVC + API-first` · `JWT` · `CSRF` · `rate limiting` · `migrations` · `i18n`

🇧🇷 Framework leve, sem Composer: MVC para web e API-first para REST. Router com middleware e grupos,
query builder fluente, JWT, CSRF, rate limiting por IP, migrations, i18n, validação automática
derivada do schema da base de dados e introspecção de tabelas.

🇬🇧 Lightweight, Composer-free: MVC for web apps, API-first for REST services. Router with middleware
and groups, fluent query builder, JWT, CSRF, per-IP rate limiting, migrations, i18n, automatic
validation derived from the database schema, and table introspection.

### Intranet corporativa multi-aplicação · Multi-application corporate intranet
_projeto privado de cliente · private client project_

`CodeIgniter 2 HMVC` · `PostgreSQL + MySQL` · `LDAP` · `Microsoft Graph OAuth2`

🇧🇷 Sistema interno com várias aplicações independentes sob o mesmo document root: intranet em
CodeIgniter 2 + HMVC (controladoria, análise de crédito, gestão de frota, _orderbook_,
rentabilidade, RH), serviço de fila de emails via Microsoft Graph, importadores automáticos
de _feeds_ SFTP de parceiro externo e endpoint de relatórios.

🇬🇧 Internal system with several independent applications under a single document root: a CodeIgniter 2
+ HMVC intranet (controlling, credit analysis, fleet management, order book, profitability, HR),
an email queue service over Microsoft Graph, automated importers for an external partner's SFTP
feeds, and a reporting endpoint.

> 🇧🇷 Projeto de migração contínua de legado: o padrão de 3 camadas, documentado no próprio repo,
> permite mover páginas do sistema antigo uma a uma — sem _big bang_ e sem parar a operação.
>
> 🇬🇧 Continuous legacy migration: the three-layer pattern, documented in the repo itself, lets pages
> move off the old system one at a time — no big bang, no downtime.

### Imagens com IA · AI imaging
**Instalador ComfyUI + DirectML · ComfyUI + DirectML installer**

`PowerShell` · `ComfyUI` · `Stable Diffusion 1.5` · `DirectML`

🇧🇷 Instalador PowerShell modular que monta ComfyUI + Stable Diffusion 1.5 com DirectML no Windows,
otimizado para hardware limitado (GPU integrada de 2 GB). Sem versões fixas no código: verificação
de pré-requisitos, perfis de execução e detecção de LLM local competindo por RAM.

🇬🇧 Modular PowerShell installer that sets up ComfyUI + Stable Diffusion 1.5 with DirectML on Windows,
tuned for constrained hardware (2 GB integrated GPU). No pinned versions in the code: prerequisite
checks, execution profiles, and detection of a local LLM competing for RAM.

---

## 🧭 Como trabalho · How I work

**🇧🇷 Português**

- **Camadas com fronteiras explícitas** — cada camada tem uma lista do que pode e do que nunca pode acessar, escrita na documentação e verificável.
- **Documentação viva** — guias e mapas por camada em cada repo, para navegar sem reler o código todo. Quando o código muda, o mapa muda no mesmo PR.
- **Segredos fora do repositório** — `.env` nunca versionado, credenciais geradas na própria VPS, `.dockerignore` excluindo `**/.env` de toda imagem.
- **Legado tratado como legado** — congelo, documento o padrão de migração e movo página a página, em vez de reescrever tudo de uma vez.
- **Registo de bugs** — cada bug encontrado (meu, de _review_ ou reportado) vira entrada com severidade, localização e correção sugerida.

**🇬🇧 English**

- **Layers with explicit boundaries** — each layer carries a written list of what it may and may never access, documented and verifiable.
- **Living documentation** — per-layer guides and maps in every repo, so the code can be navigated without rereading all of it. When the code changes, the map changes in the same PR.
- **Secrets out of the repository** — `.env` never versioned, credentials generated on the VPS itself, `.dockerignore` excluding `**/.env` from every image.
- **Legacy treated as legacy** — freeze it, document the migration pattern, move page by page, rather than rewriting everything at once.
- **Bug log** — every bug found (mine, from review, or user-reported) becomes an entry with severity, location and a suggested fix.

---

## 📊 GitHub

![Stats](https://github-readme-stats.vercel.app/api?username=marcuspcouto&show_icons=true&hide_border=true&count_private=true)
![Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=marcuspcouto&layout=compact&hide_border=true&langs_count=8)

## 📫 Contato · Contact

[![Email](https://img.shields.io/badge/marcus.couto@gmail.com-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:marcus.couto@gmail.com)
[![GitHub](https://img.shields.io/badge/marcuspcouto-181717?style=flat&logo=github&logoColor=white)](https://github.com/marcuspcouto)
