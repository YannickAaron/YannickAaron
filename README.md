<div align="center">

<img src="assets/hero.svg" alt="Yannick Aaron Lehr, Cofounder of EMPA Spain, building KIVO" width="100%">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-yannickaaron-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/yannickaaron/)
[![KIVO](https://img.shields.io/badge/KIVO-kivo.eco-C6E355?style=for-the-badge&labelColor=20242E)](https://kivo.eco)
[![EMPA](https://img.shields.io/badge/EMPA-empa.co-4B5165?style=for-the-badge&labelColor=20242E)](https://empa.co)
![Valencia](https://img.shields.io/badge/Valencia-🇪🇸-C9CBD1?style=for-the-badge&labelColor=20242E)

![Profile views](https://komarev.com/ghpvc/?username=YannickAaron&style=flat-square&color=C6E355&label=profile+views)
&nbsp;![Followers](https://img.shields.io/github/followers/YannickAaron?style=flat-square&color=C6E355&labelColor=20242E)

</div>

Data scientist turned full stack builder. I design data platforms, ship the software that runs on
them, and use AI where it actually pays off, not where it merely demos well.

---

## 🚀 Currently building: KIVO

> **A European business management platform built to run companies on one connected data foundation.**

Instead of moving information between disconnected systems, data is captured where it originates and
immediately becomes part of the wider business context, enabling automated processes, better
decisions and a view of the company that is always current. Today KIVO is built for service
businesses. The vision is to grow it into the operating system through which midsized companies
across industries manage, understand and steer their entire organisation.

It is not a traditional ERP, and that word does not really fit. KIVO is a holistic system for
running the whole business rather than one more tool sitting next to all the others.

### The problem

Companies run on a pile of separate systems: lead management here, project management there,
documents and devices somewhere else, plus onboarding, HR software and employee contracts. The data
ends up scattered, and even companies that already own an ERP keep a constellation of extra systems
around it. So people spend their days carrying information from system A to system B,
cross checking it, consolidating it, preparing it for someone else. What finally comes out is
usually already out of date, and rarely the right information at the right moment.

### The solution: finished processes, not an empty shell

Unlike Odoo and friends, KIVO arrives ready to use. Think of the Apple principle: you are not only
buying software, you are getting the well designed, tested processes that come with it.

* **Operational on day one.** Import your data, start working, trust the processes.
* **No consultants, no technical setup**, and no bending KIVO around the processes you happen to have today.
* **No separate automation layer** bolted on because automation is the current buzzword. The processes for lead management, device management, HR contracts and the rest ship finished, already fed by the right data, and they always look at the business as a whole.

### Data is captured where it originates

No transfer between systems, no double entry, no two readings of the same fact. Standard cases run
by themselves and the system only speaks up when something is out of the ordinary or a decision is
genuinely needed. Report sick leave, and the notification, the follow up and the people who need to
know are all handled.

Everything downstream derives from that single capture:

```mermaid
flowchart LR
  LOG(["1 hour logged<br/>once, in KIVO"]) --> HOUR{{"the hour<br/>who · project · contract<br/>billable?"}}
  CON[/"contract<br/>rate · budget · rule"/] -.-> HOUR
  EMP[/"person<br/>cost rate · capacity"/] -.-> HOUR

  HOUR --> SIGN["client sign off<br/>sealed timesheet"]
  HOUR --> BILL["billable value"]
  HOUR --> COST["internal cost"]
  HOUR --> CAP["capacity plan"]

  SIGN --> INV["invoice<br/>signed and unbilled only"]
  BILL --> INV
  BILL --> MAR["project margin"]
  COST --> MAR
  INV --> CASH["cash flow forecast"]
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

### Decisions that already carry their context

Sick leave, vacation, projects, working hours, invoices, employee and freelancer contracts, expenses:
all of it is connected, which is what makes a day by day financial view and a genuinely usable cash
flow forecast possible. A vacation request arrives with its consequences already calculated: the
cost, the project plan for those weeks, and a warning when a project is put at risk or planned time
can no longer be billed. Whoever decides has the relevant facts in front of them, and management
sees across the whole business.

### Our approach to AI

Deterministic by default. Most business data and processes are deterministic, so we solve them that
way. No AI spam. AI is used where it genuinely earns its place: in expense management, receipts are
read and validated in the background, so the employee hears immediately that the VAT number is
missing or the invoice recipient is wrong, long before anything reaches administration.

And KIVO is the foundation the next AI actually needs: a strong API, all relevant data in one
system, and a semantic understanding of what that data means. No data lake project, no data
governance programme to launch first.

### Europe first

100% European infrastructure on Scaleway, with no American services underneath, European AI models,
encryption throughout and very high standards for data security. The mission is to help Europe
digitalise and become AI ready, not by throwing AI at broken foundations, but by building the
infrastructure and the data foundation that lets it work at all.

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
    LLM["European AI models"]
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

Row level isolation with a `tenant_id` on every row, tenant scoped storage prefixes, the customer's
own KMS key encrypting data at rest, and prompts that never leave the EU.

### Why it is not an automation project

Automation projects are fashionable and they fail for a boring reason: they automate an inefficient
process instead of fixing it. The old way of working gets digitised rather than rethought. KIVO
brings the process with it, so the administrative overhead disappears because the automation lives
inside the process rather than on top of it.

Built by a management consulting firm around real operational problems, worked on for three years,
with two customers in production. Nothing vibe coded overnight. 🇩🇪 🇪🇸

---

## 🧭 What I actually do

```
Data Strategy  ──►  Governance, data models, AI readiness for large organisations
Engineering    ──►  TypeScript / Next.js / tRPC / Prisma / Postgres, from schema to shipped UI
AI             ──►  LLM pipelines with eval harnesses, agents, document intelligence
Analytics      ──►  Spatiotemporal forecasting, geodata, ML in production (PyTorch, Airflow)
Business       ──►  Cofounder, P&L, hiring, and the unglamorous operations in between
```

```mermaid
%%{init: {"themeVariables": {"cScale0": "#4B5165", "cScaleLabel0": "#FFFFFF", "cScale1": "#0F766E", "cScaleLabel1": "#FFFFFF", "cScale2": "#0EA5E9", "cScaleLabel2": "#04283A", "cScale3": "#4B5165", "cScaleLabel3": "#FFFFFF", "cScale4": "#C6E355", "cScaleLabel4": "#20242E"}}}%%
timeline
    title Data, then software, then one platform
    2018 to 2022 · Freelance : IT consultant and developer
        : TypeScript, Python, SQL for client systems
    ioki · a Deutsche Bahn company : Data Scientist
        : Geodata quality automation, Airflow pipelines
        : Demand forecasting with PyTorch transformers
        : M.Sc. Frankfurt School alongside
    Workever : Cofounder
        : Learned to build a product, not a project
    EMPA Spain : Cofounder and Director Ejecutivo
        : Data and management consulting, DE and ES, ~20 people
    KIVO : One platform that runs an entire company
        : Built inside EMPA, ran the firm on it for 3 years
        : Now shipping to customers on a European stack
```

* 🏗️ **Cofounder & Director Ejecutivo**, EMPA Spain, data and management consulting across DE and ES
* 🤖 Deep in **AI supported business intelligence** and software automation, including the fun parts of the EU AI Act
* 🎓 **M.Sc. Management (Data & Business Analytics)**, Frankfurt School. Thesis: geospatial time series forecasting with transformers *(with ioki, a Deutsche Bahn company)*
* 🖨️ Off keyboard: 3D printing with **Klipper**, and pretending Valencia's weather is a productivity tool

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
| [`lexware-client-ts`](https://github.com/YannickAaron/lexware-client-ts) | Modern, fully typed TypeScript client for the Lexware API |
| [`BetterMSFile`](https://github.com/YannickAaron/BetterMSFile) | A saner explorer app for OneDrive and SharePoint |
| [`quick-docu-mcp`](https://github.com/YannickAaron/quick-docu-mcp) | MCP server for quick documentation capture |
| [`scw-easy-container-redeploy`](https://github.com/YannickAaron/scw-easy-container-redeploy) | GitHub Action to redeploy a Scaleway container by name |
| [`TimeSeriesForecasting`](https://github.com/YannickAaron/TimeSeriesForecasting) | Spatiotemporal forecasting experiments |

> 🔒 Most of my daily work, KIVO included, lives in private repos. The stats below are the honest version.

---

## 📊 Stats

<div align="center">

<img width="49%" src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=YannickAaron&theme=transparent" alt="GitHub stats">
<img width="49%" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=YannickAaron&theme=transparent" alt="Repos per language">

<img width="62%" src="https://streak-stats.demolab.com?user=YannickAaron&hide_border=true&background=00000000&ring=C6E355&fire=C6E355&currStreakLabel=C6E355&sideLabels=8B949E&dates=8B949E&currStreakNum=8B949E&sideNums=8B949E&stroke=8B949E" alt="Streak">

<img width="80%" src="https://ghchart.rshah.org/C6E355/YannickAaron" alt="Contribution heatmap">

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
  <img alt="Pac Man played on my contribution graph" src="assets/arcade/pacman-contribution-graph.svg">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/arcade/galaga-contribution-graph-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/arcade/galaga-contribution-graph.svg">
  <img alt="Galaga played on my contribution graph" src="assets/arcade/galaga-contribution-graph.svg">
</picture>

</details>

---

## 🤝 Let's talk

If you are wrestling with data governance, an AI project that stalled on messy data, or a company
drowning in the administration between its tools, that is my favourite kind of conversation.

<div align="center">

[![LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/yannickaaron/)
[![Website](https://img.shields.io/badge/EMPA_Consulting-4B5165?style=for-the-badge&labelColor=20242E)](https://empa.co)
[![KIVO](https://img.shields.io/badge/See_KIVO-C6E355?style=for-the-badge&labelColor=20242E)](https://kivo.eco)

🇩🇪 Deutsch · 🇬🇧 English · 🇪🇸 Español

</div>
