# 04 — Human Oversight
## NCDC Integrated Disease Surveillance Platform — AI Module

**Document Type:** Deployer Documentation  
**System:** FMoH-AI-001  
**Version:** 1.0  
**Date:** October 2026  
**Framework:** EU AI Act Article 14 | NIST AI RMF Govern 6.1  

---

## 1. Human Oversight Principle

The NCDC Disease Surveillance Platform AI Module is a **decision-support tool**. It does not issue outbreak alerts autonomously. Every alert issued by NCDC that is informed by the AI module requires authorisation by a qualified NCDC epidemiologist.

This is not a nominal oversight requirement — it is a substantive, documented process in which epidemiologists are trained, empowered, and expected to exercise independent professional judgement before acting on AI outputs.

---

## 2. Oversight Structure

### 2.1 Roles and Responsibilities

| Role | Oversight Responsibility |
|---|---|
| **NCDC National Epidemiologist (on duty)** | Primary reviewer of weekly AI risk dashboard; authorises or declines to act on High/Critical risk classifications |
| **NCDC State Epidemiologist** | Reviews state-level risk scores; initiates field investigation requests for their state |
| **NCDC Emergency Operations Centre (EOC) Director** | Authorises outbreak alerts with national or multi-state implications |
| **NCDC Director General** | Final authority for national outbreak declarations |
| **AI System Owner (Director General, NCDC)** | Accountable for ensuring oversight protocols are followed |

### 2.2 Oversight Hierarchy

```
AI Module generates weekly risk scores
            ↓
National Epidemiologist reviews dashboard
            ↓
    ┌───────────────────────────┐
    │                           │
Low/Medium Risk           High/Critical Risk
    │                           │
Routine monitoring        Epidemiologist Assessment
                                │
                    ┌───────────────────────┐
                    │                       │
              Plausible signal        Implausible / data
              (consistent with        quality concern
              field reports,          (inconsistent with
              seasonality,            field reports or
              regional context)       known data gap)
                    │                       │
            Initiate enhanced          Flag as low-confidence
            surveillance /             Monitor only
            field investigation
                    │
            EOC Director review
            (for multi-state or
            high-severity events)
                    │
            Outbreak alert issued
            (if confirmed)
```

---

## 3. Review Protocol

### 3.1 Weekly Dashboard Review

Every Monday, the NCDC National Epidemiologist on duty conducts a structured review of the weekly AI risk dashboard. The review follows a documented protocol:

**Step 1 — Data Quality Check**  
Review the weekly Data Quality Summary. Identify any LGAs with low-confidence risk scores due to reporting gaps. Note any states with reporting compliance below threshold.

**Step 2 — Risk Score Review**  
Review all LGAs classified as High or Critical risk. For each:
- Compare the risk score to the previous week's score (trend assessment)
- Compare to the same period in previous years (seasonal baseline check)
- Cross-reference with any field reports or informal signals received from state teams
- Assess whether the classification is consistent with known epidemiological context

**Step 3 — Classification Decision**  
For each High or Critical LGA, the epidemiologist makes one of three decisions:

| Decision | Meaning | Action |
|---|---|---|
| **Confirmed — Act** | Risk score is plausible and consistent with available evidence | Initiate enhanced surveillance or field investigation |
| **Monitor** | Risk score is elevated but inconsistent or uncertain — requires watching | Increase passive surveillance; review again next week |
| **Override — Low Confidence** | Risk score is assessed as unreliable due to data quality concerns | Flag in dashboard; document rationale; no escalation |

All decisions are documented in the weekly Review Log (see Section 5).

**Step 4 — Escalation (if required)**  
If a High or Critical classification is confirmed and the epidemiologist assesses it as requiring multi-state or emergency response coordination, the EOC Director is notified immediately.

---

## 4. Epidemiologist Authority to Override

NCDC epidemiologists have **full authority** to:

- Decline to act on any AI risk classification
- Override a Low or Medium classification if field intelligence suggests a genuine emerging threat not captured by the model
- Suspend use of the AI module for a specific disease category or geography if they assess the outputs as unreliable
- Request an unscheduled model review from the AI Governance Lead

Epidemiologists are **never required** to justify a decision not to act on an AI output. The model is a tool. Professional epidemiological judgement is the authority.

---

## 5. Documentation Requirements

### 5.1 Weekly Review Log

The National Epidemiologist documents the following for each weekly review:

| Field | Content |
|---|---|
| Review date | Date of review |
| Reviewer name and title | Epidemiologist conducting the review |
| LGAs classified High/Critical | List of all High/Critical LGAs this week |
| Decision for each LGA | Confirmed-Act / Monitor / Override-Low Confidence |
| Rationale for overrides | Brief explanation for any override decisions |
| Actions initiated | Field investigations, enhanced surveillance, or escalations triggered |
| Data quality flags | Any LGAs where low-confidence flags affected the review |

Weekly Review Logs are retained for 5 years and are available for AI Review Committee inspection.

### 5.2 Override Register

All Override — Low Confidence decisions are recorded in a dedicated Override Register, which is reviewed quarterly by the AI Review Committee. High override rates for specific LGAs, states, or disease categories are a signal of potential model performance issues and trigger a technical review.

---

## 6. Epidemiologist Training Requirements

All NCDC epidemiologists with access to the AI dashboard must complete the following before being granted access:

| Training Module | Content | Duration | Frequency |
|---|---|---|---|
| AI Surveillance Tool Induction | System purpose, capabilities, and limitations; how the model works; known limitations including data quality bias | 3 hours | Once on onboarding |
| Interpreting AI Risk Scores | Practical exercises in reviewing dashboard outputs; identifying low-confidence signals; cross-referencing with field data | 2 hours | Annually |
| Override and Escalation Protocols | When and how to override; escalation thresholds; documentation requirements | 1 hour | Annually |

Training completion is tracked by the NCDC Human Resources Division and reported to the AI System Owner.

---

## 7. Safeguards Against Over-Reliance

The following design features are implemented specifically to prevent epidemiologists from over-relying on AI outputs:

| Safeguard | Description |
|---|---|
| Mandatory data quality summary | Displayed prominently on dashboard — epidemiologists see data quality issues before risk scores |
| Low-confidence flags on risk scores | LGAs with <70% reporting compliance are flagged — score displayed with explicit uncertainty caveat |
| No automated alerts | The system cannot send alerts to state teams without epidemiologist initiation — alerts require active human action |
| Weekly training nudge | Dashboard displays a rotating reminder of one known system limitation at the top of each weekly review |
| Parallel conventional surveillance | IDSR conventional surveillance continues independently — AI outputs are never the sole source of outbreak intelligence |

---

*Document Version 1.0 — October 2026*  
*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
