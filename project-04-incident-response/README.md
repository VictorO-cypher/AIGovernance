# Project 04: AI Incident Response & Regulatory Escalation

## Scenario

**Organisation:** Federal Ministry of Health (FMoH), Nigeria  
**Incident:** MamaAlert Maternal Risk Scoring Tool (FMoH-AI-003) is found to systematically misclassify high-risk pregnancies in rural Northern Nigerian communities as Low or Medium risk — resulting in missed referrals and at least two documented cases of preventable maternal near-misses.

The incident is detected in September 2026, three months after FMoH established its formal AI governance programme. It demonstrates that governance matters even for systems already in production — and that how an institution responds to an AI failure is as important as preventing it.

---

## What This Project Demonstrates

- Understanding of AI governance as an ongoing discipline, not a point-in-time compliance exercise
- Knowledge of how to structure an AI incident response — detection, triage, containment, investigation, remediation, and review
- Awareness of regulatory escalation obligations under Nigeria's Data Protection Act 2023 and WHO AI ethics guidance
- Practical understanding of the NIST AI RMF Manage function
- Ability to apply root cause analysis methodology to AI systems in a public health context
- Understanding of how bias in AI training data produces real-world health equity harms

---

## Artefacts

| File | Description |
|---|---|
| `incident-scenario.md` | Incident description, context, and detection narrative |
| `incident-response-timeline.md` | Week-by-week incident response and remediation timeline |
| `root-cause-analysis.md` | Structured RCA and corrective action plan |

---

## Why This Project Matters

AI incidents in healthcare are not hypothetical. Biased diagnostic tools, unvalidated risk scores, and opaque automated recommendations have already produced patient harm in African and global health contexts.

The MamaAlert incident illustrates a pattern that is common across AI deployments in the Global South:

- A system developed primarily on urban or Western data is deployed in rural or underserved contexts without performance validation
- The performance gap is not monitored because no monitoring framework exists
- By the time harm is identified, the system has been operating for years

Good incident response — fast containment, honest investigation, structural remediation — determines whether a governance failure becomes a recoverable problem or a public health scandal. This project simulates what a well-prepared institution does when an AI system causes harm.

---

## Frameworks Applied

- **NIST AI RMF** — Manage function (incident response, recovery, feedback loops)
- **WHO Guidance on Ethics and Governance of AI for Health (2021)** — accountability and transparency obligations
- **Nigeria Data Protection Act 2023 (NDPA)** — breach notification and data governance obligations
- **ISO/IEC 27035** — Incident management principles (adapted for AI context)
- **EU AI Act** — Articles 9, 12, 17, 73 (risk management, logging, post-market monitoring, incident reporting — applied as international benchmark)
- 
