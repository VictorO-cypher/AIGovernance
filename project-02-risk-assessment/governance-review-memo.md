# Governance Review Memo

**TO:** Honourable Minister of Health, Federal Republic of Nigeria  
**FROM:** Director, eHealth Division, Federal Ministry of Health  
**DATE:** June 2026  
**RE:** HealthLine Nigeria AI Triage Chatbot — Governance Review and Ministerial Decision Request  
**CLASSIFICATION:** Sensitive — For Ministerial Decision  

---

## 1. Purpose

This memo presents the findings of a formal governance review of the HealthLine Nigeria AI Triage Chatbot (FMoH-AI-005), currently in pilot deployment in the Federal Capital Territory. It requests a Ministerial decision on the system's continued operation pending implementation of minimum governance controls.

---

## 2. Background

The HealthLine Nigeria AI Triage Chatbot was deployed in March 2024 by the eHealth Division in partnership with Helium Health (Lagos) as part of FMoH's digital health access strategy. The system provides automated symptom assessment and triage guidance to members of the public via SMS and WhatsApp, directing users to self-care, primary care, or emergency services.

The pilot has reached an estimated user base of several thousand FCT residents. The system operates without human clinical review of individual recommendations.

A routine AI system inventory conducted in June 2026 identified this system as the highest-risk AI deployment in the FMoH portfolio. A formal governance review was immediately commissioned.

---

## 3. Key Findings

The governance review identified six material risks. Two are rated Critical — the highest possible rating:

**Finding 1 — Critical: Risk of Incorrect Emergency Triage**

The system is making autonomous emergency care decisions for members of the public based on text-based symptom descriptions, with no clinical review before recommendations are delivered. Symptom assessment via text is inherently limited — patients may not accurately describe symptoms, and emergency presentations are frequently atypical.

An incorrect Self-care recommendation for a patient experiencing a stroke, cardiac event, or obstetric haemorrhage could directly delay life-saving treatment. In Nigeria's healthcare context — where emergency response times are already constrained — this delay could be fatal. No safety-netting advice is confirmed in current system outputs.

**Finding 2 — Critical: No Accountable Owner**

No individual within FMoH has been formally designated as the accountable owner for this system. The system is currently operating without a responsible principal. If a patient is harmed, there is no defined accountability chain, no investigation process, and no response capability within FMoH.

**Finding 3 — High: Algorithmic Bias Risk**

The system's performance has not been evaluated on Nigerian patient populations. Evidence from comparable AI health tools deployed in African contexts suggests that systems trained without localised data systematically underperform for rural users, low-literacy users, and users communicating in Pidgin or local languages. If the system is less accurate for these populations, it is failing the patients who need accessible triage guidance most.

**Finding 4 — High: Vendor Contract Does Not Address AI Safety**

The current contract with Helium Health contains no AI-specific performance standards, no incident reporting requirements, and no liability provisions for recommendation errors. FMoH has no contractual basis to hold the vendor accountable if the system causes harm.

---

## 4. What Is Working

The system's intent — expanding access to health guidance for FCT residents who cannot easily access primary care — is sound and aligned with FMoH's digital health strategy. Early user engagement data suggests strong uptake. The underlying technology from Helium Health is operationally functional.

The governance failures identified in this review are not arguments against AI-assisted triage as a tool. They are arguments for ensuring it is deployed responsibly before being scaled.

---

## 5. Recommendation

The eHealth Division recommends **conditional suspension** of the system's autonomous operation, with resumption permitted upon satisfaction of five minimum conditions:

| Condition | Responsible Party | Timeline |
|---|---|---|
| Appoint a named System Owner within eHealth Division | Director, eHealth Division | 7 days |
| Implement safety-netting messages and red-flag escalation for emergency symptoms | Helium Health / eHealth Division | 30 days |
| Introduce human clinical review for all Emergency classifications | eHealth Division / NPHCDA | 30 days |
| Update vendor contract with AI-specific performance and accountability clauses | FMoH Legal / Procurement | 45 days |
| Confirm and document AI disclosure to all users | Helium Health | 14 days |

Upon satisfaction of these conditions, the system may resume operation under a formal governance framework with quarterly Ministerial reporting.

---

## 6. Ministerial Decision Requested

The Honourable Minister is respectfully requested to:

1. **Approve** the conditional suspension of the HealthLine Nigeria AI Triage Chatbot pending implementation of the minimum governance conditions outlined above

2. **Direct** the Director of eHealth Division to submit a governance remediation report within 45 days confirming the status of each condition

3. **Note** that this review has also identified four other High Risk AI systems in the FMoH portfolio requiring governance attention, details of which will be presented in a separate briefing

---

## 7. Wider Implications

This review has broader significance beyond the HealthLine system. It is the first formal AI governance review conducted within FMoH. It has revealed that the Ministry currently has no systematic framework for governing AI systems across its departments, affiliated hospitals, and donor-funded programmes.

The eHealth Division recommends that the Minister approve the development of an **FMoH AI Governance Policy** — a lightweight framework establishing minimum standards for AI system accountability, risk assessment, human oversight, and incident reporting across all FMoH AI deployments. This would position Nigeria's Federal Ministry of Health as a regional leader in responsible health AI governance, aligned with WHO guidance and increasingly referenced by international health donors.

A policy proposal can be prepared for Ministerial consideration within 60 days.

---

*Prepared by the eHealth Division, Federal Ministry of Health, Nigeria.*  
*Governance review conducted in accordance with NIST AI Risk Management Framework (AI RMF 1.0) and WHO Guidance on Ethics and Governance of AI for Health (2021).*

*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
