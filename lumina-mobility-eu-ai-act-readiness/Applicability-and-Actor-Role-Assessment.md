# Applicability and Actor Role Assessment
**Lumina Mobility B.V.** · Document ID: LM-AIA-001 · Version 1.0 · Date: 2026-09-10 · Classification: Confidential — Legally privileged draft for counsel review

---

## 1. Purpose
Determine (a) whether each Lumina system is an **AI system** under Art. 3(1); (b) whether it falls within the **territorial and material scope** of the Act (Art. 2); and (c) Lumina's **actor role** — because obligations differ fundamentally between providers (Art. 16) and deployers (Art. 26).

## 2. Territorial Scope (Art. 2(1))
Lumina is established in the Netherlands and places Lumina Fleet on the EU market and puts Lumina Ride into service in the EU. **The Act applies.** No Art. 2 exclusions (military, research-only, personal non-professional use) are relevant.

## 3. AI System Definition Test (Art. 3(1))
Key elements: machine-based · varying levels of autonomy · may exhibit adaptiveness · **infers from input how to generate outputs** (predictions, content, recommendations, decisions) · that can influence physical or virtual environments.

| ID | System | Technique | Infers outputs? | AI system? | Rationale |
|---|---|---|---|---|---|
| S1 | Dispatch Optimisation Engine | Gradient-boosted acceptance-probability model + combinatorial optimiser | Yes — predicts acceptance & ETA, recommends assignment | **Yes** | ML inference drives assignment |
| S2 | Driver Performance Score | Ensemble model on acceptance rate, cancellations, ratings, complaints, telematics | Yes — score & tier | **Yes** | Learned weighting |
| S3 | Dynamic Pricing (surge) | Demand forecasting + pricing rules | Yes — demand forecast | **Yes** | ML forecast drives price multiplier |
| S4 | Fraud & Account-Integrity Detection | Anomaly detection + classifier | Yes — fraud likelihood | **Yes** | |
| S5 | Driver Identity Verification | 1:1 face verification (third-party SDK) | Yes — match decision | **Yes** | |
| S6 | Rider & Driver Support Chatbot | LLM (third-party GPAI via API) with RAG | Yes — content | **Yes** | |
| S7 | ETA & Route Prediction | Graph ML on traffic data | Yes — ETA | **Yes** | |
| S8 | Shift-Demand Heatmap (driver app) | Time-series forecast | Yes — forecast | **Yes** | |
| — | Fare calculator (distance × rate tables) | Deterministic rules | No | Excluded | No inference |

## 4. Actor Role Determination

| Role | Test |
|---|---|
| **Provider** (Art. 3(3)) | Develops an AI system (or has it developed) and places it on the market / puts it into service under its own name or trademark |
| **Deployer** (Art. 3(4)) | Uses an AI system under its authority in a professional context |
| **Art. 25 re-designation** | A deployer/distributor becomes provider if it puts its name on a high-risk system, makes a substantial modification, or changes intended purpose so it becomes high-risk |

### 4.1 Role matrix

| ID | System | Lumina Fleet (B2B SaaS) | Lumina Ride (own app) | Fleet customers | Third-party supplier |
|---|---|---|---|---|---|
| S1 | Dispatch Optimisation | **Provider** | **Provider + Deployer** | Deployers | — |
| S2 | Driver Performance Score | **Provider** | **Provider + Deployer** | Deployers | — |
| S3 | Dynamic Pricing | Provider | Provider + Deployer | Deployers | — |
| S4 | Fraud Detection | Provider | Provider + Deployer | Deployers | — |
| S5 | Identity Verification | Distributor/integrator — see note | Deployer | Deployers | **VeriFace Ltd = Provider** |
| S6 | Support Chatbot | Provider (of the AI system) | Provider + Deployer | Deployers | GPAI model provider (model obligations, Arts. 53–55) |
| S7 | ETA & Route | Provider | Provider + Deployer | Deployers | — |
| S8 | Demand Heatmap | Provider | Provider + Deployer | Deployers | — |

**Note on S5:** Lumina integrates VeriFace's SDK without modifying the model and markets it as "VeriFace-powered". Lumina is not the provider of S5 unless it rebrands it under its own name or substantially modifies it (Art. 25(1)). **Action:** maintain current branding; record this determination.

**Note on S6:** Building an application on a third-party GPAI model makes Lumina the **provider of the AI system** (the chatbot), while the model provider retains GPAI model obligations. Lumina should obtain the downstream-provider information required under Art. 53(1)(b).

### 4.2 Fleet-customer configuration risk (Art. 25)
Fleet customers can configure S2 thresholds and **use S2 scores to deactivate drivers**. If Lumina's documented intended purpose is narrower (e.g., "coaching only") and a customer uses it for deactivation, that customer could become a provider under Art. 25(1)(c). **Recommendation:** define S2's intended purpose to include the uses Lumina actually enables, and assume provider obligations — commercially, customers will expect Lumina to carry them.

## 5. Obligation Profile Resulting

| Lumina role | Key obligations (high-risk systems) |
|---|---|
| **Provider** (S1, S2) | Arts. 8–15 requirements; Art. 16 provider obligations; Art. 17 QMS; Art. 18 documentation retention; Art. 19 logs; Art. 20 corrective actions; Art. 43 conformity assessment (internal control, Annex VI); Art. 47 EU declaration of conformity; Art. 48 CE marking; Art. 49 registration in EU database; Art. 72 post-market monitoring; Art. 73 serious-incident reporting |
| **Deployer** (S1, S2 within Lumina Ride) | Art. 26 — use per instructions, human oversight by competent persons, input-data relevance, monitoring, log retention ≥ 6 months, **inform workers' representatives and affected workers before use (Art. 26(7))**; Art. 86 right to explanation |
| **All roles** | Art. 4 AI literacy (in force since 2 Feb 2025); Art. 5 prohibitions (since 2 Feb 2025); Art. 50 transparency (S6 and AI-generated messages) |

## 6. Applicable Dates (as amended by Reg. (EU) 2026/1744)

| Obligation | Applies from | Lumina status |
|---|---|---|
| Art. 5 prohibitions; Art. 4 AI literacy | 2 Feb 2025 | **Already applicable** — see findings |
| GPAI model obligations | 2 Aug 2025 | Not a GPAI provider |
| Art. 50 transparency | Aug 2026 | **Already applicable** — S6 disclosure partially in place |
| **Annex III high-risk obligations (S1, S2)** | **2 Dec 2027** | Planning deadline for this assessment |

## 7. Findings Requiring Immediate Attention (already-applicable obligations)

| # | Finding | Article | Action |
|---|---|---|---|
| AF-1 | No AI literacy programme for staff operating or overseeing AI | Art. 4 | Launch role-based literacy programme (roadmap WS-0) |
| AF-2 | Planned "driver mood detection" feature using in-cab camera to infer frustration/stress | Art. 5(1)(f) — emotion recognition in the workplace | **Halted.** Note: fatigue/drowsiness detection (physical state) is treated differently under the Commission's prohibited-practices guidelines and may proceed subject to separate assessment |
| AF-3 | Chatbot discloses AI use in rider app but not in driver app | Art. 50(1) | Add disclosure to driver channel |
| AF-4 | AI-drafted driver performance messages sent without indication | Art. 50 (assess) / PWD transparency | Add disclosure and human-review step |
