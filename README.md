# ESCAPE-35-SUPPLEMENTARY MATERIAL: dLCA of Lovastatin Production (KTB1 model)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](http://www.gnu.org/licenses/gpl-3.0)

**Author**: ADA ROBINSON  
**Date**: 2025-01-05  
**Environment**: `pharma`  
**Software & Library Versions**  
- Brightway25 version 1.0.6  
- bw2io version 0.9.4  
- Numpy version 1.24.4  
- Python version 3.11.11  

**Data Sources**:  
- [Ecoinvent v3.10 cut-off system](https://ecoinvent.org/)  
- [KTB1 model - DTU](https://github.com/Boskabadi/KTB1-DLCA)  
- [ENTSO-E](https://transparency.entsoe.eu/)

---

## Project Overview

> **What**  
> This repository provides **supplementary materials** for a dynamic Life Cycle Assessment (dLCA) study on **continuous lovastatin production** (KTB1 model) capturing hourly electricity demand and **time‐varying** environmental impacts over a 24‐hour period.
> **Libraries & Databases**  
>    - Uses Brightway2.5 with ecoinvent 3.10 for background activities.
> **CSV Files**:  
>    - `DI_Integer_TimeSeries1.xlsx`, `DI_Integer_TimeSeries2.xlsx`:  
>      - **Hourly Electricity Demand** for KTB1 (CSTR, Hydrocyclone, Centrifuge, Pump).  
>    - `Actual Generation per Production Type_20240808.csv`, `Actual Generation per Production Type_20250114.csv`:  
>      - **Hourly Electricity Production Shares** for Denmark in **Summer (2024-08-08)** and **Winter (2025-01-14)**.  
> **(Intended Outcome)**  
> This setup contains the supplementary material to **quantify** how fluctuations in both **process demand** and **electricity generation mix** affect the overall environmental impact in lovastatin production. By dynamically coupling foreground loads with a real‐time background grid mix, we capture **time‐varying** emissions and more accurate impact assessments than a single‐average approac

---

## Scenarios

We examine **four scenarios** that combine two **foreground modifications** with two **seasonal backgrounds**:

1. **Case 1**: Reactor volume **5000 L → 4900 L** at hour 0  
2. **Case 2**: Feed carbon **20 g/L → 16 g/L** at hour 0  
3. **Winter**: Danish electricity mix on **2025‐01‐14** (from `Actual Generation per Production Type_20250114.csv`)  
4. **Summer**: Danish electricity mix on **2024‐08‐08** (from `Actual Generation per Production Type_20240808.csv`)

This yields:  
- **S1** = Case 1 + Winter  
- **S2** = Case 1 + Summer  
- **S3** = Case 2 + Winter  
- **S4** = Case 2 + Summer  

Each scenario captures **24 hours** of operation, ensuring alignment between **foreground demand** (KTB1) and the **hourly grid mix**.  

---

## Results Files

After running the LCA, the following CSV files are produced, showing both **fully dynamic** and **average** variants:

- `dLCA_results_S1.csv` and `dLCA_results_S1_avg.csv`  
- `dLCA_results_S2.csv` and `dLCA_results_S2_avg.csv`  
- `dLCA_results_S3.csv` and `dLCA_results_S3_avg.csv`  
- `dLCA_results_S4.csv` and `dLCA_results_S4_avg.csv`

These CSVs contain **hourly ReCiPe endpoint scores** for each scenario, comparing:
1. **Fully Dynamic**: Hourly foreground × hourly background  
2. **Dynamic background + average foreground**  
3. **Single-Average** (both foreground and background)

---

**For more details on the methodology, model assumptions, and how to replicate or extend these calculations, please refer to the associated article**
[![Status: Coming Soon](https://img.shields.io/badge/Status-Coming%20Soon-yellow.svg)](#)
