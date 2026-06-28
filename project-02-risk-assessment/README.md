# Project 02: AI Risk Assessment & Governance Review Pack

## Scenario

**System Under Review:** HealthLine Nigeria AI Triage Chatbot (FMoH-AI-005)  
**Organisation:** Federal Ministry of Health (FMoH), Nigeria  
**Use Case:** Autonomous AI-powered patient triage via SMS and WhatsApp — directing members of the public to self-care, primary care, or emergency services

Following the inventory and classification exercise in Project 01, the HealthLine Nigeria AI Triage Chatbot was identified as the highest-risk system in the FMoH portfolio. It received a NIST AI RMF maturity score of 0.0 — the only system in the inventory with a complete absence of governance controls — and was classified as High Risk under EU AI Act standards.

The system operates autonomously, making healthcare triage recommendations directly to the general public with no mandatory human review at the point of decision. No accountable owner has been formally assigned within the FMoH eHealth Division. No adverse event reporting mechanism exists.

The Director of the eHealth Division has requested a formal governance review before a Ministerial decision on the system's future. The review covers:

- A structured risk assessment identifying harms, likelihood, and impact
- Proposed mitigation measures and residual risk position
- A governance review memo addressed to the Honourable Minister of Health

---

## What This Project Demonstrates

- Ability to move from AI system classification to structured risk analysis
- Understanding of AI-specific harms in a public health context — not just data protection risks, but autonomous decision-making, health equity, and accountability gaps
- Capacity to define what meaningful human oversight looks like for a patient-facing AI system
- Ability to communicate governance analysis to senior non-technical decision-makers
- Knowledge of the NIST AI RMF Map and Measure functions applied to an African public sector context

---

## Artefacts

| File | Description |
|---|---|
| `risk-assessment.md` | Full structured risk assessment with likelihood/impact matrix and mitigation measures |
| `governance-review-memo.md` | Executive memo to the Honourable Minister of Health recommending a governance decision |

---

## How the Artefacts Connect

The risk assessment is the analytical foundation. It identifies risks, assesses them on a consistent likelihood/impact scale, applies mitigation measures, and arrives at a residual risk position. This is technical-governance work.

The governance review memo translates that analysis into the format a Minister needs: clear summary, public health implications, a defined recommendation, and an actionable decision request. It avoids technical jargon while preserving analytical rigour.

Together they reflect how governance actually works in practice — rigorous analysis feeding clear decisions, not analysis as a substitute for decisions.

---

## Frameworks Applied

- **NIST AI RMF** — Map (risk identification and contextualisation) and Measure (risk analysis) functions
- **EU AI Act** — Article 9 (risk management system), Article 14 (human oversight), Article 13 (transparency), Article 52 (AI disclosure obligations)
- **WHO Guidance on Ethics and Governance of AI for Health (2021)** — principles of transparency, accountability, and inclusiveness
- **Nigeria Data Protection Act 2023 (NDPA)** — data processing obligations for sensitive health data
- **ISO 31000** — Risk assessment structure and terminology
