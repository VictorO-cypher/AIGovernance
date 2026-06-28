# 01 — Intended Purpose & System Description
## NCDC Integrated Disease Surveillance Platform — AI Module

**Document Type:** Deployer Documentation  
**System:** FMoH-AI-001  
**Version:** 1.0  
**Date:** October 2026  
**Owner:** Director General, Nigeria Centre for Disease Control (NCDC)  

---

## 1. System Identity

| Field | Detail |
|---|---|
| **System Name** | NCDC Integrated Disease Surveillance Platform — AI Outbreak Prediction Module |
| **System ID** | FMoH-AI-001 |
| **Deployer** | Nigeria Centre for Disease Control (NCDC), under the Federal Ministry of Health |
| **Technical Developer** | Africa CDC / WHO AFRO (technical support and model development) |
| **Deployment Date** | January 2022 |
| **Current Version** | v2.3 (deployed March 2025) |
| **Deployment Geography** | Nigeria — all 36 states and Federal Capital Territory |
| **Risk Classification** | High Risk (EU AI Act Annex III, Category 1 — critical infrastructure) |
| **NIST AI RMF Maturity** | 2 (Developing) — under active improvement |

---

## 2. Intended Purpose

### 2.1 Primary Purpose

The NCDC Disease Surveillance Platform AI Module is designed to **predict the probability of disease outbreaks at Local Government Area (LGA) level** across Nigeria, using historical disease case data, hospital admission records, environmental variables, and population data. Its outputs support NCDC epidemiologists in making early warning and resource deployment decisions.

The system is intended to function as a **decision-support tool** — augmenting the analytical capacity of NCDC's epidemiology teams, not replacing their professional judgement. All outbreak alerts generated on the basis of system outputs are reviewed and authorised by qualified NCDC epidemiologists before issuance.

### 2.2 Specific Use Cases

The system is authorised for the following use cases:

| Use Case | Description | Output Used For |
|---|---|---|
| Outbreak early warning | Predicting elevated disease outbreak probability at LGA level 2–4 weeks in advance | Triggering enhanced surveillance and preparedness activities |
| Resource pre-positioning | Identifying LGAs likely to require surge medical supplies or personnel | Informing logistics pre-positioning decisions |
| Priority alert generation | Flagging LGAs classified as High or Critical risk for epidemiologist review | Determining which LGAs receive active field investigation |
| Seasonal disease forecasting | Generating 12-week rolling forecasts for endemic diseases (malaria, cholera, meningitis) | Informing seasonal prevention campaigns |

### 2.3 Diseases in Scope

The current model covers the following disease categories:

- Cholera and waterborne diseases
- Cerebrospinal meningitis (CSM)
- Malaria (outbreak detection, not routine burden estimation)
- Lassa fever
- Mpox
- Measles
- Yellow fever

---

## 3. System Description

### 3.1 How the System Works

The AI module ingests weekly disease surveillance data submitted by all 36 state epidemiology teams through Nigeria's Integrated Disease Surveillance and Response (IDSR) system. This data is combined with:

- Climate and environmental data (rainfall, temperature, humidity) from the Nigeria Meteorological Agency
- Population density and movement data (LGA-level census estimates)
- Historical outbreak records from NCDC's disease registry (2010–present)
- Health facility capacity data (bed capacity, healthcare worker density by LGA)

The model generates a **risk probability score** for each LGA for each disease category on a weekly basis. Scores are classified as:

| Risk Level | Score Range | Meaning |
|---|---|---|
| Low | 0–0.30 | Routine surveillance sufficient |
| Medium | 0.31–0.60 | Enhanced monitoring recommended |
| High | 0.61–0.85 | Active investigation recommended |
| Critical | 0.86–1.00 | Immediate outbreak response recommended |

### 3.2 Model Architecture

**Model Type:** Ensemble model combining:
- Gradient Boosted Trees (XGBoost) for tabular surveillance data
- SARIMA time-series components for seasonal pattern detection
- Spatial autocorrelation features capturing disease spread between neighbouring LGAs

**Training Data Period:** 2010–2023 (13 years of NCDC surveillance records)  
**Retraining Frequency:** Annually, or following a significant outbreak event  
**Model Developer:** Africa CDC Analytics Division, with WHO AFRO technical review

### 3.3 Output Format

The system produces a weekly **Epidemiological Risk Dashboard** accessible to:
- NCDC Director General and senior epidemiologists (national level)
- State Epidemiologists (state-level view)
- NCDC Emergency Operations Centre (EOC)

Outputs are never delivered directly to the public. All public communications based on system outputs are prepared and authorised by NCDC communications staff.

---

## 4. Intended Users

| User Group | Role | Access Level |
|---|---|---|
| NCDC Epidemiologists | Primary users — review outputs and make alert decisions | Full dashboard access |
| State Epidemiologists | Review state-level risk scores | State-level view |
| NCDC Director General | Strategic oversight — reviews national risk summary | Summary dashboard |
| NCDC Emergency Operations Centre | Operational response coordination | Full dashboard access |
| FMoH eHealth Division | Governance oversight | Governance reporting view |

---

## 5. What the System Is Not Designed to Do

The following uses are **outside the intended purpose** of this system and are not authorised:

- Making autonomous outbreak declarations without epidemiologist review and authorisation
- Generating individual patient-level risk assessments
- Replacing the Integrated Disease Surveillance and Response (IDSR) reporting system
- Providing public-facing outbreak predictions or risk scores
- Informing clinical treatment decisions for individual patients
- Predicting non-communicable disease burden

Any use of the system outside these parameters must be approved in advance by the AI Review Committee.

---

## 6. Known Limitations

The following limitations are documented and must be communicated to all users:

| Limitation | Description | Mitigation |
|---|---|---|
| Rural data quality | LGAs with low IDSR reporting compliance produce less reliable predictions | Dashboard flags LGAs with <70% reporting compliance |
| Novel pathogen performance | The model is trained on known disease patterns and will not reliably predict outbreaks of novel pathogens | Epidemiologists trained to treat novel pathogen signals as requiring independent assessment |
| Lag in environmental data | Climate data has a 1–2 week processing lag, reducing real-time accuracy | Epidemiologists briefed on data lag in system training |
| Model explainability | The ensemble model does not produce feature-level explanations for individual LGA predictions | Explainability enhancement planned for v3.0 |
| Cross-border disease spread | The model does not integrate disease surveillance data from neighbouring countries | Epidemiologists instructed to supplement with WHO AFRO regional data for border LGAs |

---

*Document Version 1.0 — October 2026*  
*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*

