# 05 — Logging & Traceability
## NCDC Integrated Disease Surveillance Platform — AI Module

**Document Type:** Deployer Documentation  
**System:** FMoH-AI-001  
**Version:** 1.0  
**Date:** October 2026  
**Framework:** EU AI Act Article 12 | NIST AI RMF Manage 4.1  

---

## 1. Logging Purpose

Logging and traceability serve three functions for this system:

1. **Accountability** — creating an auditable record of what the AI predicted and what humans decided
2. **Incident investigation** — enabling reconstruction of the system's outputs and human decisions in the event of a missed or false outbreak alert
3. **Performance improvement** — providing the data needed to evaluate model accuracy and identify drift over time

---

## 2. What Is Logged

### 2.1 Model Input Logs

Every weekly model run logs the following:

| Log Field | Description | Retention |
|---|---|---|
| Run ID | Unique identifier for each weekly model run | 15 years |
| Run timestamp | Date and time of model execution | 15 years |
| Model version | Version number of the model used | 15 years |
| Input data sources | List of data feeds ingested for this run, with version/date stamps | 15 years |
| Data quality flags | LGAs and states flagged for low reporting compliance | 15 years |
| Missing data handling | Record of any substitutions made for missing environmental data | 15 years |

### 2.2 Model Output Logs

Every weekly model run logs the following outputs:

| Log Field | Description | Retention |
|---|---|---|
| LGA risk scores | Risk probability score for every LGA, for every disease category | 15 years |
| Risk classifications | Low/Medium/High/Critical classification for each LGA | 15 years |
| Score deltas | Change in risk score from previous week for each LGA | 15 years |
| High/Critical flag list | List of all LGAs classified High or Critical this week | 15 years |

### 2.3 Human Decision Logs

Every weekly epidemiologist review logs the following:

| Log Field | Description | Retention |
|---|---|---|
| Reviewer identity | Name and title of reviewing epidemiologist | 15 years |
| Review timestamp | Date and time of review completion | 15 years |
| Decision per flagged LGA | Confirmed-Act / Monitor / Override-Low Confidence | 15 years |
| Override rationale | Written rationale for any Override decisions | 15 years |
| Actions initiated | Field investigations, enhanced surveillance, or escalations triggered | 15 years |
| Time from output to review | Duration between model run completion and epidemiologist review | 5 years |

### 2.4 Alert Logs

Every outbreak alert initiated on the basis of AI module outputs logs:

| Log Field | Description | Retention |
|---|---|---|
| Alert ID | Unique identifier for each alert | 15 years |
| Authorising epidemiologist | Name of epidemiologist who confirmed the alert | 15 years |
| AI risk score at time of alert | The model's risk score that contributed to the alert decision | 15 years |
| Other evidence considered | Field reports, laboratory data, or other intelligence considered | 15 years |
| Alert outcome | Whether the outbreak was subsequently confirmed or ruled out | 15 years |

---

## 3. Traceability Chain

The logging system enables the following traceability chain for any outbreak alert or missed detection:

```
ALERT or MISSED DETECTION
        ↓
Identify Alert ID or incident date
        ↓
Retrieve Weekly Review Log for that date
        ↓
Identify epidemiologist decision and rationale
        ↓
Retrieve Model Output Log for that week
        ↓
Identify AI risk score and classification
        ↓
Retrieve Model Input Log for that week
        ↓
Identify data inputs, quality flags, and any substitutions
        ↓
Full reconstruction of AI prediction and human decision chain
```

This chain enables the AI Review Committee and any external auditor to reconstruct exactly what the model predicted, what data it used, and what the epidemiologist decided — for any week in the system's operational history.

---

## 4. Log Storage and Access

| Parameter | Detail |
|---|---|
| Storage location | NCDC secure server infrastructure (Lagos data centre) |
| Backup | Weekly backup to FMoH offsite storage |
| Access | AI Governance Lead, NCDC Director General, AI Review Committee, authorised auditors |
| Tamper protection | Logs are write-once; no modification permitted after creation |
| Encryption | AES-256 encryption at rest and in transit |

---

## 5. Log Review

| Review | Frequency | Reviewer |
|---|---|---|
| Override Register review | Quarterly | AI Review Committee |
| Alert outcome reconciliation | Quarterly | AI Governance Lead + NCDC Epidemiology team |
| Log completeness audit | Annual | AI Governance Lead |
| Full log audit | On incident or AI Review Committee request | Independent auditor |

---

*Document Version 1.0 — October 2026*  
*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
