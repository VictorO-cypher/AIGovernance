# AI Governance Operating Model
## Federal Ministry of Health, Nigeria

**Document Version:** 1.0  
**Effective Date:** July 2026  
**Owner:** Director, eHealth Division, Federal Ministry of Health  

---

## 1. Purpose

This document defines the governance structure through which the Federal Ministry of Health (FMoH) operationalises its Responsible AI Policy. It specifies the committees, roles, and accountability relationships that ensure AI systems are governed consistently, proportionately, and in alignment with FMoH's patient safety and public health mandate.

---

## 2. Governance Structure Overview

```
┌─────────────────────────────────────────────────────────┐
│           HONOURABLE MINISTER OF HEALTH                 │
│     Strategic oversight and Ministerial accountability  │
└─────────────────────────────┬───────────────────────────┘
                              │
┌─────────────────────────────▼───────────────────────────┐
│                  PERMANENT SECRETARY                    │
│     High-Risk AI system approval authority              │
│     AI governance programme sponsor                     │
└─────────────────────────────┬───────────────────────────┘
                              │
┌─────────────────────────────▼───────────────────────────┐
│              AI REVIEW COMMITTEE                        │
│  Cross-functional oversight body for High-Risk AI       │
│  systems — review, recommend, and monitor               │
└──────┬──────────────────────┬──────────────────┬────────┘
       │                      │                  │
┌──────▼──────┐    ┌──────────▼───────┐  ┌──────▼────────┐
│  eHEALTH   │    │  LEGAL &         │  │  SYSTEM       │
│  DIVISION  │    │  PROCUREMENT     │  │  OWNERS       │
│  AI Gov    │    │  TEAM            │  │  (per system) │
│  Lead      │    │                  │  │               │
└─────────────┘    └──────────────────┘  └───────────────┘
```

---

## 3. Role Descriptions

---

### 3.1 Honourable Minister of Health

**Accountability:** Ultimate Ministerial accountability for FMoH's responsible use of AI in Nigeria's health system.

**Responsibilities:**
- Approves the Responsible AI Policy and any material amendments
- Receives annual AI governance report from the Permanent Secretary
- Makes public commitments on FMoH's approach to AI in healthcare
- Escalation point for AI incidents with significant public or political implications

**Time Commitment:** Annual policy approval; incident escalation as required.

---

### 3.2 Permanent Secretary

**Accountability:** Operational accountability for FMoH AI governance programme.

**Responsibilities:**
- Final approval authority for all High-Risk AI system deployments
- Chairs or delegates chairship of the AI Review Committee
- Receives quarterly AI governance reports from the eHealth Division
- Approves suspension of AI systems where patient safety is at risk
- Ensures AI governance is resourced within eHealth Division budget

**Time Commitment:** Quarterly AI Review Committee meetings; High-Risk system approval decisions as required.

---

### 3.3 AI Review Committee

**Accountability:** Cross-functional oversight of High-Risk AI systems throughout their lifecycle.

**Composition:**

| Member | Role |
|---|---|
| Director, eHealth Division | Chair |
| FMoH Legal Adviser | Legal and regulatory compliance |
| Director, Procurement | Vendor management and contract compliance |
| Representative, Clinical Services | Clinical safety and patient outcomes |
| Representative, NCDC | Public health and surveillance systems |
| Data Protection Officer (NDPA 2023) | Data protection and privacy |
| External Clinical AI Expert (independent) | Independent technical scrutiny |

The External Clinical AI Expert rotates annually and is selected from Nigerian academic medical institutions or regional AI governance bodies.

**Responsibilities:**
- Reviews and recommends approval, deferral, or rejection of High-Risk AI system submissions
- Conducts quarterly performance reviews of all active High-Risk AI systems
- Investigates AI incidents and near-misses
- Reviews and updates the FMoH Responsible AI Policy annually
- Advises the Permanent Secretary on emerging AI governance issues

**Meeting Frequency:** Quarterly (standing); extraordinary meetings as required for urgent submissions or incidents.

**Quorum:** Five of seven members, including the Chair and at least one of: Legal Adviser, Clinical Services Representative, or External Expert.

---

### 3.4 Director, eHealth Division

**Accountability:** Day-to-day management of FMoH's AI governance programme.

**Responsibilities:**
- Chairs the AI Review Committee
- Maintains the FMoH AI Systems Register
- Manages the AI use case submission and review process
- Approves Limited Risk AI system deployments
- Coordinates AI governance training for FMoH staff
- Prepares quarterly AI governance reports for the Permanent Secretary
- Serves as primary point of contact for AI vendors on governance matters
- Manages relationships with international AI governance bodies and donors

---

### 3.5 AI Governance Lead (eHealth Division)

**Accountability:** Operational execution of the AI governance programme under the Director's oversight.

**Responsibilities:**
- Conducts initial screening and risk classification of all AI system submissions
- Prepares documentation packages for AI Review Committee meetings
- Maintains and updates the FMoH AI Systems Register
- Conducts Stage 3B (Limited Risk) and Stage 3C (Minimal Risk) governance reviews
- Coordinates bias evaluations and independent technical assessments for High-Risk systems
- Tracks System Owner compliance with post-deployment monitoring obligations
- Manages the AI incident reporting system
- Delivers AI literacy training to FMoH staff

---

### 3.6 System Owners

**Accountability:** Individual accountability for a specific AI system's governance, performance, and compliance throughout its operational lifetime.

Every active AI system in the FMoH portfolio must have a named System Owner. System Owners are senior officials within the department or institution operating the system.

**Responsibilities:**
- Submitting new AI systems through the review process
- Maintaining system documentation in the FMoH AI Systems Register
- Ensuring the human oversight protocol is implemented and followed
- Monitoring system performance and reporting anomalies to the AI Governance Lead
- Submitting quarterly (High Risk) or annual (Limited/Minimal Risk) System Performance Reports
- Managing the vendor relationship and ensuring contract compliance
- Reporting AI incidents within 24 hours of identification
- Ensuring staff using the system receive appropriate AI literacy training

**Authority:**
- System Owners may suspend an AI system immediately if they identify a patient safety risk, without waiting for AI Review Committee approval. They must notify the AI Governance Lead within 2 hours of any suspension.

---

### 3.7 FMoH Legal Adviser and Data Protection Officer

**Accountability:** Legal and regulatory compliance of AI systems.

**Responsibilities:**
- Reviewing data processing agreements and vendor contracts for AI-specific compliance
- Advising on NDPA 2023 obligations for AI systems processing personal health data
- Advising the AI Review Committee on regulatory developments affecting AI systems
- Conducting or overseeing NDPA compliance assessments for High-Risk AI submissions
- Managing interactions with the Nigeria Data Protection Commission on AI-related matters

---

### 3.8 Procurement Team

**Accountability:** Ensuring AI-specific governance requirements are embedded in vendor contracts.

**Responsibilities:**
- Including mandatory AI contract clauses in all AI system procurement contracts (performance SLAs, incident reporting, data disclosure, audit rights, liability provisions)
- Obtaining AI Review Committee approval before committing to High-Risk AI procurement
- Conducting vendor due diligence on AI governance practices before contract award
- Managing contract renewals and ensuring AI governance clauses are updated as standards evolve

---

## 4. FMoH AI Systems Register

The AI Systems Register is the central record of all AI systems active within FMoH and its affiliated institutions. It is maintained by the AI Governance Lead and reviewed quarterly by the AI Review Committee.

### Register Fields

| Field | Description |
|---|---|
| System ID | Unique identifier (format: FMoH-AI-XXX) |
| System Name | Name of the AI system |
| Department / Institution | Operating department or affiliated institution |
| System Owner | Named accountable official |
| Vendor | Supplier name and contract reference |
| Risk Tier | High / Limited / Minimal |
| Deployment Status | Pilot / Production / Suspended / Decommissioned |
| Approval Date | Date of AI Review Committee or Director approval |
| Last Review Date | Date of most recent performance review |
| Next Review Due | Date of next scheduled performance review |
| Open Incidents | Number of open incident reports |

### Access

The register is maintained as a confidential internal document. A redacted summary (excluding vendor contract details and incident specifics) is published annually as part of FMoH's AI transparency report.

---

## 5. AI Incident Reporting

### Definition of an AI Incident

An AI incident is any event in which an AI system's output may have contributed to:

- Patient harm or near-miss
- Significant delay in appropriate care
- Discriminatory treatment of a patient or user
- Data breach involving personal health data
- Significant reputational or legal risk to FMoH

### Reporting Process

| Step | Action | Timeline |
|---|---|---|
| 1 | System Owner identifies or receives report of potential incident | — |
| 2 | System Owner notifies AI Governance Lead | Within 24 hours |
| 3 | AI Governance Lead conducts initial assessment and classifies severity | Within 48 hours |
| 4 | For Critical incidents: AI system suspended pending investigation | Immediately |
| 5 | AI Governance Lead convenes incident review (AI Review Committee for Critical/High) | Within 5 working days |
| 6 | Root cause analysis completed and remediation plan agreed | Within 30 working days |
| 7 | Remediation implemented and documented | Per agreed plan |
| 8 | Lessons learned shared across FMoH AI system portfolio | Within 60 working days |

### Severity Classification

| Severity | Description | Example |
|---|---|---|
| **Critical** | Patient harm confirmed or strongly suspected | AI triage chatbot recommended self-care for a patient who subsequently required emergency admission |
| **High** | Significant patient safety risk identified; no confirmed harm yet | Bias evaluation reveals systematic under-classification of emergency symptoms for rural users |
| **Medium** | Operational failure with potential patient impact | System outage during peak usage; performance degradation below defined thresholds |
| **Low** | Minor operational issue; no patient impact | Data quality anomaly in non-clinical planning system |

---

## 6. AI Literacy and Training

The AI Governance Programme can only function if FMoH staff understand AI well enough to use it responsibly and challenge it when appropriate.

The eHealth Division shall deliver the following training programme:

| Programme | Audience | Frequency | Format |
|---|---|---|---|
| AI Foundations for Health Professionals | All clinical staff using AI systems | Once at onboarding; refresher every 2 years | 2-hour online module |
| AI Governance for System Owners | All designated System Owners | Annually | Half-day workshop |
| AI Procurement and Contract Management | Procurement officers | Once; refreshed when standards change | 3-hour workshop |
| AI Review Committee Induction | New Committee members | On appointment | Full-day induction |

---

## 7. Annual AI Governance Report

The Director, eHealth Division, shall prepare an Annual AI Governance Report for the Permanent Secretary and Minister. The report shall include:

- Summary of all active AI systems in the FMoH portfolio
- Number and severity of AI incidents during the year
- Status of High-Risk AI system compliance
- Training completion rates
- Material changes to the AI governance framework
- Forward look: new AI systems expected in the coming year and governance readiness

A redacted public version of this report shall be published on the FMoH website as part of the Ministry's commitment to AI transparency.

---

*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
