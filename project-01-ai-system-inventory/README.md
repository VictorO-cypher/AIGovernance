# Project 01 — AI System Inventory & Classification
## Federal Ministry of Health, Nigeria

**Framework:** NIST AI Risk Management Framework (AI RMF) | EU AI Act  
**Author:** Victor Eze Odoh  
**Context:** Nigerian Public Sector — Federal Ministry of Health (FMoH)  
**Status:** Governance Portfolio Project

---

## 1. Overview

This project documents a structured AI system inventory and risk classification exercise for the Federal Ministry of Health (FMoH) of Nigeria. As Nigerian health institutions increasingly procure and deploy AI-powered tools — from diagnostic imaging software to disease surveillance platforms — there is an urgent need for a centralised register that tracks what AI systems are in use, who is accountable for them, and what risks they carry.

This inventory applies the **NIST AI RMF GOVERN and MAP functions** alongside the **EU AI Act's risk classification tiers** to create a practical, replicable template for African public health institutions.

---

## 2. Problem Statement

Nigeria's Federal Ministry of Health is actively deploying and procuring AI systems across multiple verticals — maternal health diagnostics, disease outbreak prediction, patient triage, and health data management. However:

- There is **no centralised register** of AI systems in use across FMoH departments and affiliated hospitals
- **Accountability is fragmented** — vendors, departments, and external donors each manage systems independently
- **Risk classification is absent** — no formal process exists to distinguish low-risk administrative AI tools from high-risk clinical decision-support systems
- **EU AI Act and global standards** are increasingly referenced in donor and procurement conditions, but FMoH has no internal compliance framework to respond

This inventory addresses the first and most foundational step: **knowing what AI systems exist and what risks they carry.**

---

## 3. Scope

This inventory covers AI systems deployed or procured by:

- FMoH headquarters (Abuja)
- National Health Management Information System (NHMIS)
- Nigeria Centre for Disease Control (NCDC)
- Selected tertiary hospitals: Lagos University Teaching Hospital (LUTH), University of Nigeria Teaching Hospital (UNTH)

---

## 4. AI System Inventory Register

The following register documents active and pending AI system deployments within scope.

---

### System 01 — NCDC Disease Surveillance & Outbreak Prediction Platform

| Field | Details |
|---|---|
| **System Name** | NCDC Integrated Disease Surveillance Platform (IDSR-AI Module) |
| **Department** | Nigeria Centre for Disease Control (NCDC) |
| **Vendor / Developer** | Africa CDC / WHO AFRO (external technical support) |
| **Primary Function** | Predict disease outbreak probability by region using historical case data and environmental variables |
| **Data Inputs** | Patient case reports, hospital admission data, climate data, population density data |
| **Output Type** | Risk probability score (Low / Medium / High / Critical) per LGA |
| **Human Oversight** | NCDC Epidemiologists review outputs before alerts are issued |
| **Deployment Date** | 2022 (ongoing) |
| **EU AI Act Risk Tier** | **HIGH RISK** — AI system used in critical infrastructure (public health emergency response) |
| **NIST AI RMF Category** | GOVERN 1.1, MAP 1.5 — System with significant potential societal impact |
| **Identified Risks** | Data quality gaps in rural LGA reporting; potential for false alerts triggering resource misallocation; limited model explainability for epidemiologists |
| **Accountability Owner** | Director General, NCDC |
| **Review Frequency** | Quarterly |

---

### System 02 — AI-Assisted Diagnostic Imaging (LUTH Radiology)

| Field | Details |
|---|---|
| **System Name** | AI Radiology Assistant (Vendor: Inference Analytics Ltd) |
| **Department** | Radiology Department, Lagos University Teaching Hospital (LUTH) |
| **Vendor / Developer** | Inference Analytics Ltd (Lagos-based health-tech startup) |
| **Primary Function** | Detect anomalies in chest X-rays and CT scans; flag suspected TB, pneumonia, and cancer cases |
| **Data Inputs** | Anonymised patient imaging data (X-rays, CT scans) |
| **Output Type** | Anomaly probability score + recommended review flag |
| **Human Oversight** | Consultant radiologist mandatory review before diagnosis is confirmed |
| **Deployment Date** | 2023 (pilot phase) |
| **EU AI Act Risk Tier** | **HIGH RISK** — AI system used in medical device/diagnostic context (Annex III) |
| **NIST AI RMF Category** | MAP 3.5 — AI system with direct patient safety implications |
| **Identified Risks** | Training data sourced primarily from non-Nigerian patient cohorts (potential bias); limited audit trail for AI recommendations; no formal incident reporting mechanism |
| **Accountability Owner** | Chief Medical Director, LUTH |
| **Review Frequency** | Monthly during pilot; quarterly post-deployment |

---

### System 03 — Maternal Health Risk Scoring Tool (National Primary Healthcare)

| Field | Details |
|---|---|
| **System Name** | MamaAlert Risk Stratification Tool |
| **Department** | National Primary Health Care Development Agency (NPHCDA) |
| **Vendor / Developer** | DabaDoc / USAID-funded development |
| **Primary Function** | Predict maternal mortality risk at antenatal registration; flag high-risk pregnancies for specialist referral |
| **Data Inputs** | Age, parity, blood pressure, haemoglobin levels, gestation week, LGA location |
| **Output Type** | Risk category (Low / Medium / High) with referral recommendation |
| **Human Oversight** | Community health extension workers (CHEWs) receive output; midwife or doctor must confirm referral decisions |
| **Deployment Date** | 2021 (12 states active) |
| **EU AI Act Risk Tier** | **HIGH RISK** — AI system in healthcare affecting vulnerable populations |
| **NIST AI RMF Category** | GOVERN 6.1 — System affecting underserved/vulnerable communities |
| **Identified Risks** | Geographic bias (model trained on urban facility data; performance degrades in rural settings); CHEWs lack training to interpret or challenge AI outputs; no formal feedback loop to retrain model on Nigerian-specific data |
| **Accountability Owner** | Executive Director, NPHCDA |
| **Review Frequency** | Bi-annual |

---

### System 04 — NHMIS Health Data Analytics Dashboard

| Field | Details |
|---|---|
| **System Name** | DHIS2 Analytics Module with ML Forecasting |
| **Department** | National Health Management Information System (NHMIS) |
| **Vendor / Developer** | DHIS2 (University of Oslo) / FMoH customisation |
| **Primary Function** | Aggregate national health data; generate trend forecasts for resource planning (drug supply, staffing) |
| **Data Inputs** | Facility-level health service data, supply chain records, staffing data |
| **Output Type** | Trend reports, forecasts, and resource allocation recommendations |
| **Human Oversight** | Health planners and M&E officers interpret dashboard outputs; no automated decision-making |
| **Deployment Date** | 2019 (ongoing; ML module added 2023) |
| **EU AI Act Risk Tier** | **LIMITED RISK** — AI used for planning support; human decision-maker retains full control |
| **NIST AI RMF Category** | MAP 2.2 — AI system used for operational planning with indirect impact |
| **Identified Risks** | Data completeness gaps from low-reporting facilities; potential for planning decisions to be made on incomplete AI-generated forecasts without flagging data quality issues |
| **Accountability Owner** | Director, NHMIS Division, FMoH |
| **Review Frequency** | Annual |

---

### System 05 — AI-Powered Patient Triage Chatbot (Pilot)

| Field | Details |
|---|---|
| **System Name** | HealthLine Nigeria AI Triage Bot |
| **Department** | FMoH eHealth Division |
| **Vendor / Developer** | Helium Health (Lagos) |
| **Primary Function** | Provide symptom assessment and triage guidance to patients via SMS/WhatsApp; direct to appropriate facility level |
| **Data Inputs** | Patient-reported symptoms (text), age, location |
| **Output Type** | Triage recommendation (self-care / primary care / emergency) |
| **Human Oversight** | No mandatory human review of individual outputs; system operates autonomously at scale |
| **Deployment Date** | 2024 (FCT pilot) |
| **EU AI Act Risk Tier** | **HIGH RISK** — Autonomous AI system making healthcare triage recommendations to general public |
| **NIST AI RMF Category** | GOVERN 4.2 — Autonomous system with direct patient-facing output and no human-in-the-loop |
| **Identified Risks** | **Highest risk system in this inventory.** No mandatory human review; potential for incorrect triage leading to delayed emergency care; limited accessibility for non-English/non-Pidgin speakers; no formal adverse event reporting; vendor accountability unclear if harm occurs |
| **Accountability Owner** | Director, eHealth Division, FMoH (**Currently unassigned — governance gap identified**) |
| **Review Frequency** | Monthly minimum recommended; **currently unscheduled** |

---

## 5. Risk Classification Summary

| System | EU AI Act Tier | NIST AI RMF Priority | Human Oversight | Governance Gap |
|---|---|---|---|---|
| NCDC Disease Surveillance | HIGH RISK | High | Partial | Data quality; explainability |
| AI Diagnostic Imaging (LUTH) | HIGH RISK | High | Strong | Training data bias; audit trail |
| MamaAlert Maternal Risk | HIGH RISK | High | Partial | Rural performance; CHEW capacity |
| NHMIS Analytics Dashboard | LIMITED RISK | Medium | Strong | Data completeness |
| HealthLine Triage Chatbot | HIGH RISK | **Critical** | **None** | **Accountability gap; no oversight** |

---

## 6. Key Findings

**Finding 1 — High-risk systems dominate without proportionate governance**  
Four of five inventoried systems are classified as HIGH RISK under the EU AI Act. None have formal conformity assessments, incident reporting mechanisms, or documented accountability chains that would meet international standards.

**Finding 2 — The HealthLine Triage Chatbot presents the highest immediate risk**  
This is the only system operating with no mandatory human oversight at the point of decision. It is deployed to the general public at scale. An incorrect triage recommendation could directly delay emergency care. Immediate governance action is recommended.

**Finding 3 — Training data bias is a systemic issue**  
Two systems (AI Diagnostic Imaging, MamaAlert) were developed primarily on non-Nigerian or urban-only datasets. Performance degradation in rural and Northern Nigerian contexts is a documented but unaddressed risk.

**Finding 4 — Vendor accountability is poorly defined**  
Across all five systems, contractual provisions for AI-specific accountability — model performance monitoring, incident reporting, retraining obligations — are either absent or not publicly documented.

---

## 7. Recommendations

1. **Establish a FMoH AI Systems Register** — mandate all departments and affiliated institutions to register AI systems annually using this inventory template
2. **Immediate governance review of HealthLine Triage Chatbot** — suspend autonomous operation pending appointment of an accountable owner and introduction of human oversight protocols
3. **Require bias audits for high-risk systems** — all HIGH RISK systems should undergo independent performance evaluation on Nigerian-specific patient cohorts within 12 months
4. **Adopt the NIST AI RMF as FMoH's internal governance standard** — adapt the GOVERN, MAP, MEASURE, and MANAGE functions to Nigerian institutional context
5. **Develop AI-specific procurement clauses** — future vendor contracts should include mandatory provisions for model documentation, incident reporting, and periodic performance review

---

## 8. Framework References

- NIST AI Risk Management Framework (AI RMF 1.0), National Institute of Standards and Technology, 2023
- EU Artificial Intelligence Act, European Parliament, 2024
- WHO Guidance on Ethics and Governance of Artificial Intelligence for Health, 2021
- Africa CDC Digital Health Strategy 2021–2025
- Nigeria National Digital Economy Policy and Strategy (NDESP) 2020–2030
- Nigeria eHealth Strategy, Federal Ministry of Health, 2016 (under revision)

---

## 9. About This Project

This project is part of a broader AI governance portfolio applying international frameworks to African public sector contexts. It is authored by **Victor Eze Odoh**, an independent AI governance researcher based in Nigeria, with a background in Political Science and Data Analytics.

The goal is to demonstrate that AI governance is not only a Western policy concern — it is an urgent operational need for African institutions deploying AI systems that directly affect millions of people.

**Portfolio Repository:** [github.com/VictorO-cypher/AIGovernance](https://github.com/VictorO-cypher/AIGovernance)

---

*Last updated: June 2026*
