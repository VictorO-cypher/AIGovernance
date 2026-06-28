# Incident Response Timeline — FMoH-INC-2026-001

**Incident:** MamaAlert Maternal Risk Scoring Tool — Systematic Misclassification  
**System:** FMoH-AI-003  
**Incident Opened:** 4 September 2026  
**Target Resolution:** 4 December 2026 (90 days)  

---

## Phase 1 — Detection and Containment (Week 1: 4–11 September 2026)

| Date | Action | Owner | Status |
|---|---|---|---|
| 4 Sep | AI Governance Lead classifies incident as Critical — Patient Safety | AI Governance Lead | ✅ Complete |
| 4 Sep | Director, eHealth Division notified | AI Governance Lead | ✅ Complete |
| 5 Sep | MamaAlert suspended across all 12 active states | Director, eHealth Division | ✅ Complete |
| 5 Sep | Suspension notifications sent to all state PHCDAs, CHEW supervisors, NPHCDA, DabaDoc, and USAID | AI Governance Lead | ✅ Complete |
| 5 Sep | CHEWs instructed to revert to manual clinical risk assessment protocols | NPHCDA | ✅ Complete |
| 5 Sep | AI Review Committee extraordinary meeting convened | Director, eHealth Division (Chair) | ✅ Complete |
| 5 Sep | Incident investigation team established | AI Review Committee | ✅ Complete |
| 6 Sep | DabaDoc formally notified of incident and required to preserve all system logs and model documentation | FMoH Legal Adviser | ✅ Complete |
| 6 Sep | USAID Nigeria health programme office notified of incident and suspension | Director, eHealth Division | ✅ Complete |
| 8 Sep | Clinical review of random sample (200 cases) from Northwest states completed — 23% misclassification rate confirmed | Clinical Services Representative | ✅ Complete |
| 8 Sep | Estimate of total patient exposure communicated to AI Review Committee (~4,200 active cases; ~180,000 historical) | AI Governance Lead | ✅ Complete |
| 10 Sep | Nigeria Data Protection Commission notified (NDPA 2023 — data processing linked to patient harm) | Data Protection Officer | ✅ Complete |
| 11 Sep | Manual clinical re-assessment protocol confirmed operational in all 12 states | NPHCDA | ✅ Complete |

---

## Phase 2 — Investigation (Weeks 2–4: 12 September – 3 October 2026)

| Date | Action | Owner | Status |
|---|---|---|---|
| 12 Sep | DabaDoc requested to provide: training data composition report, model architecture documentation, performance evaluation results, and all previous internal bias assessments | FMoH Legal Adviser | ✅ Complete |
| 15 Sep | Independent clinical AI expert engaged to lead technical investigation | AI Review Committee | ✅ Complete |
| 18 Sep | DabaDoc submits training data composition report — confirms training data was 94% urban Southwest Nigeria facility data | DabaDoc | ✅ Complete |
| 19 Sep | Training data bias confirmed as primary root cause — model systematically undertrained on Northwest Nigerian patient risk profile | Independent Expert | ✅ Complete |
| 22 Sep | Historical case review initiated — clinical teams in Northwest states begin reviewing MamaAlert classifications for women who subsequently experienced adverse maternal outcomes | NPHCDA / Clinical Services | 🔄 In Progress |
| 25 Sep | Root cause analysis draft completed and shared with AI Review Committee | Independent Expert / AI Governance Lead | ✅ Complete |
| 30 Sep | DabaDoc presents remediation proposal to AI Review Committee: retraining plan using Northwest Nigerian data, independent bias evaluation before redeployment | DabaDoc | ✅ Complete |
| 3 Oct | AI Review Committee approves root cause analysis and requests final RCA report | AI Review Committee | ✅ Complete |

---

## Phase 3 — Remediation Planning (Weeks 5–8: 4–31 October 2026)

| Date | Action | Owner | Status |
|---|---|---|---|
| 4 Oct | FMoH Legal team initiates vendor contract renegotiation — new AI-specific clauses including training data disclosure, bias evaluation obligations, performance SLAs, incident reporting, and liability provisions | FMoH Legal / Procurement | 🔄 In Progress |
| 7 Oct | NPHCDA and clinical teams begin structured data collection in Northwest states to support model retraining | NPHCDA | 🔄 In Progress |
| 10 Oct | Communication plan approved — proactive briefing for state health commissioners in 12 active states | Director, eHealth Division | ✅ Complete |
| 10 Oct | State health commissioners briefed on incident, suspension, and remediation plan | Director, eHealth Division | ✅ Complete |
| 14 Oct | Historical case review — interim findings: 17 additional cases identified in Northwest states where MamaAlert Low/Medium classification preceded adverse maternal outcome; causal link under clinical assessment | NPHCDA / Clinical Services | 🔄 In Progress |
| 15 Oct | CHEW capacity building programme designed — training curriculum for interpreting and challenging AI risk scores | eHealth Division / NPHCDA | 🔄 In Progress |
| 20 Oct | Outcome tracking system designed — links MamaAlert classifications to actual maternal outcomes for continuous performance monitoring post-redeployment | AI Governance Lead / NHMIS | 🔄 In Progress |
| 25 Oct | Independent bias evaluator procured — independent organisation to validate retrained model before redeployment approval | AI Review Committee | 🔄 In Progress |
| 31 Oct | Vendor contract renegotiation — target completion | FMoH Legal / Procurement | ⬜ Pending |

---

## Phase 4 — Remediation Implementation (Weeks 9–12: 1 November – 4 December 2026)

| Date | Action | Owner | Status |
|---|---|---|---|
| 1 Nov | DabaDoc begins model retraining incorporating Northwest Nigerian clinical data | DabaDoc | ⬜ Pending |
| 7 Nov | CHEW capacity building training delivered in all 12 states | eHealth Division / NPHCDA | ⬜ Pending |
| 14 Nov | Outcome tracking system implemented in DHIS2 — links MamaAlert classifications to maternal outcome records | NHMIS / eHealth Division | ⬜ Pending |
| 20 Nov | DabaDoc submits retrained model for independent bias evaluation | DabaDoc | ⬜ Pending |
| 28 Nov | Independent bias evaluation completed — results presented to AI Review Committee | Independent Evaluator | ⬜ Pending |
| 30 Nov | AI Review Committee reviews bias evaluation results and makes redeployment recommendation to Permanent Secretary | AI Review Committee | ⬜ Pending |
| 4 Dec | Permanent Secretary decision on redeployment | Permanent Secretary | ⬜ Pending |

---

## Phase 5 — Post-Incident Review and Lessons Learned (Week 13+: December 2026)

| Action | Owner | Target Date |
|---|---|---|
| Full incident post-mortem report completed and shared with AI Review Committee | AI Governance Lead | 18 Dec 2026 |
| Lessons learned communicated to all FMoH System Owners | AI Governance Lead | 18 Dec 2026 |
| Historical case review — final report on adverse outcomes potentially linked to MamaAlert misclassification | NPHCDA / Clinical Services | 31 Dec 2026 |
| Annual AI Governance Report — MamaAlert incident included as case study | Director, eHealth Division | Jan 2027 |
| Policy update — mandatory pre-deployment bias evaluation added as explicit gate condition for all High Risk AI systems | AI Governance Lead | Jan 2027 |
| WHO Nigeria country office briefed on incident and FMoH response | Director, eHealth Division | Jan 2027 |

---

## Incident Status Summary

| Phase | Status |
|---|---|
| Phase 1 — Detection and Containment | ✅ Complete |
| Phase 2 — Investigation | ✅ Substantially complete; historical review ongoing |
| Phase 3 — Remediation Planning | 🔄 In Progress |
| Phase 4 — Remediation Implementation | ⬜ Pending |
| Phase 5 — Post-Incident Review | ⬜ Pending |

**Overall Incident Status: Under active management**  
**No patient safety risk from active system** (system suspended)  
**Manual clinical protocols operational in all 12 states**

---

*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
