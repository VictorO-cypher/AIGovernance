# 06 — Performance Monitoring
## NCDC Integrated Disease Surveillance Platform — AI Module

**Document Type:** Deployer Documentation  
**System:** FMoH-AI-001  
**Version:** 1.0  
**Date:** October 2026  
**Framework:** EU AI Act Articles 15 & 17 | NIST AI RMF Measure 2.5 & Manage 4.2  

---

## 1. Performance Monitoring Purpose

Post-deployment performance monitoring ensures that the AI module continues to perform as intended throughout its operational lifetime. It detects model drift, identifies bias against specific populations or geographies, and provides the evidence base for decisions about model retraining, scope changes, or suspension.

Monitoring is the operational complement to the pre-deployment bias evaluation — it answers the question not just "does the model work?" but "does it continue to work, for whom, and under what conditions?"

---

## 2. Performance Metrics

### 2.1 Primary Accuracy Metrics

Performance is assessed by comparing AI risk classifications to outbreak outcomes confirmed through conventional surveillance and laboratory confirmation.

| Metric | Definition | Target | Review Frequency |
|---|---|---|---|
| Sensitivity (Recall) | % of confirmed outbreaks that were preceded by a High/Critical AI classification in the 2–4 weeks before confirmation | ≥75% | Quarterly |
| Specificity | % of non-outbreak LGA-weeks correctly classified as Low/Medium | ≥80% | Quarterly |
| False Negative Rate | % of confirmed outbreaks NOT preceded by a High/Critical classification | ≤25% | Quarterly |
| Lead Time | Average number of weeks between first High/Critical classification and outbreak confirmation | ≥2 weeks | Quarterly |
| AUC-ROC | Overall discriminatory performance of the model across all LGAs | ≥0.80 | Annually (at retraining) |

### 2.2 Equity Metrics

Performance is assessed separately for population subgroups to detect differential performance:

| Metric | Disaggregation | Target | Review Frequency |
|---|---|---|---|
| Sensitivity by geopolitical zone | Northwest, Northeast, North-Central, Southwest, Southeast, South-South | No zone >10pp below national average | Quarterly |
| Sensitivity by urbanicity | Urban LGAs vs rural LGAs | Rural sensitivity ≥ urban sensitivity − 10pp | Quarterly |
| Sensitivity by reporting compliance tier | High compliance LGAs (>80%) vs low compliance (<70%) | Documented and monitored | Quarterly |
| False negative rate by disease category | Per disease in scope | No category >15pp above national average | Quarterly |

### 2.3 Operational Metrics

| Metric | Definition | Target | Review Frequency |
|---|---|---|---|
| Model run completion | % of weekly model runs completed on schedule | ≥99% | Monthly |
| Data ingestion completeness | % of expected data feeds successfully ingested each week | ≥95% | Weekly (automated) |
| Review timeliness | % of weekly reviews completed within 48 hours of model run | ≥95% | Quarterly |
| Override rate | % of High/Critical classifications overridden by epidemiologists | Monitored — no fixed target; high override rate triggers review | Quarterly |

---

## 3. Performance Review Process

### 3.1 Weekly Automated Monitoring

The system generates an automated weekly performance digest that reports:

- Data ingestion completeness for the week
- Number of LGAs flagged High/Critical
- Number of LGAs with low-confidence flags
- Any system errors or failed model runs

The digest is sent automatically to the AI Governance Lead and the NCDC Epidemiology team lead every Monday.

### 3.2 Quarterly Performance Review

The AI Review Committee conducts a formal quarterly performance review. The AI Governance Lead prepares a **Quarterly Performance Report** covering:

- Primary accuracy metrics vs targets for the quarter
- Equity metrics — performance by zone, urbanicity, and compliance tier
- Override rate analysis — patterns in epidemiologist override decisions
- Alert outcome reconciliation — outbreaks confirmed vs AI predictions
- Operational metrics
- Open risk items status update
- Any incidents or near-misses in the quarter

The Quarterly Performance Report is presented to the AI Review Committee and filed in the FMoH AI Systems Register.

### 3.3 Annual Model Review and Retraining

An annual model review is conducted each January, coinciding with the post-rainy-season surveillance analysis. The review includes:

- Full AUC-ROC assessment on the prior year's data
- Comparison of model predictions to confirmed outbreak outcomes for the full year
- Bias evaluation across demographic and geographic subgroups
- Assessment of any significant epidemiological changes (new pathogens, demographic shifts, health system changes) that may require model updates
- Decision on whether model retraining is required

Model retraining is mandatory if:
- AUC-ROC falls below 0.78
- Any geopolitical zone sensitivity falls more than 15 percentage points below the national average
- A new disease category is added to the system's scope

---

## 4. Performance Thresholds and Escalation

The following thresholds trigger automatic escalation to the AI Review Committee:

| Trigger | Threshold | Action |
|---|---|---|
| Sensitivity below target | Quarterly sensitivity <70% nationally | Immediate AI Review Committee notification; technical review within 14 days |
| Zonal equity breach | Any zone sensitivity >15pp below national | Technical review and retraining assessment within 30 days |
| High override rate | >30% of High/Critical classifications overridden in a quarter | Technical review — potential model performance issue |
| False negative incident | Confirmed outbreak not preceded by any High/Medium classification | Incident report filed; root cause analysis within 30 days |
| Model run failure | >2 consecutive weekly model runs fail | Immediate technical escalation to Africa CDC; manual surveillance protocols activated |

---

## 5. Retraining Protocol

When retraining is triggered, the following protocol applies:

| Step | Action | Owner | Timeline |
|---|---|---|---|
| 1 | Retraining need confirmed by AI Review Committee | AI Review Committee | Within 14 days of trigger |
| 2 | Training data preparation — updated IDSR records and outbreak outcomes | Africa CDC Analytics | 4 weeks |
| 3 | Model retrained and internally validated | Africa CDC Analytics | 6 weeks |
| 4 | Independent bias evaluation of retrained model | Independent Evaluator | 3 weeks |
| 5 | Results presented to AI Review Committee | AI Governance Lead | 1 week |
| 6 | Deployment approved by Permanent Secretary | Permanent Secretary | 1 week |
| 7 | New model version deployed | Africa CDC / NCDC technical team | 1 week |

**Total retraining cycle: approximately 16 weeks**

During the retraining cycle, the existing model remains operational with enhanced human oversight — epidemiologists are briefed that the model is under review and instructed to apply additional caution to High/Critical classifications.

---

## 6. Continuous Improvement

Performance monitoring findings are fed back into the system's development roadmap. The following improvements are currently on the roadmap based on monitoring insights:

| Improvement | Basis | Target Version |
|---|---|---|
| Explainability module — feature-level explanations for LGA predictions | Epidemiologist feedback: difficulty interpreting predictions without explanation | v3.0 (2027) |
| Cross-border data integration — WHO AFRO regional surveillance feeds | Border LGA false negative analysis | v3.0 (2027) |
| Real-time environmental data feed — reduce climate data lag from 2 weeks to 3 days | Quarterly review: lag reduces real-time accuracy | v3.0 (2027) |
| Rural LGA confidence model — explicit uncertainty quantification for low-compliance LGAs | Equity metric analysis: rural performance gap | v3.0 (2027) |

---

*Document Version 1.0 — October 2026*  
*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
