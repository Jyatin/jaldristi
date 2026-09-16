# JalDrishti 2030

**An IoT–AI Digital Twin for predictive water-stress assessment and intervention planning in Bengaluru.**

> **Research implementation / frontend prototype**
>
> This repository is the software implementation of our research paper, **“JalDrishti 2030: An IoT–AI Digital Twin for Predictive Water-Stress and Intervention Planning in Bengaluru,”** submitted to the **SMART CITY 2030** international student research competition.

## What is JalDrishti?

JalDrishti 2030 is a decision-support platform designed to help planners understand **where water stress may emerge, how conditions may evolve, and which intervention strategies can be evaluated before resources are committed**.

The project is intentionally positioned as a **planning and research layer above utility operations**. It is not an operational water-control system and does not autonomously control infrastructure.

The planned system brings together:

- water demand and supply indicators
- rainfall and groundwater information
- population and spatial context
- water-loss / reliability indicators
- predictive modelling
- a neighbourhood-level Water-Stress Index
- Digital Twin concepts for water-network simulation
- EPANET / WNTR hydraulic simulation
- multi-objective intervention optimisation using NSGA-II
- scenario analysis for 2030 planning
- provenance, uncertainty, and equity-aware decision support

## Relationship to the research paper

The research paper defines the **scientific problem, architecture, methodology, assumptions, and proposed analytical workflow**.

This repository is the **implementation track** of that work:

```text
Research Paper
      ↓
Proposed methodology & architecture
      ↓
Working software prototype
      ↓
Real-data integration
      ↓
Hydraulic + forecasting experiments
      ↓
Optimisation experiments
      ↓
Measured results and validation
```

The aim is to keep the implementation traceable to the paper rather than building a generic water dashboard.

### Paper → Implementation

| Research component | Repository implementation / planned module |
|---|---|
| Sense → Decide cycle | Application flow and decision-support workflow |
| Phase 2 data audit | Data catalogue, provenance and availability layer |
| Water-Stress Index | WSI calculation module with weighting and sensitivity analysis |
| Predictive modelling | Forecasting module with chronological validation |
| Level 2 Digital Twin | Representative hydraulic network, later replaceable with calibrated EPANET/WNTR models |
| Intervention library | Structured intervention definitions and scenario parameters |
| Multi-objective optimisation | Pareto-based portfolio search, planned NSGA-II integration |
| Equity-aware planning | Equity / vulnerability objective in intervention evaluation |
| Uncertainty & sensitivity | Forecast intervals, weighting switch and stability analysis |
| 2030 scenarios | Scenario engine for alternative planning assumptions |
| Governance & privacy | Decision-support only; no autonomous operational control |

## Current status

### Phase 1 — Frontend prototype ✅

The current frontend provides the research-facing interface and browser-side analytical prototype.

Planned/represented modules include:

- **Water Stress** — neighbourhood map, indicators, drivers and scenarios
- **Network** — representative distribution-network view
- **Optimisation** — intervention portfolio and Pareto exploration
- **Data** — source and availability audit
- **Provenance** — traceability from a displayed result back to indicators, assumptions and data limitations

### Important data boundary

This project distinguishes **real evidence from synthetic demonstration data**.

At the prototype stage, some neighbourhood-level and hydraulic variables are synthetic because the research audit identified gaps in publicly available data at the resolution required for the complete model.

Therefore:

> **Synthetic prototype outputs must never be presented as measured Bengaluru water-system results.**

As the project advances, synthetic fixtures will be replaced by documented public datasets where available, followed by validated analytical services and calibrated network models where appropriate data exists.

## Proposed technical architecture

```text
                    JALDRISHTI 2030
                           │
          ┌────────────────┼─────────────────┐
          ▼                ▼                 ▼
     Data Layer       Analytics Layer     Spatial Layer
          │                │                 │
          └────────────────┼─────────────────┘
                           ▼
                  Water-Stress Engine
                           │
                           ▼
                    Forecasting Model
                           │
                           ▼
                    Digital Twin Layer
                           │
                      EPANET / WNTR
                           │
                           ▼
                  Scenario Simulation
                           │
                           ▼
                  NSGA-II Optimisation
                           │
                           ▼
                Decision-Support Dashboard
```

## Planned implementation roadmap

### Phase 1 — Frontend prototype

- React / Next.js interface
- research-oriented dashboard
- WSI prototype
- scenario exploration
- provenance and data-audit views
- synthetic demonstration fixtures

### Phase 2 — Backend foundation

- FastAPI analytical service
- PostgreSQL + PostGIS
- dataset and provenance versioning
- public-data ingestion layer
- API boundary between UI and analytics

### Phase 3 — Real analytics

- server-side WSI calculations
- forecasting models
- rolling / chronological validation
- per-area error analysis
- uncertainty and sensitivity reporting

### Phase 4 — Hydraulic Digital Twin

- EPANET / WNTR integration
- extended-period simulation
- pressure and flow analysis
- leakage / supply perturbation scenarios
- calibration only where suitable field data is available

### Phase 5 — Multi-objective optimisation

- NSGA-II implementation
- intervention portfolio generation
- hydraulic response evaluation
- Pareto-front analysis
- cost, stress, population protection and equity objectives

### Phase 6 — Decision workflow

- scenario comparison
- reviewer / planning workflow
- intervention acceptance notes
- experiment and audit history
- research-result export

## Technology

### Current frontend

- Next.js
- React
- TypeScript
- Tailwind CSS
- hand-built SVG visualisations

### Planned analytical stack

- Python
- FastAPI
- PostgreSQL / PostGIS
- scikit-learn or equivalent forecasting stack
- EPANET / WNTR
- pymoo / NSGA-II
- Parquet / analytical result storage

## Research principle

JalDrishti is being developed with a strict separation between:

**what is measured → what is inferred → what is simulated → what is optimised → what is recommended for further evaluation.**

This distinction is essential for a research implementation because a polished interface must not imply a level of empirical validation that the underlying data does not support.

## Repository structure

The repository will evolve from the current frontend prototype into a full research implementation:

```text
jaldristi/
├── src/                 # frontend application
├── public/              # static assets
├── data/                # documented fixtures / datasets
├── analytics/           # forecasting and WSI services
├── hydraulics/          # EPANET / WNTR models and jobs
├── optimisation/        # NSGA-II experiments
├── docs/                # research-to-code documentation
├── experiments/         # reproducible experiments and results
└── README.md
```

## Reproducibility & provenance

Every future analytical result should be traceable to:

1. the dataset or fixture used,
2. the transformation / normalisation applied,
3. the model and parameters used,
4. the scenario assumptions,
5. the optimisation objectives and constraints, and
6. the experiment version that produced the result.

## Author

**Jyatin Kumar Singh**  
B.Tech Computer Science & Engineering, Lovely Professional University

## Research

**Research paper:** *JalDrishti 2030: An IoT–AI Digital Twin for Predictive Water-Stress and Intervention Planning in Bengaluru*

**Research competition:** III International Competition of Student and Young Researcher Projects — **SMART CITY 2030: Managing Sustainable Urban Development in the BRICS Countries**

**Track:** Smart-City Technologies and Services

## Status

🚧 **Active research implementation — frontend prototype stage**

The current objective is to incrementally turn the research framework into a reproducible software system and experimental platform.
