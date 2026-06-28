# Responsible AI Policy
## Federal Ministry of Health, Nigeria

**Document Version:** 1.0  
**Effective Date:** July 2026  
**Review Date:** July 2027  
**Owner:** Director, eHealth Division, Federal Ministry of Health  
**Approved by:** Honourable Minister of Health, Federal Republic of Nigeria  

---

## 1. Purpose and Scope

### 1.1 Purpose

This policy establishes the Federal Ministry of Health's (FMoH) commitment to the responsible development, procurement, deployment, and use of artificial intelligence (AI) systems. It sets out the principles, obligations, and standards that govern all AI activity within FMoH and provides the foundation for the Ministry's AI Governance Operating Model.

AI offers significant potential to strengthen Nigeria's health system — improving diagnostic accuracy, expanding access to health information, optimising resource allocation, and accelerating disease surveillance. Realising this potential requires that AI systems are trustworthy, accountable, and designed with the needs and rights of Nigerian patients at their centre.

### 1.2 Scope

This policy applies to:

- All AI systems procured, deployed, or used by FMoH headquarters divisions and departments
- All AI systems deployed in FMoH-affiliated institutions (teaching hospitals, research institutes, national agencies)
- AI systems funded through donor programmes managed by or accountable to FMoH
- Third-party vendors supplying AI systems to FMoH or its affiliated institutions
- All FMoH staff, contractors, and partners who procure, manage, or use AI systems

This policy does not apply to basic data analytics tools, standard statistical software, or rule-based systems that do not involve machine learning or predictive modelling.

---

## 2. Definitions

| Term | Definition |
|---|---|
| **AI System** | A machine-based system that generates outputs — predictions, recommendations, decisions, or content — that influence real-world decisions, for a given set of objectives |
| **High-Risk AI System** | An AI system whose outputs directly influence clinical decisions, resource allocation decisions, or public-facing health guidance (aligned with EU AI Act Annex III categories as a benchmark) |
| **System Owner** | The designated FMoH official accountable for a specific AI system's governance, performance, and compliance |
| **AI Vendor** | Any third-party organisation supplying an AI system or AI-powered service to FMoH or its affiliated institutions |
| **Human Oversight** | A meaningful, documented process by which a qualified human reviews and can override or escalate an AI system's output before or after it is acted upon |

---

## 3. Responsible AI Principles

FMoH is committed to the following six principles in all AI activity. Each principle is accompanied by the operational commitment that gives it practical effect.

---

### Principle 1 — Patient Safety First

**Commitment:** No AI system shall be deployed in a clinical or patient-facing context unless it can be demonstrated that it does not create an unreasonable risk of harm to patients.

**In practice:**
- All High-Risk AI systems require a formal risk assessment before deployment
- AI systems making clinical recommendations must have mandatory human clinical review before recommendations are acted upon
- All patient-facing AI systems must include safety-netting advice directing users to seek professional care if symptoms worsen
- AI systems must be suspended immediately if evidence of patient harm linked to AI recommendations is identified

---

### Principle 2 — Accountability

**Commitment:** Every AI system deployed within FMoH or its affiliated institutions shall have a named, accountable System Owner. No AI system shall operate without a responsible principal.

**In practice:**
- A System Owner must be designated before any AI system is deployed or procured
- System Owners are personally accountable for their system's governance, performance monitoring, and incident response
- The FMoH AI Systems Register (maintained by eHealth Division) shall record the System Owner for every active AI deployment
- Operating an AI system without a designated System Owner is a policy violation

---

### Principle 3 — Transparency

**Commitment:** Patients and users have the right to know when they are interacting with or being assessed by an AI system. FMoH will be transparent about its use of AI.

**In practice:**
- All patient-facing AI systems must clearly disclose their automated nature at the start of every interaction
- Disclosures must be in plain language accessible to users with low health literacy
- Disclosures must be available in English and, where applicable, in the primary local language(s) of the user population
- FMoH will publish an annual summary of active AI deployments across its portfolio

---

### Principle 4 — Fairness and Health Equity

**Commitment:** AI systems deployed by FMoH shall not discriminate on the basis of gender, ethnicity, geography, language, age, or socioeconomic status. FMoH will actively work to ensure AI benefits all Nigerians — particularly those in underserved communities.

**In practice:**
- All High-Risk AI systems shall undergo a bias evaluation before deployment, assessing performance across demographic groups relevant to the Nigerian context (urban/rural, Northern/Southern, English/Pidgin/local language)
- Bias evaluation results shall be disclosed to the AI Review Committee
- AI systems found to perform significantly worse for any identifiable population group shall not be deployed until performance gaps are addressed
- Post-deployment performance monitoring shall include disaggregated metrics by geography and demographics where feasible

---

### Principle 5 — Human Oversight and Control

**Commitment:** AI systems shall support, not replace, human clinical and institutional judgement. Humans must remain in meaningful control of decisions that affect patient health and welfare.

**In practice:**
- All High-Risk AI systems must have a documented human oversight protocol specifying who reviews AI outputs, when, and how they can override or escalate
- Fully autonomous AI systems making healthcare decisions without any human review are not permitted for High-Risk use cases
- Human oversight must be substantive — not nominal. Oversight processes where reviewers lack the time, training, or authority to meaningfully challenge AI outputs do not satisfy this requirement
- All staff using AI systems shall receive appropriate training on interpreting, challenging, and overriding AI outputs

---

### Principle 6 — Data Protection and Privacy

**Commitment:** FMoH will process personal health data used in AI systems in accordance with Nigeria's Data Protection Act 2023 (NDPA) and applicable health data governance standards.

**In practice:**
- AI systems processing personal health data must have a documented lawful basis under the NDPA 2023
- Sensitive health data shall not be shared with AI vendors without a formal data processing agreement
- Data minimisation shall be applied — AI systems shall only collect and process the minimum personal data necessary for their function
- Data retention limits shall be defined and enforced for all AI systems processing personal health data

---

## 4. AI System Classification

All AI systems within scope of this policy shall be classified into one of four risk tiers, using EU AI Act standards as a benchmark:

| Tier | Description | Examples | Governance Requirements |
|---|---|---|---|
| **High Risk** | AI systems making or influencing clinical decisions, public health emergency responses, or patient-facing triage guidance | Diagnostic imaging AI, triage chatbots, disease surveillance platforms, maternal risk scoring | Full risk assessment, bias evaluation, human oversight protocol, System Owner, quarterly review |
| **Limited Risk** | AI systems interacting with patients or the public in non-clinical contexts | Health information chatbots, appointment booking assistants | AI disclosure, System Owner, annual review |
| **Minimal Risk** | AI systems used internally for administrative or planning purposes | Resource planning dashboards, staff scheduling tools | System Owner, annual review |
| **Unacceptable Risk** | AI systems that FMoH will not deploy under any circumstances | Systems that manipulate patients; systems that enable covert surveillance of health workers without consent | Prohibited |

---

## 5. Obligations

### 5.1 System Owners

System Owners are responsible for:

- Maintaining up-to-date records in the FMoH AI Systems Register
- Conducting or commissioning risk assessments for High-Risk systems
- Ensuring human oversight protocols are documented and followed
- Monitoring system performance and reporting anomalies to the AI Review Committee
- Managing vendor relationships and ensuring AI-specific contract clauses are in place
- Reporting AI incidents in accordance with the AI Incident Response Policy

### 5.2 Procurement Teams

Procurement officers are responsible for:

- Ensuring AI-specific clauses are included in all vendor contracts (performance SLAs, incident reporting, data governance, audit rights)
- Requiring vendors to disclose training data provenance and bias evaluation results for High-Risk systems
- Obtaining AI Review Committee approval before committing to any High-Risk AI procurement

### 5.3 AI Vendors

Vendors supplying AI systems to FMoH or its affiliated institutions are required to:

- Disclose the training data used to develop their systems and any known performance limitations
- Provide quarterly performance reports for deployed systems
- Report any identified safety issues or model failures within 24 hours of identification
- Cooperate with any FMoH-commissioned audit or bias evaluation
- Comply with all applicable provisions of the Nigeria Data Protection Act 2023

### 5.4 All Staff

All FMoH staff using AI systems are required to:

- Complete AI literacy training as provided by the eHealth Division
- Report concerns about AI system performance or unexpected outputs to their System Owner
- Never rely solely on AI outputs for High-Risk clinical decisions without human review
- Comply with all data protection obligations when inputting data into AI systems

---

## 6. Governance and Enforcement

This policy is owned by the Director, eHealth Division, and enforced through the FMoH AI Governance Operating Model.

Suspected policy violations shall be reported to the eHealth Division. Confirmed violations may result in:

- Suspension of the AI system in question
- Formal investigation by the AI Review Committee
- Disciplinary action for individuals responsible for the violation
- Termination of vendor contracts in cases of serious or repeated vendor non-compliance

---

## 7. Review and Update

This policy shall be reviewed annually by the eHealth Division and updated to reflect:

- Changes in Nigeria's legal and regulatory framework
- Material changes to the FMoH AI systems portfolio
- Developments in international AI governance standards
- Lessons learned from AI incidents or near-misses

---

## 8. Related Documents

- FMoH AI Systems Register
- AI Review Process and Approval Workflow
- FMoH AI Governance Operating Model
- AI Incident Response Policy
- Nigeria Data Protection Act 2023 (NDPA)
- WHO Guidance on Ethics and Governance of AI for Health (2021)
- NIST AI Risk Management Framework (AI RMF 1.0)

---

*Approved by the Honourable Minister of Health, Federal Republic of Nigeria.*  
*Effective: July 2026*

*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
