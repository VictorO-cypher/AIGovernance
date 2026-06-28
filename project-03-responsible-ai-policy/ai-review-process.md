# AI Use Case Review & Approval Process
## Federal Ministry of Health, Nigeria

**Document Version:** 1.0  
**Effective Date:** July 2026  
**Owner:** Director, eHealth Division, Federal Ministry of Health  

---

## 1. Purpose

This document defines the process by which AI systems are submitted, reviewed, approved, and monitored within the Federal Ministry of Health (FMoH). It ensures that every AI deployment — whether procured from a vendor, developed internally, or introduced through a donor programme — passes through a proportionate governance review before deployment.

The process is designed to be **proportionate**: minimal-risk systems receive a lightweight review. High-risk clinical AI systems receive rigorous scrutiny. The goal is appropriate oversight, not bureaucratic friction.

---

## 2. Process Overview

The FMoH AI Review Process has five stages:

```
Stage 1: Submission
      ↓
Stage 2: Initial Screening & Risk Classification
      ↓
Stage 3: Governance Review (proportionate to risk tier)
      ↓
Stage 4: Approval Decision
      ↓
Stage 5: Post-Deployment Monitoring
```

---

## 3. Stage 1 — Submission

### Who submits?

Any FMoH department head, hospital director, programme manager, or donor programme coordinator who intends to:

- Procure a new AI system or AI-powered service
- Deploy an AI system developed internally or by a donor partner
- Significantly upgrade or expand the scope of an existing AI system

### What is submitted?

The submitting party completes an **AI System Submission Form** and sends it to the eHealth Division. The form requires:

| Field | Description |
|---|---|
| System name and vendor | Name of the AI system and the vendor or developer |
| Intended use case | What the system will be used for and by whom |
| Data inputs | What data the system will process |
| Outputs | What the system will produce (predictions, recommendations, decisions) |
| Affected persons | Who will be affected by the system's outputs |
| Human oversight | How human review of AI outputs is planned |
| Proposed System Owner | Who will be accountable for the system |
| Procurement status | Whether procurement has begun and at what stage |

### Timeline

The eHealth Division acknowledges receipt within **5 working days** and initiates Stage 2 screening.

---

## 4. Stage 2 — Initial Screening & Risk Classification

### Who conducts it?

The eHealth Division AI Governance Lead conducts initial screening, in consultation with the FMoH Legal Adviser where needed.

### What happens?

The AI Governance Lead reviews the submission form and assigns a risk tier based on the FMoH AI Risk Classification criteria (aligned with EU AI Act tiers):

| Risk Tier | Classification Criteria |
|---|---|
| **High Risk** | System makes or influences clinical decisions, patient triage, disease surveillance, or public health emergency response; system processes sensitive health data to generate individual-level recommendations |
| **Limited Risk** | System interacts with patients or public in non-clinical context; advisory-only outputs with no direct clinical decision pathway |
| **Minimal Risk** | Internal administrative or planning tool; no direct patient impact; human retains full decision authority |
| **Unacceptable Risk** | System manipulates patients; enables covert surveillance; violates NDPA 2023 or FMoH ethical standards |

### Outputs

- Risk tier assigned and communicated to submitting party within **10 working days**
- Unacceptable Risk systems: rejected immediately with written explanation
- High Risk systems: proceed to full governance review (Stage 3A)
- Limited Risk systems: proceed to standard review (Stage 3B)
- Minimal Risk systems: proceed to lightweight review (Stage 3C)

---

## 5. Stage 3 — Governance Review

### Stage 3A — Full Governance Review (High Risk Systems)

**Conducted by:** AI Review Committee  
**Timeline:** 30 working days

The submitting party must provide:

| Document | Description |
|---|---|
| Risk Assessment | Structured risk assessment using FMoH risk methodology (see Project 02) |
| Bias Evaluation Report | Independent evaluation of system performance across demographic groups |
| Training Data Disclosure | Vendor disclosure of training data provenance and demographic representation |
| Human Oversight Protocol | Documented process for human review of AI outputs |
| Data Protection Assessment | NDPA 2023 compliance review for personal health data processing |
| Vendor AI Contract Clauses | Confirmation that AI-specific obligations are included in vendor contract |
| System Owner Nomination | Formal nomination of a named System Owner with written acceptance |

The AI Review Committee reviews all documents, may request additional information or independent expert assessment, and issues a written recommendation to the Permanent Secretary.

---

### Stage 3B — Standard Review (Limited Risk Systems)

**Conducted by:** eHealth Division AI Governance Lead  
**Timeline:** 15 working days

Required documentation:

| Document | Description |
|---|---|
| AI Disclosure Plan | How users will be informed they are interacting with an AI |
| Data Protection Assessment | NDPA 2023 compliance review |
| System Owner Nomination | Named System Owner with written acceptance |

The AI Governance Lead reviews documentation and issues an approval recommendation.

---

### Stage 3C — Lightweight Review (Minimal Risk Systems)

**Conducted by:** eHealth Division AI Governance Lead  
**Timeline:** 5 working days

Required documentation:

| Document | Description |
|---|---|
| System Owner Nomination | Named System Owner with written acceptance |
| Brief Use Case Description | One-page summary of system purpose, data inputs, and outputs |

The AI Governance Lead registers the system in the FMoH AI Systems Register and issues confirmation of registration.

---

## 6. Stage 4 — Approval Decision

### High Risk Systems

**Decision Authority:** Permanent Secretary, FMoH (on recommendation of AI Review Committee)

Possible decisions:
- **Approved** — system may proceed to deployment with conditions as specified
- **Approved with Conditions** — system may proceed subject to satisfying specified conditions within a defined timeframe
- **Deferred** — additional information or remediation required before decision
- **Rejected** — system does not meet FMoH governance standards and may not be deployed

All decisions are communicated in writing to the submitting party within **5 working days** of the AI Review Committee recommendation.

### Limited Risk Systems

**Decision Authority:** Director, eHealth Division

### Minimal Risk Systems

**Decision Authority:** eHealth Division AI Governance Lead (registration confirmation)

---

## 7. Stage 5 — Post-Deployment Monitoring

Approval is not the end of governance — it is the beginning of ongoing oversight.

### Review Frequencies

| Risk Tier | Review Frequency | Reviewer |
|---|---|---|
| High Risk | Quarterly | System Owner + AI Review Committee |
| Limited Risk | Annual | System Owner + eHealth Division |
| Minimal Risk | Annual | System Owner |

### What is reviewed?

At each review, the System Owner submits a **System Performance Report** covering:

- Performance metrics (accuracy, false positive/negative rates where applicable)
- Incidents or near-misses since last review
- Changes to system design, scope, or data inputs
- User feedback and complaints
- Vendor compliance with contract obligations
- Any material changes to the risk profile

### Triggers for unscheduled review

The following events trigger an immediate unscheduled review regardless of the scheduled cycle:

- Any identified case of patient harm potentially linked to an AI recommendation
- A material change to the system's design, training data, or operational scope
- A significant change in the vendor's ownership, financial stability, or security posture
- A data breach involving personal health data processed by the system
- A regulatory or legal development that may affect the system's compliance status

---

## 8. Fast-Track Process for Donor-Funded AI Systems

Many AI systems in the FMoH portfolio are introduced through international donor programmes (USAID, GAVI, Global Fund, WHO). These systems frequently arrive with existing governance documentation from the donor's own review processes.

Donor-funded systems are not exempt from this review process. However, where a donor has conducted a governance review aligned with NIST AI RMF, WHO AI Ethics guidance, or equivalent international standards, the eHealth Division may accept donor documentation in partial satisfaction of Stage 3 requirements. A gap analysis will be conducted to identify any requirements not addressed by donor documentation.

Donor programme managers are encouraged to engage the eHealth Division early in procurement planning to streamline the review process.

---

## 9. Process Summary Diagram

```
AI System Identified
        ↓
Submit AI System Submission Form to eHealth Division
        ↓
eHealth Division: Initial Screening & Risk Classification (10 days)
        ↓
    ┌───────────────────────────────────────┐
    │                                       │
High Risk                            Limited Risk          Minimal Risk
    │                                       │                   │
Full Governance Review              Standard Review      Lightweight Review
(AI Review Committee, 30 days)      (15 days)            (5 days)
    │                                       │                   │
Permanent Secretary Decision        Director Decision    Registration
    │                                       │                   │
    └───────────────────────────────────────┘
                        ↓
              Deployment (if approved)
                        ↓
         Post-Deployment Monitoring (ongoing)
                        ↓
         Scheduled Reviews + Incident Reporting
```

---

*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
