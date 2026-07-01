# Understanding Condition Monitoring
### HPCL Internship · Visakh Refinery, Visakhapatnam

An integrated project linking **predictive equipment-failure models** to **spare-parts inventory and procurement decisions** for critical rotary equipment at HPCL's Visakh Refinery. Goal: use degradation forecasts to time procurement, cut holding cost, and reduce emergency expediting — validated on a **simulated operational quarter**.

> **Duration:** [May 2026 – July 2026]
> **Division:** [Maintenance & Reliability / Supply-Distribution — Maintenance]
> **Nature:** Simulation / proof-of-concept (not deployed to production)

---

## Problem
Maintenance procurement was reactive: emergency part expediting and either overstocked or unavailable spares for high-value rotary equipment. Driven by HPCL’s digital transformation goals to reduce overall maintenance costs by detecting equipment anomalies before catastrophic failure.

## Approach
End-to-end pipeline:

1. **Failure prediction** — built predictive failure models for critical mechanical components using equipment health index, sensor data and historical failure records with XGBoost algorithms.
2. **Degradation forecasting** — forecasted component lifecycle degradation to anticipate replacement timing by XGBoost.
3. **Inventory linkage** — aligned model outputs with spare-parts inventory data and vendor lead times.
4. **Reorder optimization** — optimized reorder points for high-value spares and designed **just-in-time (JIT) procurement** timed to predicted degradation.

## Results *(simulated over one operational quarter)*
- **~17.5% lower holding cost** on critical mechanical components via JIT procurement aligned to predicted failures.
- **~24% fewer emergency part-expediting incidents** from degradation-based procurement timing.
- **[Availability metric — VERIFY: see note below]** for high-value rotary equipment spares during planned turnarounds, by cross-referencing equipment health indices with vendor lead times.

> All figures are from a simulated scenario, not live operations. Baselines and assumptions are documented in [`/results`].

---

## Tech Stack
- **Language:** Python [3.x]
- **Data:** pandas, numpy
- **Modeling:** scikit-learn 
- **Forecasting:** XGBoost
- **Visualization:** matplotlib, seaborn
- **Other:** Excel, Power BI, SAP export

## Repository Structure
```
.
├── data/            # synthetic / anonymized only — no confidential HPCL data
├── notebooks/       # failure modeling, degradation forecast, inventory optimization
├── src/
├── results/         # metrics, baselines, assumptions
└── README.md
```

## Running
```bash
git clone https://github.com/KilkankB/HPCL--Understanding-Condition-Monitoring.git
cd HPCL--Understanding-Condition-Monitoring
pip install -r requirements.txt
```

---

## Key Learnings
- Gained hands-on expertise in processing real-time sensor data and deploying predictive analytics to detect early-stage equipment degradation.
- Developed a deep understanding of rotating equipment failure modes and their critical impact on refinery throughput, safety, and turnaround schedules.

## Note on Data
HPCL operational data is confidential. This repository uses available data only. No proprietary data is published.
