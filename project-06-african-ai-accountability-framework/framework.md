# Algorithmic Accountability Audit Framework
## For AI Systems in Sub-Saharan Africa

**Author:** Victor Eze Odoh  
**Version:** 2.0  
**Date:** June 2026  
**Licence:** CC BY 4.0 — free to use, adapt, and share with attribution

---

## Part 1 — Purpose

### 1.1 Why a Dedicated Framework for Sub-Saharan Africa?

Global AI governance frameworks — the EU AI Act, the NIST AI Risk Management Framework, the OECD AI Principles — represent serious and important contributions to the field. This framework does not compete with them. It builds on them.

But three structural realities of Sub-Saharan African public institutions create governance gaps that existing frameworks do not adequately address:

**Reality 1 — Institutional resource constraints**

Most global AI governance frameworks assume the deploying institution has: a dedicated compliance team, legal counsel with AI expertise, the contractual leverage to impose conditions on large international vendors, and the technical capacity to conduct independent model audits. Most Sub-Saharan African government ministries have none of these. A governance framework that requires them is not a framework — it is an aspiration.

This framework is designed to be applied by a policy officer, a civil society researcher, or a procurement official with governance knowledge but without ML engineering expertise. Every assessment criterion is answerable without access to the model's source code.

**Reality 2 — Donor-funded AI complexity**

A significant proportion of AI systems deployed in Sub-Saharan African public institutions are introduced through international donor programmes — USAID, GAVI, the World Bank, bilateral donors. These systems present unique accountability challenges: the vendor is often selected by the donor, not the government; accountability is fragmented across donor, implementing partner, and government; and when the programme ends, the system frequently continues to operate with no governance successor.

Existing frameworks assume a simple deployer-vendor accountability relationship. They do not address the three-way accountability dynamics of donor-funded AI.

**Reality 3 — Non-African training data**

AI systems deployed in Sub-Saharan Africa are frequently trained on datasets from North America, Europe, or urban African contexts. When deployed in rural African communities — which have different disease profiles, linguistic patterns, socioeconomic characteristics, and digital literacy levels — these systems systematically underperform for the populations they are intended to serve. This is not a hypothetical risk. It is a documented pattern across health AI, agricultural AI, and financial inclusion AI in African contexts.

Existing frameworks address training data bias in principle. This framework provides specific assessment criteria for auditing non-African training data in African deployment contexts.

### 1.2 What This Framework Assesses

This framework assesses **accountability structures** around AI systems — not the technical performance of models. It determines whether the governance conditions exist for an AI system to be deployed responsibly, monitored effectively, and corrected when it causes harm.

Technical performance evaluation is a necessary complement to this framework, not a substitute for it.

### 1.3 Scope

This framework applies to any AI system that:
- Makes or influences decisions that affect members of the public
- Is deployed by or through a public institution, or funded through public or donor resources
- Operates in a Sub-Saharan African context

It is most critical for high-risk systems — those making decisions in healthcare, social protection, education, agriculture, electoral administration, law enforcement, or financial inclusion.

---

## Part 2 — Audit Principles

The framework is grounded in eight principles. These principles inform the design of every assessment domain and criterion.

| # | Principle | What It Means in Practice |
|---|---|---|
| 1 | **Public Interest** | AI systems deployed in public contexts must serve the public good — not primarily the interests of vendors, donors, or deploying institutions |
| 2 | **Accountability** | Every AI system must have a named person responsible for its governance, performance, and consequences |
| 3 | **Transparency** | Affected people have the right to know when AI is involved in decisions about them, and to understand the basis of those decisions |
| 4 | **Human Oversight** | Humans must retain meaningful authority to review, challenge, and override AI outputs — particularly in high-risk contexts |
| 5 | **Equity** | AI systems must not systematically disadvantage any population group — with particular attention to rural communities, women, linguistic minorities, and people with low digital literacy |
| 6 | **Data Quality** | AI systems are only as good as the data they are trained on — data quality, representativeness, and documentation are governance prerequisites |
| 7 | **Community Impact** | The communities most affected by AI systems must have a voice in their governance — through transparency, complaint mechanisms, and meaningful participation |
| 8 | **Sustainability** | AI governance must be sustainable beyond the life of any individual project, donor programme, or vendor relationship |

---

## Part 3 — Audit Domains

The framework assesses AI systems across ten domains. Each domain addresses a distinct governance dimension.

| # | Domain | Core Governance Question |
|---|---|---|
| 1 | **Governance** | Are accountability structures formally established? |
| 2 | **Risk Management** | Are risks assessed, documented, and mitigated before and during deployment? |
| 3 | **Data Governance** | Is training and operational data documented, representative, and appropriately managed? |
| 4 | **Human Oversight** | Can humans review, challenge, and override AI outputs? |
| 5 | **Transparency** | Do affected people know AI is involved and what it does? |
| 6 | **Security** | Is the system protected against misuse, manipulation, and unauthorised access? |
| 7 | **Monitoring** | Is post-deployment performance tracked and reported? |
| 8 | **Incident Response** | Are AI failures detected, investigated, and remediated? |
| 9 | **Procurement** | Do vendor and donor contracts define AI-specific responsibilities? |
| 10 | **Public Trust** | Are complaint, appeal, and redress mechanisms accessible to affected communities? |

---

## Part 4 — Maturity Model

Rather than a simple pass/fail assessment, this framework uses a five-level maturity model. Maturity levels describe where an institution currently is — and provide a clear progression path toward stronger governance.

| Level | Name | Description |
|---|---|---|
| **1** | **Initial** | AI governance is absent or entirely ad hoc. No formal policies, roles, or processes exist. Governance depends on individual awareness rather than institutional structure. |
| **2** | **Developing** | Some governance practices exist but are inconsistently applied. Accountability is partially defined. Some documentation exists but is incomplete or not systematically maintained. |
| **3** | **Defined** | Governance policies and processes are formally documented and consistently applied. Accountability is clearly assigned. Review cycles are established and followed. |
| **4** | **Managed** | Governance is data-driven. Performance is actively monitored, measured against defined targets, and reported. Issues are identified proactively rather than reactively. |
| **5** | **Optimised** | Governance incorporates continuous improvement. Lessons learned from incidents and reviews are systematically fed back into policy and process. The institution actively contributes to sector-wide governance improvement. |

### Maturity by Domain

Each of the ten domains receives a separate maturity score (1–5). This produces a **maturity profile** — showing where governance is strong and where the most urgent improvement is needed.

**Example maturity profile (illustrative):**

```
Governance          ████░░░░░░  2
Risk Management     ███░░░░░░░  1
Data Governance     ███░░░░░░░  1
Human Oversight     █████░░░░░  3
Transparency        ████░░░░░░  2
Security            ████░░░░░░  2
Monitoring          ██░░░░░░░░  1
Incident Response   ██░░░░░░░░  1
Procurement         ███░░░░░░░  1
Public Trust        ███░░░░░░░  1
```

A maturity profile identifies not just overall governance quality but the specific domains requiring priority attention.

---

## Part 5 — Domain Assessments

### Domain 1 — Governance

**Core Question:** Are accountability structures formally established?

| Assessment Criterion | Level 1 | Level 3 | Level 5 |
|---|---|---|---|
| System Owner | No accountable person designated | Named System Owner formally assigned with documented responsibilities | System Owner embedded in institution's performance framework with AI-specific KPIs |
| AI Policy | No AI governance policy exists | Formal AI governance policy approved and in effect | Policy reviewed annually and updated based on incident learnings |
| Review Cycle | No review has been conducted | Formal review cycle established and followed | Reviews are data-driven and findings are published |
| Board/Leadership Visibility | AI systems are invisible to senior leadership | Senior leadership receives periodic AI governance reports | Leadership actively engages with AI governance as a strategic priority |

**Key questions for auditors:**
- Who is the named accountable person for this system? Can they be identified by name and title?
- What happens to accountability when the project manager leaves or the donor programme closes?
- Has senior leadership ever received a report on this system's performance or risks?

---

### Domain 2 — Risk Management

**Core Question:** Are risks assessed, documented, and mitigated before and during deployment?

| Assessment Criterion | Level 1 | Level 3 | Level 5 |
|---|---|---|---|
| Pre-deployment risk assessment | No risk assessment conducted | Formal risk assessment completed before deployment | Risk assessment updated annually and after material system changes |
| Risk register | No risk register exists | Risk register maintained with likelihood, impact, and mitigation for each risk | Risk register actively managed with residual risk tracking |
| High-risk classification | System has not been classified by risk level | System risk tier formally assigned and documented | Risk classification reviewed when system scope changes |
| Mitigation implementation | No mitigations in place | Key mitigations documented and implemented | Mitigation effectiveness is monitored and reported |

**Key questions for auditors:**
- Was a risk assessment conducted before this system was deployed?
- Who conducted it — the vendor, the donor, or the government institution?
- Has the risk assessment been updated since initial deployment?

---

### Domain 3 — Data Governance

**Core Question:** Is training and operational data documented, representative, and appropriately managed?

| Assessment Criterion | Level 1 | Level 3 | Level 5 |
|---|---|---|---|
| Training data documentation | Training data composition is unknown or undisclosed | Training data sources, size, and date range are documented | Training data documentation includes demographic and geographic representation analysis |
| African dataset representation | System is trained entirely on non-African data | Training data includes African data but representation gaps are acknowledged | Training data is validated as representative of the specific African deployment population |
| Data quality monitoring | No data quality monitoring exists | Data quality is monitored and gaps are flagged to system users | Data quality issues trigger automatic alerts and defined responses |
| Data protection compliance | No data protection assessment conducted | Data processing is assessed against national data protection law | Data protection compliance is reviewed annually and documented |

**Key questions for auditors:**
- Where was the training data collected? Is any of it from the country or region where the system is deployed?
- Has the vendor disclosed the demographic and geographic composition of the training dataset?
- What happens to personal data collected by this system? Where is it stored and for how long?

---

### Domain 4 — Human Oversight

**Core Question:** Can humans review, challenge, and override AI outputs?

| Assessment Criterion | Level 1 | Level 3 | Level 5 |
|---|---|---|---|
| Oversight protocol | No oversight protocol exists; AI operates autonomously | Documented oversight protocol specifies who reviews outputs, when, and how | Oversight protocol is tested, audited, and refined based on review quality data |
| Override authority | Human reviewers cannot override AI outputs | Human reviewers have formal authority to override without requiring justification | Override decisions are logged and analysed to identify model improvement opportunities |
| Reviewer capacity | Reviewers have no training relevant to AI outputs | Reviewers receive regular training on interpreting and challenging AI outputs | Reviewer capacity is assessed and training effectiveness is measured |
| Autonomous operation safeguards | High-risk AI operates autonomously with no human review | Autonomous operation limited to low-risk use cases with documented safeguards | All autonomous operations are logged and subject to retrospective human review |

**Key questions for auditors:**
- Is there a human being who reviews this system's outputs before they are acted upon?
- Does that person have the training, time, and authority to meaningfully challenge the AI's recommendation?
- Has a human ever overridden the system? If not — is that because the system is always right, or because override is discouraged?

---

### Domain 5 — Transparency

**Core Question:** Do affected people know AI is involved and what it does?

| Assessment Criterion | Level 1 | Level 3 | Level 5 |
|---|---|---|---|
| Public disclosure | System existence is not publicly disclosed | System existence and general purpose are publicly disclosed | Detailed system description including known limitations is publicly available |
| User notification | Affected people receive no notification of AI involvement | AI involvement is disclosed to affected people in plain language | Disclosure is designed for the literacy and language profile of the affected community |
| Language accessibility | Information only in official or foreign language | Information available in primary local language(s) | Information available in all languages spoken by significant portions of the affected population |
| Decision explanation | No explanation of AI outputs is available | Explanations available on request | Proactive explanation provided for all consequential AI decisions |

**Key questions for auditors:**
- Do the people most affected by this system know it exists?
- Is the disclosure designed for someone with low literacy in a rural community — or only for someone who reads English and has internet access?
- Can an affected person find out why the AI system produced the output it did about them?

---

### Domain 6 — Security

**Core Question:** Is the system protected against misuse, manipulation, and unauthorised access?

| Assessment Criterion | Level 1 | Level 3 | Level 5 |
|---|---|---|---|
| Access controls | No formal access controls | Role-based access controls documented and implemented | Access controls audited regularly and access logs reviewed |
| Model integrity | No controls to detect model tampering or manipulation | Model version control in place; changes require authorisation | Model integrity monitoring detects anomalous outputs that may indicate manipulation |
| Data security | No data security assessment conducted | Data security assessed and basic protections implemented | Data security reviewed annually; encryption at rest and in transit confirmed |
| Misuse monitoring | No monitoring for misuse of AI outputs | Defined prohibited uses documented and communicated to all users | Misuse detection monitoring in place with defined escalation procedures |

**Key questions for auditors:**
- Who has access to this system and its outputs? Is access controlled and logged?
- Has the system or its underlying data ever been accessed without authorisation?
- Is there monitoring to detect if the system is being used for purposes outside its intended scope?

---

### Domain 7 — Monitoring

**Core Question:** Is post-deployment performance tracked and reported?

| Assessment Criterion | Level 1 | Level 3 | Level 5 |
|---|---|---|---|
| Performance metrics | No performance metrics defined | Core performance metrics defined and tracked (accuracy, error rates) | Performance metrics include equity metrics disaggregated by population group |
| Monitoring frequency | No monitoring occurs | Performance reviewed quarterly | Continuous automated monitoring with defined alert thresholds |
| Reporting | No performance reports produced | Quarterly performance reports produced for system owner | Performance reports shared with AI Review Committee and published in summary form |
| Model drift detection | No model drift detection | Annual performance review identifies significant drift | Automated drift detection triggers retraining assessment |

**Key questions for auditors:**
- How does the institution know whether this system is still performing as intended?
- Is performance monitored separately for different population groups — rural vs urban, men vs women, different regions?
- When was the last performance review, and what did it find?

---

### Domain 8 — Incident Response

**Core Question:** Are AI failures detected, investigated, and remediated?

| Assessment Criterion | Level 1 | Level 3 | Level 5 |
|---|---|---|---|
| Incident definition | No definition of what constitutes an AI incident | AI incident defined and communicated to all staff | Incident classification includes severity tiers with differentiated response timelines |
| Reporting mechanism | No mechanism for reporting AI incidents | Formal incident reporting mechanism accessible to staff | Incident reporting mechanism accessible to affected community members as well as staff |
| Investigation process | Incidents are not investigated | All reported incidents are formally investigated with documented findings | Root cause analysis is standard for all High and Critical incidents |
| Remediation and learning | No remediation process | Remediation implemented for confirmed incidents | Lessons learned are systematically applied to other systems in the portfolio |

**Key questions for auditors:**
- If this system caused harm to a patient, a citizen, or a community — what would happen?
- Is there a process for staff to report concerns about AI outputs without fear of consequences?
- Has any incident involving this system ever been investigated? What was found?

---

### Domain 9 — Procurement

**Core Question:** Do vendor and donor contracts define AI-specific responsibilities?

| Assessment Criterion | Level 1 | Level 3 | Level 5 |
|---|---|---|---|
| Vendor contract | No vendor contract exists or contract has expired | Vendor contract in place with AI-specific performance obligations | Contract includes bias evaluation requirements, incident reporting SLAs, and audit rights |
| Training data disclosure | Vendor has not disclosed training data | Vendor has disclosed training data sources and composition | Vendor provides regular training data updates and bias evaluation results |
| Donor accountability | No donor accountability conditions for AI | Donor programme includes AI governance conditions | Donor conditions address post-programme governance sustainability |
| Post-programme governance | No plan for governance after donor programme ends | Transition plan exists for pos
