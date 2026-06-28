# AI Risk Assessment — HealthLine Nigeria AI Triage Chatbot

**System:** FMoH-AI-005 — HealthLine Nigeria AI Triage Chatbot  
**Organisation:** Federal Ministry of Health (FMoH), Nigeria  
**Assessment Date:** June 2026  
**Prepared by:** Victor Eze Odoh, AI Governance Researcher  
**Review Due:** December 2026  
**Classification:** HIGH RISK (EU AI Act standards) | NIST AI RMF Maturity: 0.0  

---

## 1. System Overview

The HealthLine Nigeria AI Triage Chatbot is a conversational AI system deployed by the FMoH eHealth Division in partnership with Helium Health. It provides symptom assessment and triage guidance to members of the public via SMS and WhatsApp, directing users to one of three care pathways:

- **Self-care** — manage symptoms at home
- **Primary Care** — visit a primary health care centre
- **Emergency** — seek immediate emergency care

The system is currently in a pilot phase covering the Federal Capital Territory (FCT), Abuja. It operates **autonomously** — no human health professional reviews individual triage recommendations before they are delivered to users.

### Key Facts

| Parameter | Detail |
|---|---|
| Deployment Status | Production Pilot — FCT Abuja |
| User Base | General public — FCT residents |
| Interaction Channel | SMS and WhatsApp |
| Languages Supported | English and Nigerian Pidgin (unconfirmed) |
| Human Oversight | None at point of decision |
| Accountable Owner | Unassigned |
| Adverse Event Reporting | None in place |
| Vendor | Helium Health (Lagos) |
| Last Governance Review | Never conducted |

---

## 2. Risk Assessment Methodology

Risks are assessed on two dimensions:

**Likelihood** (probability of occurrence):

| Score | Level | Description |
|---|---|---|
| 5 | Almost Certain | Expected to occur regularly under normal operation |
| 4 | Likely | Will probably occur in most circumstances |
| 3 | Possible | May occur in some circumstances |
| 2 | Unlikely | Could occur but not expected |
| 1 | Rare | May occur only in exceptional circumstances |

**Impact** (severity of consequence if risk materialises):

| Score | Level | Description |
|---|---|---|
| 5 | Catastrophic | Patient death or severe irreversible harm; major public scandal |
| 4 | Major | Serious patient harm; significant delay in emergency care; regulatory action |
| 3 | Moderate | Patient harm requiring additional treatment; reputational damage |
| 2 | Minor | Inconvenience to patient; minor delays in care |
| 1 | Negligible | No meaningful impact on patient outcomes |

**Risk Rating = Likelihood × Impact**

| Rating | Level | Action Required |
|---|---|---|
| 20–25 | Critical | Immediate action — suspend or halt system operation |
| 15–19 | High | Urgent action within 30 days |
| 10–14 | Medium | Action within 90 days |
| 5–9 | Low | Monitor and review annually |
| 1–4 | Negligible | Accept and monitor |

---

## 3. Risk Register

---

### Risk 01 — Incorrect Emergency Triage (Under-triage)

**Description:** The system classifies a patient presenting with genuine emergency symptoms (e.g. chest pain, stroke symptoms, severe bleeding, obstetric emergency) as Self-care or Primary Care. The patient delays seeking emergency treatment, resulting in preventable serious harm or death.

**Risk Category:** Patient Safety — Clinical Harm

| Assessment | Score |
|---|---|
| Likelihood | 4 — Likely. Symptom assessment via text input is inherently limited. Patients may not accurately describe symptoms. The model cannot perform clinical examination. Emergency presentations are frequently atypical. |
| Impact | 5 — Catastrophic. Delayed emergency care for conditions such as stroke, myocardial infarction, or obstetric haemorrhage is a leading cause of preventable death in Nigeria. |
| **Inherent Risk Rating** | **20 — Critical** |

**Current Controls:** None. No human clinical review. No safety-netting advice ("if symptoms worsen, call emergency services") confirmed in system outputs.

**Proposed Mitigations:**
- Implement mandatory safety-netting message with every triage output — regardless of recommendation level
- Add automatic escalation for a defined list of red-flag symptom keywords (chest pain, difficulty breathing, heavy bleeding, loss of consciousness, severe headache)
- Introduce human clinical review for all Emergency classifications before delivery
- Display emergency contact numbers (NCDC, state emergency lines) with every interaction

**Residual Risk Rating (post-mitigation):** 12 — Medium  
**Residual Likelihood:** 3 | **Residual Impact:** 4

---

### Risk 02 — Algorithmic Bias Against Rural and Northern Nigerian Users

**Description:** The model's training data is unconfirmed but likely skewed toward urban, educated, English-speaking users. Performance may systematically degrade for users in rural FCT communities, users communicating in Nigerian Pidgin or local languages, or users with lower health literacy who describe symptoms in non-clinical terms.

**Risk Category:** Health Equity — Discriminatory Outcomes

| Assessment | Score |
|---|---|
| Likelihood | 4 — Likely. This is a documented pattern in AI health tools deployed in African contexts without localised training data. |
| Impact | 4 — Major. Systematic misclassification of a specific population group constitutes discriminatory harm and undermines the public health purpose of the tool. |
| **Inherent Risk Rating** | **16 — High** |

**Current Controls:** None. No bias evaluation has been conducted. No multilingual support confirmed.

**Proposed Mitigations:**
- Commission independent bias evaluation disaggregated by geography, language, and literacy level
- Require vendor to disclose training data demographic composition
- Pilot multilingual support (Hausa, Igbo, Yoruba, Pidgin) before national rollout
- Implement performance monitoring disaggregated by user geography and language

**Residual Risk Rating (post-mitigation):** 9 — Low  
**Residual Likelihood:** 3 | **Residual Impact:** 3

---

### Risk 03 — Absence of Accountable Owner

**Description:** No individual within FMoH has been formally designated as the accountable owner for this system. If a patient is harmed, there is no defined process for accountability, investigation, or response. The system is effectively operating without a responsible principal.

**Risk Category:** Governance — Accountability Gap

| Assessment | Score |
|---|---|
| Likelihood | 5 — Almost Certain. The gap is already confirmed — no owner is currently assigned. |
| Impact | 4 — Major. In the event of patient harm, the absence of an accountable owner exposes FMoH to reputational, legal, and regulatory consequences with no defined response capability. |
| **Inherent Risk Rating** | **20 — Critical** |

**Current Controls:** None.

**Proposed Mitigations:**
- Immediately designate a named Senior Health Officer as System Owner with documented accountability
- Define the System Owner's responsibilities: performance monitoring, incident response, vendor management, and annual review
- Include AI system accountability in FMoH eHealth Division's performance framework

**Residual Risk Rating (post-mitigation):** 8 — Low  
**Residual Likelihood:** 1 | **Residual Impact:** 4 (harm potential remains; accountability risk eliminated)

---

### Risk 04 — Vendor Accountability Gap

**Description:** The current contract with Helium Health does not contain AI-specific obligations — no model performance standards, no incident reporting requirements, no data breach notification timelines, and no liability provisions for AI recommendation errors. If the system causes harm, FMoH has no contractual basis to hold the vendor accountable.

**Risk Category:** Legal and Contractual — Vendor Risk

| Assessment | Score |
|---|---|
| Likelihood | 5 — Almost Certain. Confirmed — no AI-specific clauses in current contract. |
| Impact | 3 — Moderate. Financial and reputational exposure for FMoH; limited recourse against vendor. |
| **Inherent Risk Rating** | **15 — High** |

**Current Controls:** None specific to AI performance or safety.

**Proposed Mitigations:**
- Renegotiate vendor contract to include: model performance SLAs, incident reporting obligations (within 24 hours of identified harm), training data disclosure, bias audit requirements, and liability provisions
- Require vendor to provide quarterly performance reports with precision/recall metrics
- Include right to audit and right to terminate clauses

**Residual Risk Rating (post-mitigation):** 6 — Low  
**Residual Likelihood:** 2 | **Residual Impact:** 3

---

### Risk 05 — Absence of AI Disclosure to Users

**Description:** Users interacting with the HealthLine chatbot may not be clearly informed they are receiving advice from an AI system rather than a qualified health professional. This creates a transparency failure and may cause users to place inappropriate confidence in AI recommendations.

**Risk Category:** Transparency — User Rights

| Assessment | Score |
|---|---|
| Likelihood | 3 — Possible. Disclosure status unconfirmed — may not be prominently displayed. |
| Impact | 3 — Moderate. Users who believe they are speaking with a clinician may not seek further care when appropriate. |
| **Inherent Risk Rating** | **9 — Low** |

**Current Controls:** Unconfirmed — disclosure status not documented.

**Proposed Mitigations:**
- Implement mandatory AI disclosure at the start of every interaction in plain language: *"This is an automated health information service, not a doctor. Always seek professional medical advice for serious concerns."*
- Display disclosure in English and Nigerian Pidgin as a minimum
- Log disclosure delivery for audit purposes

**Residual Risk Rating (post-mitigation):** 4 — Negligible  
**Residual Likelihood:** 1 | **Residual Impact:** 3

---

### Risk 06 — Data Protection Non-Compliance (NDPA 2023)

**Description:** The system collects sensitive health data (symptoms, age, location) from users via WhatsApp and SMS. It is unclear whether data processing complies with Nigeria's Data Protection Act 2023, which requires lawful basis for processing sensitive personal data, user consent, and data minimisation.

**Risk Category:** Legal — Data Protection

| Assessment | Score |
|---|---|
| Likelihood | 3 — Possible. NDPA 2023 compliance has not been confirmed for this system. |
| Impact | 3 — Moderate. Regulatory action by the Nigeria Data Protection Commission; reputational damage. |
| **Inherent Risk Rating** | **9 — Low** |

**Current Controls:** Unknown — data governance documentation not available.

**Proposed Mitigations:**
- Conduct NDPA 2023 compliance review with FMoH legal team
- Implement explicit consent mechanism at start of each interaction
- Define and enforce data retention limits for symptom data
- Confirm data storage location and security standards with vendor

**Residual Risk Rating (post-mitigation):** 4 — Negligible  
**Residual Likelihood:** 1 | **Residual Impact:** 3

---

## 4. Risk Summary Matrix

| Risk | Category | Inherent Rating | Inherent Level | Residual Rating | Residual Level |
|---|---|---|---|---|---|
| R01 — Incorrect Emergency Triage | Patient Safety | 20 | Critical | 12 | Medium |
| R02 — Algorithmic Bias | Health Equity | 16 | High | 9 | Low |
| R03 — No Accountable Owner | Governance | 20 | Critical | 8 | Low |
| R04 — Vendor Accountability Gap | Legal/Contractual | 15 | High | 6 | Low |
| R05 — No AI Disclosure | Transparency | 9 | Low | 4 | Negligible |
| R06 — NDPA Non-Compliance | Data Protection | 9 | Low | 4 | Negligible |

---

## 5. Overall Risk Position and Recommendation

**Current inherent risk position: CRITICAL**

The HealthLine Nigeria AI Triage Chatbot is currently operating with two Critical-rated risks (R01 and R03) and two High-rated risks (R02 and R04). The combination of autonomous clinical decision-making, zero human oversight, no accountable owner, and unvalidated performance on the Nigerian population creates an unacceptable risk profile.

**Recommendation: Conditional Suspension**

The system should be suspended from autonomous operation until the following minimum conditions are met:

1. A named System Owner is appointed within FMoH eHealth Division
2. Safety-netting messages and red-flag escalation protocols are implemented
3. Human clinical review is introduced for all Emergency classifications
4. Vendor contract is updated with AI-specific performance and accountability clauses
5. AI disclosure is confirmed and documented

Upon meeting these conditions, the system may resume operation under a formal governance framework with quarterly review.

---

*This risk assessment should be reviewed upon any material change to the system's design, deployment scope, or operating context.*

*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
