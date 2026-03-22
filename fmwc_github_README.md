# 5-Year Operational & Financial Model for a 3PL Logistics Company

**Financial Modeling World Cup (FMWC) · Global Ranking #172**

> Extended practice build using a competition case by **Julien Lacaze** (FMWC). The model and dashboard were built from scratch using the original narrative case and assumptions table. Accuracy was checked against the 20 official FMWC scored questions.

---

## Overview

A 5-year monthly financial projection model for **X-Logistic Services (XLS)**, a third-party logistics company. The model forecasts EBITDA across 61 months and evaluates whether management should sign a contract with a new large client.

**Tools:** Advanced Excel · Financial Modeling

---

## Business Question

> *Should XLS sign a contract with Tim Forward Brands — and will it be profitable or operationally disruptive?*

---

## Model Architecture

### Volume Engine
- Six clients across three segments (Retail, E-commerce, Industrial)
- Client-specific baseline volumes, segment-level seasonality profiles, and compounding annual growth rates
- Inbound pallets driven by next month's outbound demand — requires 61 months of outbound calculations to support 60 months of inbound
- Storage balance: Beginning + Inbound − Outbound, billed at end-of-month pallet count

### Revenue Model

| Service | Rate | Basis |
|---|---|---|
| Inbound Handling | $4.50 | Per pallet |
| Outbound Picking | $0.35 | Per parcel |
| Outbound Handling | $5.00 | Per pallet |
| Storage | $6.00 | Per pallet/month |

3% annual inflation applied every January from 2027 across all revenue and cost lines.

### Labor Optimization
- Permanent staff (174 baseline) paid regardless of utilization
- Temporary staff hired only when permanent capacity is exceeded
- **Annual solver:** every January, calculates the exact integer number of new permanent hires (max 10/year) that would have minimized prior year total labor cost

### Equipment & CAPEX
- **Powered Pallet Trucks** — inbound unloading, outbound picking, outbound loading (35 initial)
- **Reach Trucks** — putaway to rack, replenishment (25 initial)
- Three-shift system: trucks required = activity FTEs divided by 3, rounded up to next integer
- Automatic purchase trigger — model never runs out of equipment

### Scenario Toggle
Single cell switch evaluates full 5-year EBITDA **with and without Tim Forward Brands** (Month 37 start, 1,500 pallets) across all outputs simultaneously.

---

## Key Results

| Metric | Result |
|---|---|
| 5-Year EBITDA — without new client | $55,621,678 |
| 5-Year EBITDA — with Tim Forward Brands | **$61,161,159** |
| EBITDA uplift | **+$5,539,481** |
| Total truck investment | $1,254,790 |
| Total temporary labor cost | $11,150,061 |
| Additional permanent staff hired (Jan 2027) | 2 |
| First additional Reach Truck purchased | May 2026 |

### Recommendation: Sign the New Client
Tim Forward Brands generates $5.5M in additional EBITDA over the 5-year projection period without major operational disruption. The new client is profitable and the model supports approval.

---

## Excel Functions Used

IF · SUMIFS · XLOOKUP · OFFSET · INDEX/MATCH · DATA TABLE · DATE Functions · MAX · ROUNDUP · AND · SUM

---

## Repository Contents

```
fmwc-value-in-transit/
├── README.md
└── 3PL_Logistics_Company_Financial_Model.xlsx
    ├── Cover
    ├── Assumptions
    ├── Financial Model (P&L summary)
    ├── Model (calculation engine)
    ├── Dashboard
    └── Model Validation (hidden)
```

---

## About This Build

This model was built as an extended practice exercise using a competition case by **Julien Lacaze** for the **Financial Modeling World Cup** — a global competition where participants build financial models under timed conditions. The originating materials included a narrative case description and the assumptions table. The model and dashboard were built from scratch. Accuracy was checked against the 20 official FMWC scored questions. My global ranking of **#172** reflects my actual FMWC competition standing.

---

*Part of the [Alicia Bruce Data & Financial Analytics Portfolio](https://www.notion.so/Data-Financial-Analytics-Portfolio-323b743fecb880c49f67d0ada9312832)*
