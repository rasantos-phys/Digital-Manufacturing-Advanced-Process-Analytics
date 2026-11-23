# Pharma & Chemical Digital Manufacturing — Data Science Portfolio

> **Bridging Advanced Analytics with **GMP** Compliance, Data Integrity (**ALCOA+**), and Process Control

---

## Overview
This repository presents an industrial-grade portfolio of three data science use cases tailored for **Digital Manufacturing** in highly regulated environments (such as pharmaceutical and peptide synthesis plants). It demonstrates how to combine machine learning, multivariate statistical process control **(MSPC)**, and rigorous software validation while adhering strictly to **GMP** (Good Manufacturing Practices), **ALCOA+** data integrity principles, and **CSV** (Computerized Systems Validation).

---

## 📁 Repository Structure

├── caso1_yield_shap.py         # Batch Synthesis Yield Drop & SHAP Explainability
├── caso2_hplc_anomalia.py      # HPLC Column Degradation & PCA/Hotelling T² MSPC
├── caso3_gmp_pipeline.py       # GMP Data Pipeline, SHA-256 Immutability & OQ/PQ CSV Tests
├── requirements.txt            # Locked dependencies
└── README.md                   # Project documentation

---

## Case Studies Breakdown

## Case Study 1: Batch Yield Drop Prediction & Root-Cause Explainability
* **Objective**: Predict batch yield fluctuations in chemical synthesis and identify hidden non-linear interactions between process parameters before batch completion.

* **Methodology**:
  - Implemented XGBoost regression combined with GroupKFold cross-validation grouped strictly by batch_id to completely eliminate data leakage.
  - Applied **SHAP** (SHapley Additive exPlanations) to open the model "black box" and generate audit-ready waterfall plots for **CAPA** (Corrective and Preventive Action) investigations.

* **Key Result**: Achieved an out-of-sample **RMSE of 1.178%**, accurately flagging root causes (e.g., combined reagent moisture and temperature spikes) rather than relying on isolated univariate alarms.

## Case Study 2: HPLC Column Degradation & Anomaly Detection (MSPC)
* **Objective**: Detect early-stage degradation in expensive chromatography columns (**HPLC**) to prevent **Out-of-Specification (OOS)** product batches.

* **Methodology**:
  - Built a semi-supervised Principal **Component Analysis (PCA)** model trained exclusively on healthy reference runs (Golden Batches).
  - Monitored multivariate plant health in real-time using Hotelling’s T^2 statistical control limits derived from the F-distribution (99% confidence).

* **Key Result**: Set a control limit at **T^2 = 9.85**, achieving 0 false alarms across 100 normal batches while successfully catching early degradation trends across 15 compromised cycles weeks before failure.

## Case Study 3: GMP-Compliant Data Pipeline & Automated CSV Validation
* **Objective**: Ensure data integrity and automated software validation for predictive models deployed in a regulated manufacturing plant.

* **Methodology**:
  - Enforced **ALCOA+** principles using cryptographic **SHA-256** data hashing to prove raw historian data immutability and appending timestamped JSON-line **Audit Trails**.
  - Automated Computerized Systems Validation **(CSV)** protocols, running software qualification tests **(OQ/PQ)** directly as code.

* **Key Result**: Pipeline successfully passed automated qualification checks: {'OQ_Deterministic': True, 'OQ_Rejects_NaN': True, 'PQ_Accuracy': True} (**RMSE\< 0.25**).

---

## Tech Stack & Dependencies
* Core Language: Python 3.10+
* Data Science & ML: scikit-learn, xgboost, shap, numpy, pandas
* Statistics & Validation: scipy, joblib
* Environment: Tested on Windows (VS Code / / PowerShell)


