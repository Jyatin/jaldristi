# 💧 JalDrishti 2030

### *An IoT–AI Digital Twin for Predictive Water-Stress and Intervention Planning in Bengaluru*

<p align="center">
  <strong>From research paper → working prototype → experimental digital twin</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Research%20Prototype-orange?style=for-the-badge" alt="Research Prototype" />
  <img src="https://img.shields.io/badge/Domain-Smart%20City%20%7C%20Water%20Resilience-0f766e?style=for-the-badge" alt="Smart City Water Resilience" />
  <img src="https://img.shields.io/badge/Research-AI%20%2B%20Digital%20Twin-111827?style=for-the-badge" alt="AI Digital Twin" />
</p>

> **JalDrishti 2030 is the software implementation of our research paper, _“JalDrishti 2030: An IoT–AI Digital Twin for Predictive Water-Stress and Intervention Planning in Bengaluru.”_**
>
> The goal is to turn the proposed research framework into a reproducible software and experimentation platform that can identify water stress, forecast future conditions, simulate network behaviour, and evaluate intervention strategies for Bengaluru.

---

## 🔬 The Research Behind the Project

JalDrishti 2030 was proposed for the **III International Competition of Student and Young Researcher Projects — “SMART CITY 2030: Managing Sustainable Urban Development in the BRICS Countries”**, Category 3: **Smart-City Technologies and Services**.

The research paper proposes a planning and equity-prioritisation layer that combines water consumption, groundwater, rainfall, supply, losses, demographic and spatial information into a **Water-Stress Twin**. Forecasts are geographically disaggregated to appropriate hydraulic network nodes, evaluated through **EPANET/WNTR**, and passed to a multi-objective optimisation stage using **NSGA-II**.

The paper explicitly frames the work as a proposed research approach and does **not** claim city-scale deployment or validated improvements in accuracy, hydraulic performance, cost, or public opinion. This repository follows the same evidence boundary.

### 📄 Research paper

**JalDrishti 2030: An IoT–AI Digital Twin for Predictive Water-Stress and Intervention Planning in Bengaluru**  
**City:** Bengaluru, Karnataka, India  
**Track:** Smart-City Technologies and Services

---

## 📑 Research Paper — In Context

The repository keeps the research foundation visible so that the implementation can always be traced back to the original work.

### Paper — opening / research framing

![JalDrishti 2030 Research Paper](paper/paper-page-1.jpg)

### Figure 4 — Proposed 2030 planning and intervention framework

![Proposed 2030 scenario and intervention framework](paper/figure-4-scenarios.png)

> **Research principle:** the paper defines the scientific framework; the repository progressively implements and tests that framework. Prototype outputs are not presented as measured Bengaluru results.

---

# 🧭 What Are We Building?

JalDrishti is **not simply a water dashboard** and not only an ML forecasting model.

It is a **decision-support system for urban water resilience**.

```text
Bengaluru Water & Spatial Data
              │
              ▼
       Water-Stress Engine
              │
              ▼
       Demand / Stress Forecast
              │
              ▼
        Digital Water Twin
          EPANET / WNTR
              │
              ▼
       Scenario Simulation
              │
              ▼
       NSGA-II Optimisation
              │
              ▼
   Intervention Trade-offs
              │
              ▼
      Planning Dashboard
```

The intended system should help answer three practical research questions:

1. **Where is water stress occurring or emerging?**
2. **How could demand and stress evolve under future conditions?**
3. **Which intervention portfolios can be evaluated under cost, hydraulic, protection, equity and implementation constraints?**

---

# 🚀 Development in 3 Phases

The project is deliberately being developed in **three major phases**, moving from interface and research translation toward a reproducible analytical system.

## Phase 1 — Research Prototype & Decision Interface

**Goal:** Turn the research framework into an interactive software prototype.

### What we build

- Research-oriented Next.js frontend
- Bengaluru / neighbourhood water-stress visualisation
- Water-Stress Index prototype
- Stress drivers and indicator views
- Scenario exploration
- Representative hydraulic-network visualisation
- Intervention library
- Optimisation / Pareto exploration interface
- Data availability and provenance views
- Explicit separation of real evidence and synthetic demonstration data

### Output

A working **research-facing prototype** that communicates the complete JalDrishti workflow and provides a foundation for the analytical implementation.

**Current status: 🟢 In progress / frontend prototype**

---

## Phase 2 — Data, AI & Digital Twin Engine

**Goal:** Replace browser-side demonstration logic with reproducible analytical services.

### What we build

- Public-data ingestion and provenance pipeline
- PostgreSQL / PostGIS data layer
- FastAPI analytical backend
- Water-Stress Index calculation service
- Demand forecasting models
- Chronological / rolling validation
- Per-area forecasting error analysis
- Uncertainty and sensitivity analysis
- EPANET / WNTR hydraulic simulation
- Representative-to-calibrated network progression where suitable data exists

### Output

A research-grade analytical backend where forecasts and water-stress results can be reproduced from documented datasets, parameters and assumptions.

**Status: 🔵 Proposed / next implementation stage**

---

## Phase 3 — Intervention Optimisation & Experimental Validation

**Goal:** Implement the paper's decision and optimisation methodology and generate measurable research results.

### What we build

- NSGA-II multi-objective optimisation
- Intervention portfolio generation
- Hydraulic feasibility checks
- Scenario simulation for 2030
- Cost and water-saving objectives
- Residual stress evaluation
- Population-protection metrics
- Equity-aware evaluation
- Uncertainty-aware comparisons
- Pareto-front analysis
- Reproducible experiments and result exports
- Research-result dashboard and documentation

### The four paper scenarios

| Scenario | Purpose |
|---|---|
| **A — Business as Usual** | Baseline for comparison |
| **B — Supply Augmentation** | Examine increased supply / intervention capacity |
| **C — Predictive Intervention** | Examine priority-driven intervention planning |
| **D — Integrated Water Resilience** | Combine the relevant planning dimensions into an integrated portfolio |

All scenarios are evaluated using common dimensions from the paper, including **WSI, residual stress, intervention cost, water savings, population protected, equity and hydraulic feasibility**.

**Status: 🟣 Research implementation / experimental stage planned**

---

# 🧠 Paper → Software Traceability

The most important design rule for this repository is **research traceability**.

| Research paper concept | JalDrishti implementation |
|---|---|
| Sense → Decide planning workflow | End-to-end application workflow |
| Water-Stress Twin | WSI engine + spatial indicators |
| Water consumption / demand | Data and forecasting layer |
| Groundwater + rainfall | Environmental and stress-driver inputs |
| Spatial disaggregation | Ward / neighbourhood representation |
| Predictive modelling | Demand and stress forecasting service |
| Digital Twin | Hydraulic network model |
| EPANET / WNTR | Hydraulic simulation engine |
| Intervention library | Parameterised intervention definitions |
| NSGA-II | Multi-objective portfolio optimisation |
| Equity prioritisation | Population / vulnerability objective layer |
| Uncertainty & sensitivity | Model uncertainty and weighting analysis |
| 2030 scenarios | Scenario engine |
| Common evaluation dimensions | Experimental metrics and comparison layer |

This means every major feature should answer:

> **“Which part of the research methodology does this implement?”**

---

# 📊 What the Final System Should Demonstrate

A planner should eventually be able to select an area or scenario and move through a workflow such as:

```text
1. Observe
   ↓
2. Measure current water stress
   ↓
3. Forecast future demand / stress
   ↓
4. Simulate the hydraulic network
   ↓
5. Select possible interventions
   ↓
6. Optimise intervention portfolios
   ↓
7. Compare cost / stress / savings / protection / equity
   ↓
8. Inspect uncertainty and assumptions
   ↓
9. Export reproducible research results
```

The system therefore connects **prediction → simulation → optimisation → decision support**.

---

# ⚠️ Research Integrity & Data Boundary

JalDrishti is being developed with a strict distinction between:

**Measured → Inferred → Simulated → Optimised → Proposed for evaluation**

At the prototype stage, some neighbourhood-level and hydraulic values may be synthetic because the research audit identified gaps in publicly available data at the resolution required for the complete model.

Therefore:

> **Synthetic values are demonstration fixtures and must never be presented as measured Bengaluru water-system results.**

Similarly, an optimisation output from an uncalibrated representative network is an **experimental result of the model**, not evidence of real-world infrastructure performance.

---

# 🏗️ Proposed Architecture

```text
                         JALDRISHTI 2030
                                │
          ┌─────────────────────┼─────────────────────┐
          ▼                     ▼                     ▼
      DATA LAYER          ANALYTICS LAYER       SPATIAL LAYER
          │                     │                     │
          └─────────────────────┼─────────────────────┘
                                ▼
                       WATER-STRESS ENGINE
                                │
                                ▼
                       FORECASTING ENGINE
                                │
                                ▼
                       DIGITAL WATER TWIN
                                │
                           EPANET / WNTR
                                │
                                ▼
                       SCENARIO SIMULATION
                                │
                                ▼
                       NSGA-II OPTIMISATION
                                │
                                ▼
                    DECISION-SUPPORT DASHBOARD
```

---

# 🛠️ Technology Stack

### Current prototype

- **Next.js**
- **React**
- **TypeScript**
- **Tailwind CSS**
- SVG / browser-side visualisations

### Planned research implementation

- **Python**
- **FastAPI**
- **PostgreSQL + PostGIS**
- **scikit-learn / forecasting libraries**
- **EPANET / WNTR**
- **pymoo / NSGA-II**
- **Parquet / analytical result storage**

---

# 📁 Repository Roadmap

```text
jaldristi/
│
├── src/                  # Next.js research interface
├── public/               # Frontend assets
│
├── paper/                # Research-paper figures and evidence
│   ├── paper-page-1.jpg
│   └── figure-4-scenarios.png
│
├── data/                 # Documented datasets / fixtures
├── analytics/             # WSI + forecasting services
├── hydraulics/            # EPANET / WNTR models
├── optimisation/          # NSGA-II experiments
├── experiments/           # Reproducible experiments and results
├── docs/                  # Research-to-code documentation
│
└── README.md
```

---

# 🔁 Reproducibility

Future analytical results should be traceable to:

1. dataset / fixture version,
2. preprocessing and transformations,
3. model and parameters,
4. scenario assumptions,
5. optimisation objectives and constraints,
6. hydraulic-network configuration, and
7. experiment version / commit.

This is important because JalDrishti is being developed as a **research implementation**, not merely a product demo.

---

# 👨‍💻 Research & Development

**Author:** Jyatin Kumar Singh  
**Programme:** B.Tech Computer Science & Engineering  
**University:** Lovely Professional University  
**City studied:** Bengaluru, Karnataka, India

### Research Paper

**JalDrishti 2030: An IoT–AI Digital Twin for Predictive Water-Stress and Intervention Planning in Bengaluru**

### Competition

**III International Competition of Student and Young Researcher Projects**  
**“SMART CITY 2030: Managing Sustainable Urban Development in the BRICS Countries”**  
**Category 3 — Smart-City Technologies and Services**

---

# 📌 Current Status

> 🚧 **Active research implementation**
>
> **Phase 1:** Frontend / research prototype  
> **Phase 2:** Data + AI + Digital Twin engine  
> **Phase 3:** NSGA-II optimisation + experimental validation

The long-term objective is to transform the proposed research framework into a **reproducible, transparent and experimentally testable software system for predictive urban water-stress and intervention planning**.

---

<p align="center">
  <strong>JalDrishti 2030</strong><br/>
  <em>Turning a research framework into a working Digital Twin for urban water resilience.</em>
</p>
