# Incident Scenario — MamaAlert Maternal Risk Scoring Tool

**Incident Reference:** FMoH-INC-2026-001  
**System:** FMoH-AI-003 — MamaAlert Maternal Risk Scoring Tool  
**Incident Classification:** Critical — Patient Safety  
**Date Detected:** 4 September 2026  
**Date Reported to AI Review Committee:** 5 September 2026  
**System Status:** Suspended (5 September 2026)  

---

## 1. System Background

The MamaAlert Maternal Risk Scoring Tool has been deployed by the National Primary Health Care Development Agency (NPHCDA) since March 2021 across 12 Nigerian states. The system stratifies maternal mortality risk at antenatal registration, assigning pregnant women a risk category of Low, Medium, or High, and generating a referral recommendation for Community Health Extension Workers (CHEWs).

The system was developed with USAID funding and technical support from DabaDoc. Its training data was drawn primarily from urban primary health care facilities in Lagos, Abuja, and Port Harcourt — the facilities with the most complete digital health records available at the time of development.

At the time of this incident, the system was active in 12 states including Kano, Katsina, Sokoto, and Zamfara — states in Northwest Nigeria with some of Nigeria's highest maternal mortality rates and predominantly rural patient populations.

---

## 2. Detection

### Initial Signal — 28 August 2026

Following the establishment of FMoH's AI governance programme in July 2026, the newly appointed System Owner for FMoH-AI-003 — the Executive Director, NPHCDA — submitted the system's first formal System Performance Report to the AI Governance Lead as required under the new governance framework.

The report included aggregated referral data from the 12 active states. A data analyst reviewing the report noticed an anomaly: the High Risk referral rate in the four Northwest states (Kano, Katsina, Sokoto, Zamfara) was **3.1%** — compared to **11.7%** in the four Southwest states (Lagos, Ogun, Oyo, Osun).

This disparity was significant. Northwest Nigeria has materially higher rates of early marriage, grand multiparity (high number of pregnancies), anaemia, and limited access to emergency obstetric care — all established risk factors for maternal mortality. A lower High Risk classification rate in this region was the opposite of what epidemiological evidence would predict.

### Escalation — 2 September 2026

The AI Governance Lead escalated the anomaly to the Director, eHealth Division, who instructed an immediate clinical review of recent MamaAlert outputs in the Northwest states.

### Confirmed Incident — 4 September 2026

Clinical reviewers at two facilities in Kano State identified two cases in which women who subsequently experienced obstetric emergencies (one severe postpartum haemorrhage, one eclampsia) had been classified as **Low Risk** by MamaAlert at their antenatal registration and were not referred for specialist care. Both women survived but required emergency intervention. Both cases were assessed by the clinical reviewers as cases where a correct High Risk classification would likely have triggered earlier specialist referral.

The AI Governance Lead classified the incident as **Critical — Patient Safety** at 17:30 on 4 September 2026.

---

## 3. Immediate Impact Assessment

### Patient Impact
- **2 confirmed near-miss cases** in Kano State where MamaAlert misclassification contributed to delayed specialist referral
- Clinical review of a random sample of 200 MamaAlert outputs from Northwest states found a **misclassification rate of approximately 23%** for women with established risk factors common in rural Northwest Nigeria (grand multiparity, low haemoglobin, rural LGA location)
- Estimated **active exposure:** approximately 4,200 women currently under antenatal care in the 12 active states who received a MamaAlert risk classification in the preceding 6 months

### System Exposure
- MamaAlert has been active in Northwest states since 2022 — **4 years of potentially biased risk classification**
- Estimated total antenatal registrations processed by MamaAlert in Northwest states: approximately 180,000
- The proportion of these that were incorrectly classified cannot be determined without case-by-case clinical review

### Governance Exposure
- The system operated for 4 years without a formal governance review, performance monitoring, or bias evaluation
- No outcome tracking (actual vs predicted maternal risk) was implemented — meaning the bias was invisible until the new governance framework triggered the first performance review
- No adverse event reporting mechanism existed prior to July 2026 — meaning near-miss cases linked to MamaAlert would not previously have been identified or investigated

---

## 4. Root Cause (Summary)

Full root cause analysis is documented in `root-cause-analysis.md`. In summary:

**Primary cause:** Training data bias. MamaAlert's model was trained on data from urban Southwest Nigerian health facilities. The patient population in rural Northwest Nigeria differs materially in risk factor profile, clinical presentation, and socioeconomic characteristics. The model learned to associate risk with features common in urban Southwest patients and systematically underweighted risk factors more prevalent in Northwest patients.

**Contributing causes:**
- No bias evaluation was conducted before deployment in Northwest states
- No performance monitoring framework was implemented post-deployment
- No outcome tracking linked MamaAlert classifications to actual maternal outcomes
- CHEWs lacked training to identify or report cases where the AI classification appeared inconsistent with their clinical observation
- No vendor obligation existed to monitor or report performance degradation

---

## 5. Stakeholders Affected

| Stakeholder | Impact |
|---|---|
| Pregnant women in Northwest Nigeria | Direct patient safety risk — potentially incorrect risk classification and missed referrals |
| Community Health Extension Workers (CHEWs) | Relied on MamaAlert outputs without adequate training to challenge them |
| NPHCDA | Operational and reputational accountability for system deployment |
| FMoH eHealth Division | Governance accountability; new governance programme's first major test |
| DabaDoc (vendor) | Contractual and reputational exposure |
| USAID (donor funder) | Programme accountability for funded AI system causing harm |
| Nigeria Data Protection Commission | Regulatory interest in data processing practices linked to patient harm |

---

## 6. Decision to Suspend

At 09:00 on 5 September 2026, the Director, eHealth Division, exercising authority under the FMoH Responsible AI Policy, suspended MamaAlert from active use across all 12 states pending the outcome of the incident investigation and root cause analysis.

Suspension notification was sent to:
- All 12 state Primary Health Care Development Agencies
- All facility-level CHEW supervisors in active states
- NPHCDA headquarters
- DabaDoc (vendor)
- USAID Nigeria health programme office

CHEWs were instructed to revert to manual clinical risk assessment protocols pending system restoration or replacement.

---

*Prepared as part of the AI Governance Portfolio — [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)*
