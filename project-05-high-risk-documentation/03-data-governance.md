# 03 — Data Governance
## NCDC Integrated Disease Surveillance Platform — AI Module

**Document Type:** Provider + Deployer Documentation  
**System:** FMoH-AI-001  
**Version:** 1.0  
**Date:** October 2026  
**Framework:** EU AI Act Article 10 | Nigeria Data Protection Act 2023  

---

## 1. Data Governance Principles

FMoH and NCDC apply the following principles to all data used in the Disease Surveillance Platform AI Module:

- **Minimisation:** Only data necessary for outbreak prediction is collected and processed
- **Purpose limitation:** Data collected for disease surveillance is used only for that purpose
- **Quality:** Data quality is monitored and deficiencies are flagged to system users
- **Accountability:** A named Data Controller is responsible for all data processing associated with this system
- **Legal basis:** All data processing has a documented lawful basis under the Nigeria Data Protection Act 2023

---

## 2. Data Inputs

### 2.1 Primary Surveillance Data

| Data Source | Description | Frequency | Legal Basis |
|---|---|---|---|
| IDSR Weekly Reports | Disease case counts by LGA, submitted by state epidemiology teams | Weekly | Public health mandate — NCDC Act 2017 |
| Hospital Admission Records | Aggregate (not individual) admission data by disease category from sentinel hospitals | Weekly | Public health mandate — FMoH statutory function |
| NCDC Disease Registry | Historical outbreak records 2010–present, aggregated at LGA level | Static (updated annually) | Public health mandate |
| Laboratory Confirmation Data | Confirmed disease cases from NCDC Reference Laboratory and state labs | Weekly | Public health mandate |

**Personal data:** Primary surveillance data is processed at **aggregate LGA level**. No individual patient identifiers are used as model inputs. Individual-level data collected through IDSR is aggregated before ingestion into the AI module.

### 2.2 Environmental and Contextual Data

| Data Source | Description | Frequency | Legal Basis |
|---|---|---|---|
| Nigeria Meteorological Agency | Rainfall, temperature, humidity by LGA | Weekly | Data sharing agreement (ref: NiMet-NCDC-2021-001) |
| NPC Population Data | LGA-level population estimates and density | Annual | Public domain — National Population Commission |
| Health Facility Capacity Data | Bed capacity and healthcare worker density by LGA | Annual | FMoH health facility registry |

---

## 3. Training Data

### 3.1 Training Dataset Composition

| Component | Description | Coverage |
|---|---|---|
| Historical IDSR records | Weekly disease case reports 2010–2023 | All 36 states + FCT; 774 LGAs |
| Historical outbreak records | Confirmed outbreak events from NCDC registry | 2010–2023; all disease categories in scope |
| Environmental data | Historical climate data matched to IDSR records | 2010–2023 |
| Population data | Census estimates 2006 and 2023 projections | All LGAs |

**Training data period:** 2010–2023 (13 years)  
**Total training records:** Approximately 5.2 million LGA-week observations across all disease categories

### 3.2 Known Training Data Limitations

| Limitation | Description | Impact |
|---|---|---|
| Pre-2015 data quality | IDSR reporting compliance was significantly lower before 2015 — pre-2015 records are less complete | Model may underweight patterns from the 2010–2014 period |
| Rural LGA underrepresentation | LGAs with chronically low reporting compliance contribute fewer training observations | Model may underperform in low-compliance LGAs at inference time |
| Novel pathogen gap | Training data does not include data for pathogens that emerged after 2023 | Model will not reliably detect novel pathogen outbreaks |

### 3.3 Training Data Bias Assessment

A bias evaluation was conducted by Africa CDC Analytics Division prior to model v2.0 deployment (2023). Key findings:

- Model performance (AUC-ROC) was **0.84** nationally
- Performance by geopolitical zone ranged from **0.81** (Northwest) to **0.87** (Southwest)
- The Northwest performance gap was attributed to lower average IDSR reporting compliance in Northwest states
- No systematic bias by disease category was identified
- **Recommendation:** Improved IDSR reporting in Northwest states would reduce the performance gap

A follow-up bias evaluation is scheduled for v3.0 (2027).

---

## 4. Data Quality Management

### 4.1 Automated Data Quality Checks

The system performs the following automated checks on each weekly data ingestion:

| Check | Threshold | Action if Failed |
|---|---|---|
| Reporting completeness — state level | <80% of expected LGA reports received | State flagged in dashboard; epidemiologist alerted |
| Reporting completeness — LGA level | <70% weekly completeness over rolling 4 weeks | LGA risk score flagged as low-confidence in dashboard |
| Anomalous data values | Case counts >3 standard deviations from historical baseline | Flagged for epidemiologist review before model ingestion |
| Missing environmental data | Any missing climate variable for current week | Previous week's value substituted; flag displayed |

### 4.2 Data Quality Reporting

A weekly **Data Quality Summary** is generated alongside the risk dashboard. It reports:

- Number of LGAs with low-confidence risk scores (due to reporting gaps)
- States with reporting completeness below threshold
- Any data anomalies identified and how they were handled
- Environmental data completeness

---

## 5. Data Protection Compliance

### 5.1 Personal Data Assessment

The AI module processes **aggregate, non-identifiable data** at LGA level. Individual patient records are not used as model inputs. On this basis, the AI module itself does not process personal data as defined under the Nigeria Data Protection Act 2023.

However, the underlying IDSR system from which aggregate data is drawn does process personal data (individual case reports). The following controls apply to that upstream processing:

| Control | Description |
|---|---|
| Aggregation before AI ingestion | Individual case records are aggregated at LGA level before transfer to the AI module |
| Access controls | Individual-level IDSR data is accessible only to authorised state and national epidemiology staff |
| Data retention | Individual case records are retained for 10 years per NCDC records management policy |
| Lawful basis | Individual case reporting is mandatory under Nigeria's Infectious Disease (Notification) Act |

### 5.2 Data Sharing

Aggregate AI module outputs (risk scores and forecasts) are shared with:

- State Epidemiologists (state-level data only)
- WHO AFRO (aggregate national summary, under WHO-NCDC data sharing agreement)
- Africa CDC (aggregate national summary, under Africa CDC-NCDC data sharing agreement)

No individual-level data is shared with external parties. All data sharing agreements are reviewed annually by FMoH Legal.

---

## 6. Data Retention

| Data Type | Retention Period | Basis |
|---|---|---|
| Weekly AI module inputs (aggregated) | 15 years | NCDC records management policy |
| AI module risk score outputs | 15 years | Public health accountability |
| Model training datasets | Duration of model use + 5 years | Audit and retraining requirements |
| Data quality logs | 5 years | Governance and audit |

---

*Document Version 1.0 — October 2026*  
*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
