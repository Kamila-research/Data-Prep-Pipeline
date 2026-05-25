# Data Engineering Pipeline: Pre-Processing for Causal Inference

## 📌 Project Overview
This repository details the end-to-end data engineering and pre-processing pipeline designed to prepare observational site data for advanced econometric modelling. The pipeline transitions raw, unformatted records into a highly structured, statistically sound format optimised for a **Regression Discontinuity (RD) design** and **Spatial Autocorrelation analysis**.

By separating data hygiene from downstream statistical modelling, this framework ensures reproducible research boundaries and maintains data integrity.

---

## 🏗️ The 3-Stage Data Preparation Pipeline

### 🟢 Stage 1: Ingestion & Baseline Data Hygiene
* **Objective:** Standardize incoming dirty data and fix systemic structural inconsistencies.
* **Core Operations:**
  * Handled missing data matrices and standardized data types across columns.
  * Unified naming conventions across fragmented historical data files.
  * *Associated Architecture:* `clean_data_all sites.R`

### 🟡 Stage 2: Subsetting & Operational Logic
* **Objective:** Isolate the precise target population and remove background noise.
* **Core Operations:**
  * Applied strict operational rules to filter out inactive elements, isolating "active" sites.
  * Maintained external project metadata documentation to ensure team-wide alignment on filtering parameters.
  * *Associated Architecture:* `clean_data_active_sites.R`, `We keep only active sites.txt`

### 🔴 Stage 3: Feature Engineering for Econometric Modeling
* **Objective:** Construct the strict mathematical variables required for causal inference models.
* **Core Operations:**
  * Engineered the **"running variable"** required for the Regression Discontinuity framework.
  * Normalized and centered the assignment variable relative to the specific treatment cutoff.
  * Generated treatment assignment indicators and prepared cluster-robust data structures.
  * *Associated Architecture:* `1 RD data preparation.R`, `for statistics analysis data prep.R`

---

## 🛠️ Data Pipeline Summary

| Stage | Process Component | Primary Transformation | Goal |
| :--- | :--- | :--- | :--- |
| **01** | `Standardization` | Data profiling & type-casting | Establish clean baseline |
| **02** | `Subsetting` | Categorical filtering based on site activity | Eliminate population noise |
| **03** | `Feature Engineering` | Variable centering & threshold flags | Optimize for RD modeling |

---
*Note: Raw datasets are excluded from this repository to maintain data privacy and comply with proprietary information guidelines.*
