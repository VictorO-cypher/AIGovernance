# 02 — Risk Management Summary
## NCDC Integrated Disease Surveillance Platform — AI Module

**Document Type:** Deployer Documentation  
**System:** FMoH-AI-001  
**Version:** 1.0  
**Date:** October 2026  
**Framework:** EU AI Act Article 9 | NIST AI RMF Map and Measure Functions  

---

## 1. Risk Management Approach

FMoH and NCDC apply a structured risk management approach to the Disease Surveillance Platform AI Module throughout its operational lifecycle. This approach is aligned with EU AI Act Article 9 obligations and the NIST AI RMF Map and Measure functions.

Risk management for this system is **continuous** — not a point-in-time compliance exercise. Risks are identified, assessed, mitigated, and monitored on an ongoing basis, with formal review at each quarterly AI Review Committee meeting.

---

## 2. Risk Identification Scope

Risks are assessed across four categories:

| Category | Description |
|---|---|
| **Technical** | Risks arising from model performance, data quality, or system failures |
| **Public Health** | Risks of harm to Nigeria's disease surveillance and outbreak response capacity |
| **Governance** | Risks arising from accountability gaps, process failures, or misuse |
| **Data and Privacy** | Risks arising from data processing, sharing, or retention practices |

---

## 3. Risk Register Summary

### Risk 01 — False Negative Outbreak Prediction (Missed Outbreak)

**Description:** The model fails to classify an LGA as High or Critical risk during the early stages of a genuine outbreak, delaying NCDC's detection and response.

| Assessment | Detail |
|---|---|
| Likelihood | 3 — Possible. The model has demonstrated strong performance on historical outbreaks but data quality gaps in rural LGAs reduce reliability in those areas. |
| Impact | 5 — Catastrophic. A missed early warning for a cholera or meningitis outbreak could result in hundreds of preventable deaths before the outbreak is detected through conventional surveillance. |
| **Inherent Risk** | **15 — High** |
| Mitigations | Mandatory epidemiologist review supplements model outputs; IDSR conventional surveillance continues in parallel; LGAs with low reporting compliance are flagged |
| **Residual Risk** | **9 — Low** |

---

### Risk 02 — False Positive Outbreak Prediction (Unnecessary Alert)

**Description:** The model classifies an LGA as High or Critical risk when no genuine outbreak threat exists, triggering unnecessary resource deployment and potentially causing public alarm.

| Assessment | Detail |
|---|---|
| Likelihood | 3 — Possible. Environmental data lag and seasonal anomalies can produce false elevation of risk scores. |
| Impact | 3 — Moderate. Unnecessary resource deployment is costly; false alarms repeated over time erode trust in the surveillance system. |
| **Inherent Risk** | **9 — Low** |
| Mitigations | Epidemiologist authorisation required before any alert is issued; two-week confirmation window for Medium risk classifications before escalation |
| **Residual Risk** | **4 — Negligible** |

---

### Risk 03 — Rural LGA Data Quality Bias

**Description:** LGAs with chronically low IDSR reporting compliance produce systematically unreliable risk scores. These are often the most underserved LGAs — where outbreak risk is highest and surveillance capacity is weakest. The model may underestimate risk in exactly the areas that most need early warning.

| Assessment | Detail |
|---|---|
| Likelihood | 4 — Likely. Data quality gaps in rural LGAs are a documented, persistent structural issue in Nigeria's health information system. |
| Impact | 4 — Major. Systematic underestimation of risk in high-vulnerability, low-resource LGAs is a health equity failure with potentially severe consequences. |
| **Inherent Risk** | **16 — High** |
| Mitigations | Dashboard flags all LGAs with <70% reporting compliance; epidemiologists instructed to treat low-compliance LGA scores with additional caution; NCDC field teams conduct manual surveillance in chronically low-compliance LGAs |
| **Residual Risk** | **8 — Low** |

---

### Risk 04 — Model Drift

**Description:** The model's predictive accuracy degrades over time as disease patterns, environmental conditions, or population dynamics shift in ways not captured by the training data.

| Assessment | Detail |
|---|---|
| Likelihood | 3 — Possible. Annual retraining mitigates but does not eliminate drift risk, particularly for novel or re-emerging pathogens. |
| Impact | 4 — Major. Undetected model drift could produce systematically unreliable predictions without epidemiologists being aware. |
| **Inherent Risk** | **12 — Medium** |
| Mitigations | Annual model retraining; quarterly performance review against historical outbreak records; epidemiologists trained to report anomalous prediction patterns |
| **Residual Risk** | **6 — Low** |

---

### Risk 05 — Unauthorised or Misuse of Outputs

**Description:** System outputs are shared beyond authorised users, or used for purposes outside the system's intended purpose — for example, public communication of raw risk scores without epidemiologist interpretation.

| Assessment | Detail |
|---|---|
| Likelihood | 2 — Unlikely. Access controls limit dashboard access to authorised users. |
| Impact | 4 — Major. Uninterpreted public release of outbreak risk scores could cause public panic or undermine trust in NCDC. |
| **Inherent Risk** | **8 — Low** |
| Mitigations | Role-based access controls; all public communications must be authorised by NCDC communications staff; policy prohibition on unauthorised sharing |
| **Residual Risk** | **4 — Negligible** |

---

## 4. Residual Risk Summary

| Risk | Inherent Rating | Residual Rating | Residual Level |
|---|---|---|---|
| R01 — False Negative (Missed Outbreak) | 15 — High | 9 | Low |
| R02 — False Positive (Unnecessary Alert) | 9 — Low | 4 | Negligible |
| R03 — Rural LGA Data Quality Bias | 16 — High | 8 | Low |
| R04 — Model Drift | 12 — Medium | 6 | Low |
| R05 — Unauthorised Output Use | 8 — Low | 4 | Negligible |

**Overall Residual Risk Position: LOW**  
Subject to continued implementation of mitigations and quarterly monitoring.

---

## 5. Open Risk Items

The following risk items remain open and are under active management:

| Item | Description | Owner | Target |
|---|---|---|---|
| Explainability enhancement | Model does not produce feature-level explanations — epidemiologists cannot interrogate prediction logic | Africa CDC / NCDC | v3.0 release (2027) |
| Cross-border data integration | Model does not incorporate disease data from neighbouring countries for border LGAs | NCDC / WHO AFRO | 2027 roadmap |
| Rural IDSR reporting improvement | Root cause of data quality bias — requires structural improvement in LGA reporting capacity | NHMIS / State PHCDAs | Ongoing |

---

*Document Version 1.0 — October 2026*  
*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*

