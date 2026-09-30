# GatePass Commercial Command Center

**The strategic research, market intelligence, and commercial planning repository for [GatePass](https://gatepass.io) — a guard-facing, offline-first digital access-management SaaS platform built for residential estates, gated communities, and commercial properties in Kenya.**

---

## What This Repository Contains

This repository is the **Commercial Command Center** for GatePass. It consolidates all market research, customer discovery, competitive analysis, regulatory intelligence, commercial strategy, go-to-market planning, investor matchmaking, and positioning frameworks into a structured, version-controlled knowledge base.

It is organized into three layers:

| Layer | Directory | Purpose |
|-------|-----------|---------|
| **Canonical Outputs** | `docs/` | The 9 synthesized, authoritative commercial documents (numbered `00` through `08`). These are the final reference documents used for decision-making, pitch preparation, and strategic execution. |
| **Underlying Research** | `research/` | The deep research reports generated through NotebookLM and other research tools. These contain the raw investigative data, citations, source analysis, and extended findings that were distilled into the canonical `docs/`. |
| **Supporting Sources** | `sources/` | Reserved for primary source materials — regulatory PDFs, court rulings, industry reports, screenshots, and raw data files referenced in the research. Directories are pre-structured for future population. |

---

## Canonical Documents (`docs/`)

The `docs/` directory contains 9 numbered documents forming the complete commercial intelligence stack:

| # | Document | Purpose |
|---|----------|---------|
| **00** | `00_GatePass_Product_Truth.md` | **Product Truth Baseline.** Repository-verified technical capabilities, architecture, workflows, completed features, and known limitations. The single source of truth for what GatePass actually does today. |
| **01** | `01_Kenya_Private_Security_Market.md` | **Market Dossier.** Kenya's private security industry structure, PSRA regulations, the KES 30,000 minimum wage shock, geographic demand concentration, and macro-environmental drivers. |
| **02** | `02_Customer_Discovery.md` | **Customer Discovery.** Stakeholder mapping across 9 roles, 12 gate security workflows, buyer procurement dynamics, behavioral say-do gaps, and validation scorecards. |
| **03** | `03_Competition_And_Alternatives.md` | **Competitive Landscape.** Direct competitors (SOJA VMS, EstateIQ, Mygate, SecuViz), adjacent platforms (Nyumba Zetu, TrackTik), hardware substitutes, and entrenched paper logbook analysis. |
| **04** | `04_Regulatory_And_Legal_Landscape.md` | **Legal & Regulatory Dossier.** Dual statutory regimes — PSRA Act No. 13 of 2016 and Data Protection Act 2019 (ODPC). Guard Force Numbers, search powers, data processing obligations, Evidence Act Cap 80, and compliance roadmap. |
| **05** | `05_Commercial_Strategy.md` | **Commercial Strategy.** Dual-buyer channel thesis (Route A: Security Firms vs Route B: Direct HOAs), pricing models, TAM/SAM/SOM sizing, unit economics, and defensibility analysis. |
| **06** | `06_Sales_And_Go_To_Market.md` | **Sales & GTM Playbook.** Solo-founder sales system, ICP taxonomy, field mapping methodology, "The Live Gate Drill" demo framework, pilot scorecard, objection scripts, and conversion mechanics. |
| **07** | `07_Investor_Intelligence.md` | **Capital Intelligence.** East African venture capital ecosystem analysis, investor matchmaking across 5 structural dimensions, fund profiles (Antler, FFA, Novastar, Launch Africa, etc.), and pre-seed raising strategy. |
| **08** | `08_Positioning_And_Pitch.md` | **Master Positioning & Pitch Framework.** 20 core strategic determinations, pitch deck narrative architecture, elevator pitches, one-pagers, objection defense frameworks, and fundraising roadmap. |

---

## Research Reports (`research/`)

The `research/` directory contains the underlying deep research reports organized by subject area. These are the investigative source documents from which the canonical `docs/` were synthesized.

| Subfolder | Research Report | Feeds Into |
|-----------|----------------|------------|
| `market/` | `01_Research_Kenya_Private_Security.md` | → `docs/01_Kenya_Private_Security_Market.md` |
| `customers/` | `02_Research_Customer_Discovery.md` | → `docs/02_Customer_Discovery.md` |
| `competition/` | `03_Research_Competition_And_Alternatives.md` | → `docs/03_Competition_And_Alternatives.md` |
| `regulation/` | `04_Research_Regulatory_And_Legal.md` | → `docs/04_Regulatory_And_Legal_Landscape.md` |
| `commercial/` | `05_Research_Commercial_Strategy.md` | → `docs/05_Commercial_Strategy.md` |
| `sales/` | *(no separate sales research report exists)* | — |
| `investors/` | `07_Research_Investor_Intelligence.md` | → `docs/07_Investor_Intelligence.md` |
| `pitch/` | `08_Research_Positioning_And_Pitch.md` | → `docs/08_Positioning_And_Pitch.md` |

> **Note:** There are 7 research reports feeding into 9 canonical documents. Some research reports (e.g., `05_Research_Commercial_Strategy.md`) contain material that was split across multiple canonical documents during synthesis. No research report was fabricated to fill gaps.

---

## Supporting Sources (`sources/`)

The `sources/` directory is pre-structured with category folders matching the research and docs taxonomy. These directories are reserved for primary source materials such as:

- Regulatory PDFs (PSRA Legal Notices, DPA 2019 text, ODPC Guidance Notes)
- Court rulings (ELRC judgments on minimum wage)
- Industry reports (Usalama Reforms Forum, Strathmore University surveys)
- Competitor screenshots and pricing captures
- Raw market data and interview transcripts

Source directories currently contain `.gitkeep` placeholders and will be populated as primary materials are collected.

---

## Relationship Between Research and Canonical Docs

```
┌─────────────────────┐     ┌──────────────────────┐     ┌────────────────────┐
│   sources/          │     │   research/           │     │   docs/            │
│   Primary materials │────▶│   Deep research       │────▶│   Canonical        │
│   PDFs, rulings,    │     │   reports with full   │     │   synthesized      │
│   raw data          │     │   citations & analysis│     │   outputs (00-08)  │
└─────────────────────┘     └──────────────────────┘     └────────────────────┘
       (raw inputs)              (investigation)            (final reference)
```

All claims and citations in the canonical documents trace back to the research reports, which in turn reference numbered sources grounded in publicly verifiable materials.

---

## Repository Structure

```
GatePass Commercial Command Center/
│
├── README.md
│
├── docs/
│   ├── 00_GatePass_Product_Truth.md
│   ├── 01_Kenya_Private_Security_Market.md
│   ├── 02_Customer_Discovery.md
│   ├── 03_Competition_And_Alternatives.md
│   ├── 04_Regulatory_And_Legal_Landscape.md
│   ├── 05_Commercial_Strategy.md
│   ├── 06_Sales_And_Go_To_Market.md
│   ├── 07_Investor_Intelligence.md
│   └── 08_Positioning_And_Pitch.md
│
├── research/
│   ├── market/
│   │   └── 01_Research_Kenya_Private_Security.md
│   ├── customers/
│   │   └── 02_Research_Customer_Discovery.md
│   ├── competition/
│   │   └── 03_Research_Competition_And_Alternatives.md
│   ├── regulation/
│   │   └── 04_Research_Regulatory_And_Legal.md
│   ├── commercial/
│   │   └── 05_Research_Commercial_Strategy.md
│   ├── sales/
│   │   └── .gitkeep
│   ├── investors/
│   │   └── 07_Research_Investor_Intelligence.md
│   └── pitch/
│       └── 08_Research_Positioning_And_Pitch.md
│
└── sources/
    ├── market/
    ├── customers/
    ├── competition/
    ├── regulation/
    ├── commercial/
    ├── sales/
    ├── investors/
    └── pitch/
```

---

## About GatePass

**GatePass** is a guard-facing, offline-first digital access-management SaaS platform designed to replace insecure paper visitor logbooks at residential estates, gated communities, and commercial properties across Kenya and East Africa.

The platform addresses two compounding structural crises in Kenya's private security industry:

1. **The KES 30,000 Minimum Wage Shock** — PSRA Legal Notice No. PSRA/005/2023, upheld by the Employment and Labour Relations Court (ELRC), mandates a statutory gross minimum wage of KES 30,000/month per security guard, forcing security companies to adopt technology to justify higher billing rates and protect margins.

2. **Data Protection Act (DPA 2019) Liability** — The Office of the Data Protection Commissioner (ODPC) classifies open paper gate logbooks as illegal exposures of Personal Identifiable Information (PII), with administrative penalties capped at KES 5,000,000 or 1% of annual turnover.

GatePass operates a dual-buyer channel model:
- **Route A:** B2B channel partnerships with Tier-1 and Tier-2 private security companies
- **Route B:** Direct B2B SaaS sales to estate HOAs and property management agencies

---

*This repository is maintained as the strategic intelligence foundation for GatePass commercial operations, fundraising, and go-to-market execution.*
