# EU AI Act Risk Classification — Federal Ministry of Health, Nigeria

**Classification Date:** June 2026  
**Prepared by:** Victor Eze Odoh, AI Governance Researcher  
**Review Due:** December 2026  

---

## Classification Framework

The EU AI Act establishes four risk tiers. Classification determines the compliance obligations that attach to a system. Although Nigeria is not an EU member state, this classification exercise applies EU AI Act standards as a global governance benchmark — one increasingly referenced in donor conditions, international procurement frameworks, and AI policy dialogue across Africa.

### Risk Tier Overview

| Tier | Regulatory Treatment |
|---|---|
| Unacceptable Risk | Prohibited. System must not be deployed. |
| High Risk | Strict pre-deployment obligations. Conformity assessment required. Ongoing monitoring, logging, human oversight, and documentation mandated. |
| Limited Risk | Transparency obligations. Users must be informed they are interacting with an AI. |
| Minimal Risk | No specific regulatory obligations under the Act. General data protection and sector rules still apply. |

---

## Classification Decisions

---

### FMoH-AI-001 · NCDC Disease Surveillance Platform

**Classification: HIGH RISK**

**Legal Basis:** EU AI Act Annex III, Category 1 — *"AI systems intended to be used as safety components in the management and operation of critical infrastructure."* Public health emergency surveillance qualifies as critical infrastructure under this category.

**Rationale:**

The NCDC Disease Surveillance Platform generates outbreak risk probability scores that directly inform public health emergency alerts and the deployment of emergency response resources across Nigeria's 36 states and FCT. When the system classifies a region as "High" or "Critical" risk, it triggers alert notifications to epidemiologists and can initiate resource mobilisation responses affecting millions of people.

The system processes sensitive population-level data including patient case reports, hospital admission records, climate variables, and geographic location data. The combination of population-scale impact and emergency response integration places this system firmly in the high-risk tier regardless of the EU AI Act's geographic scope.

**Obligations triggered (applied as best-practice standard):**
- Conformity assessment before deployment and after significant updates
- Technical documentation of model architecture, training data, and performance benchmarks
- Logging and audit trail of predictions and alert decisions
- Human oversight — epidemiologist review before alerts are issued (currently in place)
- Accuracy and robustness requirements — particularly regarding data quality from low-reporting rural LGAs
- Explainability — epidemiologists must be able to understand and challenge model predictions

**Current governance gap:** Model explainability is limited — epidemiologists cannot interrogate prediction logic. Data quality gaps in rural LGA reporting create risk of systematically biased predictions for underserved regions. No formal conformity documentation exists. **Priority: High.**

---

### FMoH-AI-002 · AI Radiology Assistant (LUTH)

**Classification: HIGH RISK**

**Legal Basis:** EU AI Act Annex III, Category 2(a) — *"AI systems intended to be used as safety components in the management and operation of... medical devices."* Diagnostic imaging AI used to flag clinical findings falls directly within this category.

**Rationale:**

The AI Radiology Assistant analyses chest X-rays and CT scans to detect anomalies associated with TB, pneumonia, and cancer. Its outputs — anomaly probability scores and review flags — directly influence which cases receive urgent radiologist attention. In a high-volume hospital environment like LUTH, the system's triage decisions determine how quickly life-threatening conditions are identified and treated.

The training data concern is particularly significant: if the model was trained predominantly on non-Nigerian patient cohorts, it may systematically underperform for Nigerian patients whose imaging presentations may differ due to population-specific disease prevalence, nutrition, and environmental factors. This constitutes a material bias risk that has not been evaluated.

**Obligations triggered:**
- Full conformity assessment before production deployment (currently in pilot without assessment)
- Technical documentation including training data provenance and demographic representation
- Bias evaluation on Nigerian patient imaging data
- Audit trail for every AI recommendation — which cases were flagged and what action was taken
- Mandatory human oversight — consultant radiologist review before any diagnosis is confirmed (in place but not formally documented)

**Current governance gap:** No conformity assessment conducted. Training data source and demographic composition not disclosed by vendor. No audit trail for AI recommendations. No formal documentation of the human oversight protocol. **Priority: Critical.**

---

### FMoH-AI-003 · MamaAlert Maternal Risk Scoring Tool

**Classification: HIGH RISK**

**Legal Basis:** EU AI Act Annex III, Category 2(a) — AI used in healthcare affecting vulnerable populations; and general high-risk criteria — AI system making consequential recommendations affecting the health and safety of natural persons.

**Rationale:**

MamaAlert stratifies maternal mortality risk and generates referral recommendations that determine whether a pregnant woman is referred to specialist care. In contexts where specialist facilities are distant and transport is limited, an incorrect Low or Medium risk classification for a genuinely high-risk pregnancy can be fatal. The system affects one of the most vulnerable populations in any healthcare system — pregnant women in low-resource settings.

The rural performance gap is the defining governance concern. The model was developed primarily on urban facility data. In rural Northern Nigerian communities — where maternal mortality rates are highest and where the system is most needed — the model has not been validated. Deploying an unvalidated model to guide referral decisions for the highest-risk population is a significant governance failure.

**Obligations triggered:**
- Conformity assessment with specific attention to geographic and demographic performance variation
- Mandatory bias evaluation — model performance must be separately validated for rural Northern Nigerian settings
- Training data documentation — current data provenance (urban vs rural, regional distribution) must be disclosed
- CHEW capacity building — Community Health Extension Workers must receive training to interpret and challenge AI outputs
- Feedback mechanism — a structured system for capturing outcomes (actual vs predicted risk) must be implemented to enable model retraining on Nigerian data

**Current governance gap:** Model not validated for rural performance. CHEWs lack capacity to interpret or challenge outputs. No outcome feedback loop. Review cycle of 24 months is inadequate for a High Risk system. **Priority: Critical.**

---

### FMoH-AI-004 · DHIS2 Analytics and Forecasting Module

**Classification: LIMITED RISK**

**Legal Basis:** Not listed in Annex III. Advisory planning tool with human decision-maker retaining full control.

**Rationale:**

The DHIS2 Analytics Module generates health data trend reports and resource planning forecasts for internal use by FMoH health planners. All outputs are advisory — health planners and M&E officers interpret the dashboard and make their own resource allocation decisions. The system does not make or recommend decisions that directly affect individual natural persons.

The ML forecasting module added in 2023 increases the system's sophistication but does not change its fundamental character as an internal planning support tool. The consequential decisions remain with human officials.

**Obligations triggered:**
- No high-risk obligations under EU AI Act standards
- Transparency of methodology — health planners should understand how forecasts are generated and what data completeness assumptions are embedded
- Data quality flagging — the system should surface data completeness indicators so planners know when forecasts are based on incomplete facility reporting

**Current governance gap:** ML forecasting module added in 2023 without formal governance review of the upgraded functionality. Data completeness gaps from low-reporting facilities not consistently surfaced to planners. **Priority: Medium.**

---

### FMoH-AI-005 · HealthLine Nigeria AI Triage Chatbot

**Classification: HIGH RISK**

**Legal Basis:** EU AI Act Annex III, Category 2(a) — AI system making healthcare recommendations to natural persons; and Article 52 — transparency obligations for AI systems interacting directly with natural persons.

**Rationale:**

The HealthLine Triage Chatbot is the highest-risk system in this inventory and the most urgent governance priority. It provides autonomous triage recommendations — including Emergency classifications — directly to members of the general public via SMS and WhatsApp, with no mandatory human review at the point of decision.

Unlike the other systems in this inventory where human oversight is at least nominally present, this system operates at scale with no human in the loop. A patient who receives an incorrect Self-care recommendation when they require emergency care may delay treatment until it is too late. The system is deployed to the general public — including individuals with low health literacy who may be unable to critically evaluate the AI's recommendation.

The absence of an assigned accountability owner within FMoH eHealth Division is a fundamental governance failure. No individual is currently responsible for this system's performance, safety, or incident response.

**Obligations triggered:**
- Immediate appointment of an accountable system owner within FMoH eHealth Division
- Suspension of fully autonomous operation pending implementation of human oversight protocols
- Conformity assessment before resuming deployment
- AI disclosure — patients must be clearly informed they are interacting with an AI system, not a health professional
- Adverse event reporting mechanism — a formal process for capturing and investigating cases where the triage recommendation may have contributed to patient harm
- Vendor accountability — contract must be updated to include AI-specific performance, safety, and incident reporting obligations

**Current governance gap:** No accountable owner. No human oversight at point of decision. No adverse event reporting. No AI disclosure mechanism confirmed. Vendor accountability undefined. **Priority: Critical — immediate action required.**

---

### FMoH-AI-006 · NCDC Contact Tracing ML Model

**Classification: HIGH RISK**

**Legal Basis:** EU AI Act Annex III, Category 1 — critical infrastructure (public health emergency response); and general high-risk criteria — AI system processing sensitive personal data (location, call records) with significant impact on natural persons.

**Rationale:**

The Contact Tracing Model uses call data records (CDR) and case interview data to identify and prioritise likely disease contacts for field follow-up. The use of CDR data raises serious civil liberties concerns — location tracking and social network mapping of individuals who have not consented to surveillance is a significant rights intrusion, even in an outbreak context.

The system is currently inactive but was deployed during COVID-19. The absence of a governance framework means it could be reactivated in a future outbreak without any accountability structure, data minimisation protocols, or oversight mechanism in place.

**Obligations triggered:**
- Pre-activation governance framework — establish accountability, data minimisation, and oversight protocols before the next activation
- Consent and legal basis documentation — clarify the legal basis for CDR data processing under Nigeria's data protection framework (NDPA 2023)
- Data retention policy — define and enforce limits on how long CDR data is retained post-outbreak
- Scope limitation — define the conditions under which the system may be activated and the geographic and temporal limits of each deployment

**Current governance gap:** No governance framework for activation. Data minimisation and consent protocols not documented. Data retention policy not confirmed. **Priority: High (pre-activation gate condition).**

---

## Classification Summary

| System | Classification | Compliance Status | Priority |
|---|---|---|---|
| FMoH-AI-001 NCDC Disease Surveillance | High Risk | Partial — explainability and documentation gaps | High |
| FMoH-AI-002 AI Radiology Assistant (LUTH) | High Risk | Non-compliant — no conformity assessment | Critical |
| FMoH-AI-003 MamaAlert Maternal Risk Tool | High Risk | Non-compliant — rural validation absent | Critical |
| FMoH-AI-004 DHIS2 Analytics Module | Limited Risk | Adequate — methodology transparency gap | Medium |
| FMoH-AI-005 HealthLine Triage Chatbot | High Risk | Non-compliant — no oversight, no owner | Critical — Immediate |
| FMoH-AI-006 NCDC Contact Tracing Model | High Risk | Non-compliant — no activation governance | High |

---

## Important Note on Applicability

Nigeria is not subject to the EU AI Act. This classification exercise applies EU AI Act standards as an internationally recognised governance benchmark. The practical relevance is threefold:

1. **Donor and procurement conditions** — international health donors (USAID, GAVI, Global Fund) increasingly reference EU AI Act standards in procurement and funding conditions
2. **Policy development** — the Nigeria National Information Technology Development Agency (NITDA) and the Federal Ministry of Communications are actively developing Nigeria's AI governance framework; EU AI Act principles are a reference point
3. **Institutional credibility** — FMoH systems that can demonstrate alignment with international standards are better positioned for international partnerships and funding

---

*This classification document should be reviewed annually or upon material change to a system's design, purpose, or deployment context. Classification decisions are not static.*

*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
