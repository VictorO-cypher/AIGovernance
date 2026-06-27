# NIST AI RMF Mapping — Federal Ministry of Health, Nigeria

**Framework Reference:** NIST AI Risk Management Framework (AI RMF 1.0)  
**Mapping Date:** June 2026  
**Prepared by:** Victor Eze Odoh, AI Governance Researcher  

---

## Purpose

This document maps each AI system in the Federal Ministry of Health (FMoH) inventory against the four core functions of the NIST AI Risk Management Framework. It identifies which governance practices are in place, which are absent, and where the most significant gaps exist.

### The Four Functions

| Function | Core Question |
|---|---|
| **GOVERN** | Are the right accountability structures, policies, and culture in place? |
| **MAP** | Have we identified and contextualised the risks associated with this system? |
| **MEASURE** | Have we analysed and assessed those risks in a rigorous, documented way? |
| **MANAGE** | Are we actively treating risks, monitoring systems, and ready to respond? |

### Maturity Scale

| Level | Description |
|---|---|
| 0 | Absent — no practices in place |
| 1 | Initial — ad hoc or absent |
| 2 | Developing — some practices exist but inconsistently applied |
| 3 | Defined — documented and repeatable processes in place |
| 4 | Optimised — continuously improved with feedback loops |

---

## System Mappings

---

### FMoH-AI-001 · NCDC Disease Surveillance Platform (High Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| **GOVERN** | Named owner exists (Director General, NCDC). System operates under NCDC's general mandate but no AI-specific governance policy references this system. | No AI governance charter. No formal escalation path for model risk decisions. No Board-level accountability for AI-driven outbreak alerts. | 2 |
| **MAP** | Risk context understood informally by NCDC epidemiology team. System purpose and data flows are operationally documented. | No formal AI risk mapping document. Affected population not documented with demographic or geographic breakdown. Rural LGA data quality risk not formally assessed. | 2 |
| **MEASURE** | Outbreak predictions reviewed by epidemiologists before alerts issued. No formal performance benchmarks or accuracy thresholds defined. | No structured bias evaluation — rural LGA predictions not independently validated. No model drift detection. No defined performance degradation thresholds. | 1 |
| **MANAGE** | Human review before alert issuance provides a baseline control. | No formal incident response procedure for false alerts or model failures. No model monitoring framework. No defined response if model drift detected. | 1 |

**Overall Maturity: 1.5 (Developing)**  
**Priority Actions:** Define formal performance benchmarks; conduct independent validation of rural LGA prediction accuracy; establish model monitoring and incident response procedures; document accountability chain for outbreak alert decisions.

---

### FMoH-AI-002 · AI Radiology Assistant — LUTH (High Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| **GOVERN** | Chief Medical Director (LUTH) is accountable. Vendor relationship managed through hospital procurement. | No AI-specific governance policy. No AI governance training for radiology staff. No formal accountability framework for AI-assisted diagnostic decisions. | 1 |
| **MAP** | System purpose understood by radiology department. Clinical risk context informally assessed during vendor evaluation. | No formal risk mapping document. Training data demographic representation not evaluated. Potential for systematic underperformance on Nigerian patient cohorts not assessed. | 1 |
| **MEASURE** | Pilot monitoring underway — radiologists provide informal feedback on AI flag accuracy. | No structured performance evaluation against Nigerian patient data. No bias assessment. No false negative rate tracking (missed diagnoses). No defined accuracy thresholds for production readiness. | 1 |
| **MANAGE** | Mandatory consultant radiologist review before any diagnosis confirmed. | No audit trail for AI recommendations. No formal incident reporting if AI flags are found to have contributed to missed or delayed diagnoses. No production monitoring plan. | 1 |

**Overall Maturity: 1.0 (Initial)**  
**Priority Actions:** Conduct training data provenance review with vendor; establish performance benchmarks on Nigerian patient imaging data; implement audit trail for AI recommendations; define production readiness criteria; create incident reporting mechanism for diagnostic AI failures.

---

### FMoH-AI-003 · MamaAlert Maternal Risk Scoring Tool (High Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| **GOVERN** | Executive Director, NPHCDA accountable. System is externally funded (USAID) which adds a layer of donor accountability. | No formal AI governance policy at NPHCDA level. CHEWs who use the system daily have received no AI governance training. No mechanism for CHEWs to flag concerns about AI outputs. | 1 |
| **MAP** | System purpose and intended use case documented in donor programme documentation. | Risk mapping has not been performed to AI RMF standard. Rural performance degradation not formally identified as a programme risk. Vulnerable population (pregnant women in low-resource settings) not formally documented in a risk register. | 1 |
| **MEASURE** | Referral rates tracked at aggregate level as a programme metric. | No disaggregated performance analysis by geography, age group, or ethnicity. Rural vs urban prediction accuracy not compared. Outcome tracking (actual vs predicted maternal risk) not implemented — no basis for model improvement. | 1 |
| **MANAGE** | CHEWs and midwives make final referral decisions — nominal human oversight exists. | CHEWs lack capacity to meaningfully challenge or override AI outputs. No feedback loop from clinical outcomes to model retraining. No incident reporting mechanism. 24-month review cycle is inadequate for a High Risk system affecting maternal mortality. | 1 |

**Overall Maturity: 1.0 (Initial)**  
**Priority Actions:** Immediate: implement structured outcome tracking (actual vs predicted risk). Near-term: conduct rural performance validation; develop CHEW capacity building programme; establish bi-annual review cycle; create incident reporting mechanism; implement feedback loop to enable model retraining on Nigerian outcomes data.

---

### FMoH-AI-004 · DHIS2 Analytics and Forecasting Module (Limited Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| **GOVERN** | Director, NHMIS Division accountable. System governed under FMoH's existing health information management framework. | ML forecasting module added in 2023 without formal governance review of the upgraded capability. No AI-specific policy references this system. | 3 |
| **MAP** | Use case and risk context well understood. Advisory-only nature of outputs limits risk profile. | Risk mapping is informal. Data completeness risk from low-reporting facilities not formally documented. | 3 |
| **MEASURE** | Facility reporting rates tracked. Dashboard usage monitored by NHMIS team. | Forecast accuracy not formally evaluated. No assessment of planning decisions made on incomplete data. Methodology of ML forecasting module not documented for health planners. | 2 |
| **MANAGE** | Human planners review and act on all outputs. No automated decisions. | No formal AI incident classification. No defined process if forecasting module produces anomalous outputs. | 3 |

**Overall Maturity: 2.75 (Defined)**  
**Priority Actions:** Conduct retrospective governance review of 2023 ML module addition; document forecasting methodology for health planners; implement data completeness flagging in dashboard outputs; define anomalous output response procedure.

---

### FMoH-AI-005 · HealthLine Nigeria AI Triage Chatbot (High Risk — Critical)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| **GOVERN** | **No accountable owner assigned.** FMoH eHealth Division has not formally designated a system owner for this deployment. | Fundamental governance failure. No individual is responsible for this system's performance, safety, or incident response. Vendor accountability for harmful outputs not contractually defined. | 0 |
| **MAP** | System purpose informally understood as a public health access tool. | No formal risk assessment has been conducted. The risk of autonomous triage recommendations causing patient harm has not been formally identified or documented. Vulnerable user populations (low health literacy, emergency situations) not considered in risk mapping. | 0 |
| **MEASURE** | No performance monitoring in place. No tracking of triage recommendation accuracy, user outcomes, or adverse events. | No metrics defined. No data collected on whether triage recommendations led to appropriate care-seeking behaviour. No false negative tracking (Emergency cases classified as Self-care). | 0 |
| **MANAGE** | No human oversight at point of decision. No incident reporting mechanism. No adverse event reporting. | Complete absence of management controls for a system making autonomous healthcare decisions to the general public at scale. No defined response if a patient harm linked to an AI recommendation is reported. | 0 |

**Overall Maturity: 0.0 (Absent)**  
**Priority Actions — Immediate:** Suspend autonomous operation or implement emergency human oversight protocol. Appoint a named accountable owner. Establish adverse event reporting mechanism. Update vendor contract to include AI-specific safety obligations.  
**Near-term:** Conduct full risk assessment; define performance benchmarks; implement AI disclosure for users; establish monitoring and incident response framework before resuming deployment.

---

### FMoH-AI-006 · NCDC Contact Tracing ML Model (High Risk)

| RMF Function | Current State | Gaps | Maturity |
|---|---|---|---|
| **GOVERN** | Director of Surveillance, NCDC accountable. System was deployed under COVID-19 emergency protocols. | No standing governance framework for non-emergency activations. No formal policy governing conditions under which the system may be activated, or what oversight applies during activation. | 1 |
| **MAP** | Outbreak response context understood. System purpose documented in COVID-19 response records. | Civil liberties risks of CDR data use not formally assessed. Affected population (individuals identified as contacts without prior consent) not documented in a risk register. Legal basis for data processing not confirmed under NDPA 2023. | 1 |
| **MEASURE** | Contact identification accuracy informally assessed during COVID-19 deployment. | No formal evaluation of contact identification precision/recall. No assessment of false positives — individuals incorrectly identified as contacts and subjected to follow-up. | 1 |
| **MANAGE** | Field teams execute follow-up based on system outputs. | No formal activation/deactivation protocol. No data retention policy for CDR data post-outbreak. No defined scope limits for geographic or temporal deployment. No individual redress mechanism for incorrectly identified contacts. | 1 |

**Overall Maturity: 1.0 (Initial)**  
**Priority Actions:** Establish pre-activation governance framework before next outbreak event; confirm legal basis for CDR processing under NDPA 2023; define data retention and minimisation policy; establish scope limits and deactivation criteria; create individual redress mechanism.

---

## Portfolio-Level Summary

| System | EU AI Act Tier | RMF Maturity | Action Priority |
|---|---|---|---|
| FMoH-AI-001 NCDC Disease Surveillance | High Risk | 1.5 | High |
| FMoH-AI-002 AI Radiology Assistant (LUTH) | High Risk | 1.0 | Critical |
| FMoH-AI-003 MamaAlert Maternal Risk Tool | High Risk | 1.0 | Critical |
| FMoH-AI-004 DHIS2 Analytics Module | Limited Risk | 2.75 | Medium |
| FMoH-AI-005 HealthLine Triage Chatbot | High Risk | **0.0** | **Critical — Immediate** |
| FMoH-AI-006 NCDC Contact Tracing Model | High Risk | 1.0 | High |

---

## Portfolio Risk Assessment

**Risk concentration is severe.** Five of six inventoried systems are classified as High Risk under EU AI Act standards. Four of these five have NIST AI RMF maturity scores at or below 1.0 — meaning governance practices are either absent or entirely ad hoc.

The HealthLine Triage Chatbot (FMoH-AI-005) is the single most urgent priority in this portfolio. It is the only system with a maturity score of zero across all four RMF functions, and the only system making autonomous healthcare decisions directly to the general public without any human oversight or accountability structure.

**Recommended immediate actions at portfolio level:**

1. Appoint an FMoH AI Governance Lead responsible for coordinating remediation across all systems
2. Establish a centralised AI incident reporting function
3. Require all High Risk system owners to submit a governance remediation plan within 90 days
4. Gate any new AI system deployments on completion of a minimum governance checklist (accountability owner, risk mapping, human oversight protocol, incident reporting mechanism)

---

*Next review: December 2026, or upon any new AI system deployment or material change to an existing system.*

*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
