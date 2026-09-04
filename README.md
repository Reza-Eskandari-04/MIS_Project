#  Copper Extraction & Processing Plant — Management Information System (MIS)

[![BPMN 2.0](https://img.shields.io/badge/BPMN-2.0-blue.svg)](https://www.omg.org/spec/BPMN/2.0/)
[![SQL Server](https://img.shields.io/badge/Database-MS%20SQL%20Server-red.svg)](https://www.microsoft.com/sql-server)
[![Power BI](https://img.shields.io/badge/Analytics-Power%20BI%20%7C%20DAX-yellow.svg)](https://powerbi.microsoft.com/)
[![Industrial Engineering](https://img.shields.io/badge/Discipline-Industrial%20Engineering-orange.svg)](#)

An enterprise-grade **Management Information System (MIS)** designed for an end-to-end copper mining, comminution, inventory, and refining complex. This project bridges operational engineering workflows with data architecture—translating physical metallurgical processes into formal **BPMN 2.0 process models**, a normalized **relational database schema in SQL Server**, and multi-tier **executive BI dashboards in Power BI**.

This project was developed as the final capstone for the **Management Information Systems (MIS)** course.

- **Instructor:** Dr. Hadi Mosadegh
- **Course:** Management Information Systems (MIS)
- **Department:** Industrial Engineering
---


##  Executive Summary & Industrial Domain

The production of refined electrolytic copper cathodes ($99.99\%$ purity) involves complex, capital-intensive unit operations vulnerable to equipment downtime, recovery losses, high electricity tariffs, and transport bottlenecks. 

This project designs a unified **MIS framework** that tracks, monitors, and optimizes five core operational pillars:
1. **Mine Haulage Logistics:** Tracking run-of-mine (ROM) haul truck cycles, payload limits, and route hazards.
2. **Geological Exploration:** Delineating prospective drilling coordinates from spatial assays and management sign-offs.
3. **Primary Comminution:** Regulating jaw crusher feed rates, Closed Side Settings (CSS), and scrap/waste ratios.
4. **Warehouse \& Stock Buffer Management:** Preventing storage overfill hazards ($>90\%$ capacity) and raw consumable stockouts.
5. **Quality Assurance \& Multi-Stage Assaying:** Multivariate scoring of copper concentrates, penalizing moisture and impurities (Fe, Zn).

---


##  Project Architecture (4 Phases)

```text
[ Phase 0 ] ──► Algorithmic Process Mapping (Roles, Triggers, Decision Gateways)
     │
[ Phase 1 ] ──► Visual Paradigm BPMN 2.0 (Pools, Swimlanes, Sub-Processes, Boundary Events)
     │
[ Phase 2 ] ──► Database Normalization (MS SQL Server, 10 Tables, Constraints, 12 T-SQL Queries)
     │
[ Phase 3 ] ──► Business Intelligence (Power Query ETL, Advanced DAX, 4 Dashboard Sheets, 6 KPIs)
```

### Phase 0: Process Architecture & Algorithmic BPMN Definition
- Decomposed the global 9-stage copper extraction lifecycle.
- Formulated the execution logic for **5 critical operational processes**:
  - *Process 1:* Raw Material Transportation (Haulage Dispatch System)
  - *Process 2:* Geological Investigation & Drill Pattern Planning
  - *Process 3:* Primary Comminution (Jaw Crushing Operations)
  - *Process 4:* Warehouse Inventory Control & Stock Optimization
  - *Process 5:* Multi-Stage Quality Sampling of Ore, Slurry, and Cathodes
- Defined swimlanes (e.g., *Mine Dispatch, Rig Operators, Safety Officers, QC Labs*), input triggers, exclusive decision gateways (XOR), and terminal conditions.

### Phase 1: Visual BPMN 2.0 Simulation (Visual Paradigm)
- Implemented standard **BPMN 2.0 diagrams** in Visual Paradigm with strict organizational swimlanes.
- Integrated specialized tasks (**User Tasks, Service Tasks, Manual Tasks, Script Tasks**).
- Modeled hierarchical abstraction using **Embedded and Transactional Sub-Processes**.
- Enforced operational fault handling using **Intermediate Boundary Events** (Timer timeouts and Error catching).

### Phase 2: Relational Database Architecture & Analytical SQL
- Developed an enterprise relational schema comprising **10 interconnected tables** with referential integrity constraints (`PRIMARY KEY`, `FOREIGN KEY`, `CHECK`).
- Enriched dataset with **>= 150 records per table** spanning a realistic 2-year industrial operating horizon.
- Implemented core metallurgical and logistics equations:
  - **Crushing Mass Balance:** `Output Weight = Input Weight - Waste Weight`
  - **Warehouse Capacity Utilization:** `Utilization % = (SUM(CurrentVolume) / CapacityTons) * 100`
  - **Dry Weight Calculation:** `Dry_Weight = (1 - Moisture_Percent) * SampleWeightKg`
  - **Multivariate Quality Index:**
    `Test_Score = 0.5(Purity) + 0.3(Cu%) - 0.1(Fe%) - 0.1(Zn%) - 0.2(Moisture)`
- Authored **12 analytical T-SQL queries** extracting business metrics (energy intensity per ton, warehouse overfill risks, regional haulage liabilities, and multi-depot statistical quality profiles).

### Phase 3: Executive Business Intelligence Dashboards (Power BI)
- Built a multi-page interactive analytics suite in **Power BI Desktop** powered by custom **Power Query M** data transformations and advanced **DAX calculated columns/measures**.
- Engineered **4 specialized executive dashboard sheets**:

| Dashboard Sheet | Focus Area | Key Visuals & Analysis |
| :--- | :--- | :--- |
| **Page 1: Waste & Storage** | Comminution & Capacity | Regional waste distribution donut, warehouse utilization bar charts, throughput treemaps, and overfill warning gauges. |
| **Page 2: Quality Assays** | Laboratory Metallurgical Health | Daily dry weight vs. composite QC trends, lab sampling intensity, and mine site grade rankings. |
| **Page 3: Fleet Logistics** | Transit Economics & Safety | Distance vs. accident correlations, monthly transport cost breakdown, and haulage cost variance cards. |
| **Page 4: Energy & Carbon** | Tariffs & ESG Compliance | Energy draw by shift, carbon footprint (`kg CO2/kWh`) by location, and tariff efficiency gauges. |

##  Tech Stack & Tooling Ecosystem

- **Business Process Modeling:** Visual Paradigm (BPMN 2.0 Standard)
- **Database Engine:** Microsoft SQL Server, SQL Server Management Studio (SSMS), T-SQL
- **Business Intelligence & Data Modeling:** Microsoft Power BI Desktop, Power Query (M-Language), DAX
- **Data Engineering & Preparation:** Microsoft Excel

- ## 💡 Key Learnings & Engineering Insights

This capstone project provided critical end-to-end systems engineering insights across management information systems:

- **Systems Thinking & Cross-Functional Alignment:** Modeled how operational decisions at the mine pit (e.g., blasthole spacing and ore fragmentation) propagate downstream—directly affecting jaw crusher wear rates, conveyor energy consumption, and warehouse utilization.
- **Translating Physical Phenomena into Data Schemas:** Learned to design normalized schemas that maintain physical mass balances (`Input = Output + Waste`), enforce geographical dispatch constraints, and model equipment state machines (`Operational`, `Maintenance`, `Out of Service`).
- **Defensive Data Modeling & Quality Scoring:** Formulated synthetic quality indexes (`Test_Score`) using multi-attribute utility theory—giving weight to valuable copper content while penalizing moisture and impurities like Iron and Zinc.
- **DAX Context Transition & Business Intelligence Architecture:** Gained proficiency in time-intelligence DAX expressions, dynamic grouping, Power Query ETL pipelines, and designing actionable executive dashboards that guide strategic capital expenditure (e.g., warehouse expansion vs. fleet optimization).
