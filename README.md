<div align="center">

<img src="assets/hero.svg" alt="Yannick Aaron Lehr — Co-Founder of EMPA Spain, building KIVO" width="100%">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-yannickaaron-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/yannickaaron/)
[![KIVO](https://img.shields.io/badge/KIVO-kivo.eco-C6E355?style=for-the-badge&labelColor=20242E)](https://kivo.eco)
[![EMPA](https://img.shields.io/badge/EMPA-empa.co-4B5165?style=for-the-badge&labelColor=20242E)](https://empa.co)
![Valencia](https://img.shields.io/badge/Valencia-🇪🇸-C9CBD1?style=for-the-badge&labelColor=20242E)

![Profile views](https://komarev.com/ghpvc/?username=YannickAaron&style=flat-square&color=C6E355&label=profile+views)
&nbsp;![Followers](https://img.shields.io/github/followers/YannickAaron?style=flat-square&color=C6E355&labelColor=20242E)

</div>

Data scientist turned full-stack builder. I design data platforms, ship the software that runs on
them, and use AI where it actually pays off — not where it merely demos well.

---

## 🚀 Currently building: KIVO

> **One platform that runs your entire company — and removes the administration that runs you.**

KIVO replaces the tool-zoo with a ready-to-use company platform: CRM, projects, contracts, time,
billing, HR, absences, expenses, documents, equipment and financial planning — all of it **one
business software**, working as one system from day one. No implementation project, no integrator's
phone number: the processes ship already thought through and legally exact.

The mechanism, drawn — **one hour is logged once, and everything downstream derives from it:**

```mermaid
flowchart LR
  LOG(["1 hour logged<br/>once, in KIVO"]) --> HOUR{{"the hour<br/>who · project · contract<br/>billable?"}}
  CON[/"contract<br/>rate · budget · rule"/] -.-> HOUR
  EMP[/"person<br/>cost rate · capacity"/] -.-> HOUR

  HOUR --> SIGN["client sign-off<br/>sealed timesheet"]
  HOUR --> BILL["billable value"]
  HOUR --> COST["internal cost"]
  HOUR --> CAP["capacity plan"]

  SIGN --> INV["invoice<br/>signed + unbilled only"]
  BILL --> INV
  BILL --> MAR["project margin"]
  COST --> MAR
  INV --> CASH["cash-flow forecast"]
  CAP --> CASH

  classDef born fill:#C6E355,stroke:#4B5165,stroke-width:2px,color:#20242E
  classDef core fill:#4B5165,stroke:#4B5165,color:#FFFFFF
  classDef money fill:#0F766E,stroke:#0F766E,color:#FFFFFF
  classDef plan fill:#0EA5E9,stroke:#0EA5E9,color:#04283A
  class LOG,HOUR born
  class CON,EMP core
  class SIGN,BILL,COST,INV,MAR money
  class CAP,CASH plan
```

Nobody re-types anything, so the data is **AI-ready by construction** — no cleaning project before
the first model. And it runs on **solely European infrastructure**: Scaleway for hosting and storage,
Mistral for AI, a dedicated encryption key per customer company. Your data stays yours.

**The stack, in full — there is no US cloud in it:**

```mermaid
flowchart TB
  U["Customer<br/>browser · desktop"]
  subgraph EU["🇪🇺 European infrastructure only"]
    direction TB
    APP["KIVO app<br/>Next.js · tRPC · Docker"]
    subgraph SCW["Scaleway · fr-par"]
      direction TB
      DB[("PostgreSQL<br/>one data model")]
      OBJ[("Object storage")]
    end
    KMS["KMS · one key<br/>per company"]
    LLM["Mistral · EU models"]
  end
  US["AWS · Azure · GCP<br/>US LLM APIs"]

  U --> APP
  APP --> DB
  APP --> OBJ
  APP --> LLM
  KMS -.-> DB
  KMS -.-> OBJ
  EU ~~~ US

  classDef svc fill:#0F766E,stroke:#0F766E,color:#FFFFFF
  classDef store fill:#4B5165,stroke:#4B5165,color:#FFFFFF
  classDef key fill:#C6E355,stroke:#4B5165,stroke-width:2px,color:#20242E
  classDef client fill:none,stroke:#0EA5E9,stroke-width:1.5px
  classDef gone fill:none,stroke:#94A3B8,stroke-width:1.5px,stroke-dasharray:5 5,color:#94A3B8
  class APP,LLM svc
  class DB,OBJ store
  class KMS key
  class U client
  class US gone
  style EU fill:none,stroke:#0EA5E9,stroke-width:2px
  style SCW fill:none,stroke:#4B5165,stroke-width:1.5px
```

Row-level isolation with a `tenant_id` on every row, tenant-scoped storage prefixes, the customer's
own KMS key encrypting data at rest, and prompts that never leave the EU.

Built inside our own consultancy for three years, scaled that company on it, now running for
external customers. 🇩🇪 🇪🇸

---

## 🧭 What I actually do

```
Data Strategy  ──►  Governance, data models, AI readiness for large organisations
Engineering    ──►  TypeScript / Next.js / tRPC / Prisma / Postgres — from schema to shipped UI
AI             ──►  LLM pipelines with eval harnesses, agents, document intelligence
Analytics      ──►  Spatio-temporal forecasting, geodata, ML in production (PyTorch, Airflow)
Business       ──►  Co-founder, P&L, hiring, and the unglamorous operations in between
```

```mermaid
%%{init: {"themeVariables": {"cScale0": "#4B5165", "cScaleLabel0": "#FFFFFF", "cScale1": "#0F766E", "cScaleLabel1": "#FFFFFF", "cScale2": "#0EA5E9", "cScaleLabel2": "#04283A", "cScale3": "#4B5165", "cScaleLabel3": "#FFFFFF", "cScale4": "#C6E355", "cScaleLabel4": "#20242E"}}}%%
timeline
    title Data → software → one platform
    2018-2022 · Freelance : IT consultant and developer
        : TypeScript, Python, SQL for client systems
    ioki · a Deutsche Bahn company : Data Scientist
        : Geodata quality automation, Airflow pipelines
        : Demand forecasting with PyTorch transformers
        : M.Sc. Frankfurt School alongside
    Workever : Co-founder
        : Learned to build a product, not a project
    EMPA Spain : Co-founder and Director Ejecutivo
        : Data and management consulting, DE and ES, ~20 people
    KIVO : One platform that runs an entire company
        : Built inside EMPA, ran the firm on it for 3 years
        : Now shipping to customers on a European stack
```

- 🏗️ **Co-Founder & Director Ejecutivo**, EMPA Spain — data & management consulting across DE/ES
- 🤖 Deep in **AI-supported business intelligence** and software automation — including the fun parts of the EU AI Act
- 🎓 **M.Sc. Management (Data & Business Analytics)**, Frankfurt School — thesis: geospatial time-series forecasting with transformers *(with ioki / Deutsche Bahn)*
- 🖨️ Off-keyboard: 3D printing with **Klipper**, and pretending Valencia's weather is a productivity tool

---

## 🛠️ Toolbox

<div align="center">

**Languages**

[![Languages](https://skillicons.dev/icons?i=ts,python,rust,julia,postgres,bash&theme=dark)](https://skillicons.dev)

**Web & app**

[![Web](https://skillicons.dev/icons?i=nextjs,react,tailwind,prisma,nodejs,tauri&theme=dark)](https://skillicons.dev)

**Data, AI & infra**

[![Data](https://skillicons.dev/icons?i=pytorch,docker,githubactions,azure,linux,vscode&theme=dark)](https://skillicons.dev)

`tRPC` · `LangChain` · `Airflow` · `Mistral` · `Scaleway` · `MongoDB` · `Klipper`

</div>

---

## 📌 A few public repos

| Repo | What it is |
|---|---|
| [`lexware-client-ts`](https://github.com/YannickAaron/lexware-client-ts) | Modern, type-safe TypeScript client for the Lexware API |
| [`BetterMSFile`](https://github.com/YannickAaron/BetterMSFile) | A saner explorer app for OneDrive & SharePoint |
| [`quick-docu-mcp`](https://github.com/YannickAaron/quick-docu-mcp) | MCP server for quick documentation capture |
| [`scw-easy-container-redeploy`](https://github.com/YannickAaron/scw-easy-container-redeploy) | GitHub Action to redeploy a Scaleway container by name |
| [`TimeSeriesForecasting`](https://github.com/YannickAaron/TimeSeriesForecasting) | Spatio-temporal forecasting experiments |

> 🔒 Most of my day-to-day work (KIVO included) lives in private repos — the stats below are the honest version.

---

## 📊 Stats

<div align="center">

<img width="49%" src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=YannickAaron&theme=transparent" alt="GitHub stats">
<img width="49%" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=YannickAaron&theme=transparent" alt="Repos per language">

<img width="62%" src="https://streak-stats.demolab.com?user=YannickAaron&hide_border=true&background=00000000&ring=C6E355&fire=C6E355&currStreakLabel=C6E355&sideLabels=8B949E&dates=8B949E&currStreakNum=8B949E&sideNums=8B949E&stroke=8B949E" alt="Streak">

<img width="80%" src="https://ghchart.rshah.org/C6E355/YannickAaron" alt="Contribution heatmap">

[![CodersRank](https://cr-skills-chart-widget.azurewebsites.net/api/api?username=yannickaaron&skills=typescript,python,rust,javascript,shell)](https://profile.codersrank.io/user/yannickaaron)

</div>

### 🧊 The year, in three dimensions

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/YannickAaron/YannickAaron/output-3d/profile-kivo-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/YannickAaron/YannickAaron/output-3d/profile-kivo-light.svg">
  <img alt="3D contribution calendar" src="https://raw.githubusercontent.com/YannickAaron/YannickAaron/output-3d/profile-kivo-light.svg" width="100%">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/YannickAaron/YannickAaron/output/github-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/YannickAaron/YannickAaron/output/github-snake.svg">
  <img alt="A snake eating my contribution graph" src="https://raw.githubusercontent.com/YannickAaron/YannickAaron/output/github-snake.svg" width="100%">
</picture>

</div>

<details>
<summary>🕹️ …and an arcade cabinet, because the grid was just sitting there</summary>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/arcade/pacman-contribution-graph-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/arcade/pacman-contribution-graph.svg">
  <img alt="Pac-Man played on my contribution graph" src="assets/arcade/pacman-contribution-graph.svg">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/arcade/galaga-contribution-graph-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/arcade/galaga-contribution-graph.svg">
  <img alt="Galaga played on my contribution graph" src="assets/arcade/galaga-contribution-graph.svg">
</picture>

</details>

---

## 🤝 Let's talk

If you're wrestling with data governance, an AI project that stalled on messy data, or a company
drowning in the administration between its tools — that's my favourite kind of conversation.

<div align="center">

[![LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/yannickaaron/)
[![Website](https://img.shields.io/badge/EMPA_Consulting-4B5165?style=for-the-badge&labelColor=20242E)](https://empa.co)
[![KIVO](https://img.shields.io/badge/See_KIVO-C6E355?style=for-the-badge&labelColor=20242E)](https://kivo.eco)

🇩🇪 Deutsch · 🇬🇧 English · 🇪🇸 Español

</div>
