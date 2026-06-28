# Root Cause Analysis — FMoH-INC-2026-001

**Incident:** MamaAlert Maternal Risk Scoring Tool — Systematic Misclassification  
**System:** FMoH-AI-003  
**RCA Lead:** Independent Clinical AI Expert (engaged by AI Review Committee)  
**RCA Completed:** 3 October 2026  
**Approved by:** AI Review Committee  

---

## 1. Incident Summary

The MamaAlert Maternal Risk Scoring Tool was found to systematically misclassify pregnant women in rural Northwest Nigerian communities as Low or Medium maternal mortality risk when clinical evidence indicated High Risk. The misclassification resulted in missed specialist referrals, contributing to at least two confirmed near-miss obstetric emergencies and a further 17 cases under clinical assessment.

The system was deployed across 12 states from 2021–2026 without a formal governance review, bias evaluation, or post-deployment performance monitoring framework. The bias was undetected for approximately four years.

---

## 2. RCA Methodology

This analysis applies the **5 Whys methodology** combined with an **Ishikawa (fishbone) causal analysis** to identify the root cause, contributing causes, and systemic enablers of the incident.

The investigation drew on:
- DabaDoc training data composition report
- Model architecture and feature importance documentation
- Clinical review of 200 sampled MamaAlert outputs from Northwest states
- Interviews with CHEW supervisors in Kano and Katsina states
- Review of the original programme design documents (2020)
- Historical outcome data from NHMIS (partial)

---

## 3. Five Whys Analysis

**Why did MamaAlert misclassify high-risk pregnancies in Northwest Nigeria?**

> Because the model assigned insufficient weight to risk factors that are disproportionately prevalent in rural Northwest Nigerian patients — including grand multiparity, severe anaemia, rural LGA location, and absence of prior facility-based antenatal care.

**Why did the model underweight these risk factors?**

> Because the model was trained on data from urban Southwest Nigerian health facilities (Lagos, Abuja, Port Harcourt), where these risk factors are less prevalent. The model learned risk associations from the population it was trained on — which did not represent the population it was later deployed to serve.

**Why was the model trained only on urban Southwest Nigerian data?**

> Because at the time of development (2019–2020), digital health records with sufficient completeness for model training were only reliably available from urban tertiary and secondary facilities. Rural Northwest facilities had incomplete or paper-based records. No deliberate decision was made to exclude Northwest data — it was structurally unavailable.

**Why was the model deployed in Northwest states despite being trained on non-representative data?**

> Because no formal bias evaluation was required or conducted before deployment. The programme's governance framework (designed by USAID and DabaDoc in 2020) did not include a requirement to validate model performance across geographic or demographic subgroups before rollout. No FMoH governance standard existed at the time to mandate such evaluation.

**Why was the bias not identified after deployment?**

> Because no post-deployment performance monitoring framework was in place. No outcome tracking linked MamaAlert classifications to actual maternal outcomes. No mechanism existed for CHEWs to systematically report cases where the AI classification appeared inconsistent with their clinical assessment. The system produced outputs that were accepted without audit until the new governance framework triggered the first formal performance review in September 2026.

---

## 4. Root Cause

**Root Cause: Training data not representative of deployment population**

MamaAlert's model was trained on a dataset that was 94% urban Southwest Nigerian facility data. The patient population in rural Northwest Nigeria differs materially in risk factor prevalence, clinical presentation, and socioeconomic profile. The model systematically underestimated risk for patients whose risk profile fell outside the distribution it was trained on.

This is a training data bias of the type known as **distribution shift** or **covariate shift** — the statistical properties of the deployment population differ from those of the training population, causing the model to perform poorly in the deployment context.

---

## 5. Contributing Causes

### Contributing Cause 1 — No Pre-Deployment Bias Evaluation

No bias evaluation was conducted before MamaAlert was deployed in Northwest states. A geographic and demographic performance evaluation would have identified the training data gap and the prediction accuracy disparity between Southwest and Northwest patient populations before deployment.

**What should have happened:** A mandatory bias evaluation assessing model performance across geographic zones, urbanicity, age groups, and parity levels should have been conducted and reviewed before state-level rollout.

---

### Contributing Cause 2 — No Post-Deployment Outcome Tracking

No system was implemented to link MamaAlert risk classifications to actual maternal outcomes. Without outcome tracking, it was impossible to detect whether the model's predictions were accurate or to identify whether specific patient subgroups were being systematically misclassified.

**What should have happened:** An outcome tracking system — linking antenatal MamaAlert classifications to delivery outcomes recorded in DHIS2 — should have been implemented from the outset. Quarterly performance reports should have compared predicted risk distributions to actual adverse outcome rates by state and LGA.

---

### Contributing Cause 3 — CHEWs Lacked Capacity to Challenge AI Outputs

Community Health Extension Workers were trained to enter patient data and act on MamaAlert outputs. They were not trained to recognise when an AI classification appeared inconsistent with their clinical observation, or to report such discrepancies through a formal channel. In effect, the human oversight layer was nominal rather than substantive.

**What should have happened:** CHEWs should have received training on the limitations of AI risk scoring, including explicit guidance to escalate cases where the AI classification appeared inconsistent with their clinical assessment. A formal discrepancy reporting mechanism should have been established.

---

### Contributing Cause 4 — Vendor Contract Did Not Include Performance Obligations

The contract with DabaDoc contained no AI-specific performance obligations — no accuracy benchmarks, no bias evaluation requirements, no incident reporting obligations, and no requirement to disclose training data composition. DabaDoc had no contractual obligation to monitor, report, or remediate performance issues post-deployment.

**What should have happened:** The vendor contract should have required DabaDoc to: disclose training data composition; conduct and share bias evaluations; provide quarterly performance reports; report identified performance issues within 24 hours; and cooperate with independent audits.

---

### Contributing Cause 5 — No FMoH AI Governance Framework (Pre-July 2026)

Prior to the establishment of FMoH's AI governance programme in July 2026, no institutional framework existed to require bias evaluations, mandate performance monitoring, or establish accountability for AI system outcomes. The absence of governance infrastructure meant that none of the controls that would have detected or prevented this incident were in place.

**What should have happened:** An AI governance framework — including minimum standards for pre-deployment evaluation, post-deployment monitoring, and incident reporting — should have been in place before any AI system was deployed in a clinical context.

---

## 6. Ishikawa Causal Analysis Summary

```
                    PATIENT MISCLASSIFICATION
                           (Effect)
                              │
        ┌─────────────────────┼─────────────────────┐
        │                     │                     │
   TRAINING DATA          PROCESS               GOVERNANCE
        │                     │                     │
 94% urban SW data    No bias evaluation     No FMoH AI policy
 No NW representation No outcome tracking    No vendor obligations
 Distribution shift   Nominal CHEW oversight No monitoring mandate
```

---

## 7. Timeline of Missed Opportunities

| Year | Event | Missed Opportunity |
|---|---|---|
| 2019–2020 | MamaAlert developed using urban SW Nigerian data | Bias evaluation not required; geographic representation not assessed |
| 2021 | MamaAlert deployed in Southwest states | No performance baseline established |
| 2022 | Deployment extended to Northwest states | No geographic performance validation before Northwest rollout |
| 2022–2026 | System active in 12 states | No outcome tracking; no performance monitoring; no CHEW reporting mechanism |
| Aug 2026 | First System Performance Report submitted under new governance framework | Anomaly detected — referral rate disparity identified |
| Sep 2026 | Clinical review confirms misclassification and near-miss cases | Incident confirmed and system suspended |

---

## 8. Corrective Action Plan

### Immediate Actions (Complete)
- ✅ System suspended across all 12 states
- ✅ Manual clinical protocols reinstated
- ✅ Incident investigation initiated
- ✅ Vendor required to preserve all logs and model documentation

### Short-Term Actions (Target: December 2026)

| Action | Owner | Target |
|---|---|---|
| Model retrained incorporating Northwest Nigerian clinical data | DabaDoc | Nov 2026 |
| Independent bias evaluation of retrained model | Independent Evaluator | Nov 2026 |
| CHEW capacity building programme delivered across 12 states | eHealth Division / NPHCDA | Nov 2026 |
| Outcome tracking system implemented in DHIS2 | NHMIS / eHealth Division | Nov 2026 |
| Vendor contract renegotiated with AI-specific clauses | FMoH Legal / Procurement | Oct 2026 |
| Redeployment approved by Permanent Secretary (conditional on bias evaluation results) | Permanent Secretary | Dec 2026 |

### Systemic Actions (Target: January 2027)

| Action | Owner | Target |
|---|---|---|
| FMoH Responsible AI Policy updated — mandatory pre-deployment bias evaluation added as gate condition for all High Risk AI systems | AI Governance Lead | Jan 2027 |
| Bias evaluation methodology standardised and published for use across FMoH AI portfolio | AI Governance Lead | Jan 2027 |
| All existing High Risk AI systems scheduled for retrospective bias evaluation | AI Review Committee | Jan 2027 |
| Lessons learned communicated to USAID Nigeria, WHO Nigeria, and Africa CDC | Director, eHealth Division | Jan 2027 |
| Incident published as anonymised case study in FMoH Annual AI Governance Report | Director, eHealth Division | Jan 2027 |

---

## 9. Lessons Learned

**Lesson 1 — Geographic representation in training data is not optional for national health AI systems.**  
Nigeria's health system serves populations with materially different disease profiles, risk factors, and socioeconomic characteristics across its six geopolitical zones. Any AI system deployed nationally must be evaluated for performance across these zones before deployment — not after.

**Lesson 2 — Nominal human oversight is not meaningful human oversight.**  
CHEWs were present at every interaction but lacked the training and authority to challenge AI outputs. Governance frameworks must ensure that human reviewers have the capacity, training, and formal authority to override AI recommendations — otherwise the oversight is decoration.

**Lesson 3 — Outcome tracking is not optional for clinical AI systems.**  
An AI system that makes clinical recommendations but does not track whether those recommendations led to good or bad outcomes cannot be improved, cannot be held accountable, and cannot detect its own failures. Outcome tracking must be a deployment requirement, not an afterthought.

**Lesson 4 — Governance frameworks detect what monitoring systems cannot.**  
This incident was identified not by clinical surveillance or patient complaints, but by the first formal performance report submitted under FMoH's new governance framework. Governance infrastructure — registers, review cycles, performance reporting — is the early warning system for AI failures.

**Lesson 5 — Vendor contracts must reflect AI risk.**  
A vendor supplying an AI system that influences clinical decisions must have contractual obligations proportionate to that risk. Standard procurement contracts are not designed for AI. AI-specific clauses — performance SLAs, bias evaluation obligations, incident reporting, data disclosure, and liability provisions — must be standard in every FMoH AI procurement.

---

*Approved by the AI Review Committee, Federal Ministry of Health, Nigeria.*  
*3 October 2026*

*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*

