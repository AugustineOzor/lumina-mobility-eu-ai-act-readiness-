# EU AI Act Readiness Assessment

<img width="1600" height="520" alt="lumina-mobility-eu-ai-act-readiness-banner" src="https://github.com/user-attachments/assets/3ca35356-9034-40ae-841c-45b44e6252b9" />

### Lumina Mobility — The first deliverable before committing budget to full Articles 8–15 implementation

![Domain](https://img.shields.io/badge/Domain-AI%20Regulation-468cff) ![Sector](https://img.shields.io/badge/Sector-Mobility%20SaaS-1f2a44) ![EU AI Act](https://img.shields.io/badge/EU%20AI%20Act-Art.%206%2C%209%E2%80%9314%20%7C%20Annex%20III-1f2a44) ![Omnibus](https://img.shields.io/badge/Reg.%20(EU)%202026%2F1744-Omnibus%20reflected-1f2a44) ![Status](https://img.shields.io/badge/Status-Complete-2ea043)

> **Short description:** A readiness assessment for an EU-facing ride-hailing and fleet-routing SaaS company. It determines Lumina's **actor role** for each of 8 AI systems, classifies them against **Article 6 / Annex III**, gap-assesses the two high-risk systems (dispatch optimisation and driver scoring) against **Articles 9, 10, 12, 13 and 14**, and produces a costed, prioritised roadmap — updated for the **Digital Omnibus (Regulation (EU) 2026/1744)**, which moved Annex III obligations to **2 December 2027**.

---

## 1. Organisation Context

| Attribute | Detail |
|---|---|
| Organisation | Lumina Mobility B.V. (fictional), headquartered in Amsterdam |
| Business lines | (1) **Lumina Fleet** — B2B SaaS for dispatch, routing and driver management, licensed to 140 taxi, private-hire and delivery fleet operators in 11 EU member states; (2) **Lumina Ride** — own-brand ride-hailing app in Amsterdam, Lisbon and Warsaw |
| Workers affected | ~38,000 drivers on customers' fleets; ~6,500 drivers on Lumina Ride |
| AI systems | 8 in scope |
| Adjacent regulation | GDPR (incl. Art. 22), Platform Work Directive (EU) 2024/2831 (transposition due 2 Dec 2026), national labour law, DSA (limited) |
| Trigger | Two enterprise customers inserted AI Act warranties into renewal contracts; the board asked "what will this cost, and when?" |

## 2. Objective

Produce a **readiness assessment** — not a compliance programme. The output answers four board questions:

1. **Are we in scope, and in what role?** (provider, deployer, or both — per system)
2. **Which systems are high-risk?** (Article 6 / Annex III)
3. **How far are we from compliance?** (Articles 9–14 gap assessment)
4. **What will it take, in what order, by when?** (prioritised, effort-estimated roadmap)

## 3. Scope

**In scope:** All 8 AI systems in Lumina Fleet and Lumina Ride; applicability and actor role; Article 6 classification; Articles 9, 10, 12, 13, 14 gap assessment for high-risk systems; remediation roadmap; executive summary.

**Noted but not assessed in depth:** Art. 11 technical documentation, Art. 15 accuracy/robustness/cybersecurity, Art. 17 QMS, conformity assessment (Art. 43) — included in roadmap as dependencies.

**Out of scope:** GPAI model obligations (Lumina uses but does not provide GPAI models); legal opinion.

## 4. Approach

```mermaid
flowchart LR
    A[AI system<br/>inventory · 8 systems] --> B[Art. 3 definition<br/>& Art. 2 scope]
    B --> C[Actor role<br/>provider / deployer]
    C --> D[Art. 5 prohibited<br/>practices screen]
    D --> E[Art. 6 / Annex III<br/>classification + 6(3) test]
    E --> F[Art. 9–14 gap<br/>assessment · high-risk only]
    F --> G[Roadmap &<br/>effort estimate]
    G --> H[Executive<br/>summary]
```

Evidence: 16 interviews (product, data science, legal, operations, driver-support), architecture & data-flow review, sample of 3 customer contracts, product documentation, logging configuration, driver-facing communications.

## 5. Deliverables

| # | Deliverable | Answers |
|---|---|---|
| 1 | [Applicability-and-Actor-Role-Assessment.md](Applicability-and-Actor-Role-Assessment.md) | Q1 — scope & role per system |
| 2 | [Article-6-Classification.md](Article-6-Classification.md) | Q2 — risk classification |
| 3 | [Gap-Assessment-Articles-9-14.md](Gap-Assessment-Articles-9-14.md) | Q3 — 30 requirement-level gaps scored |
| 4 | [Remediation-Roadmap.md](Remediation-Roadmap.md) | Q4 — sequenced workstreams with effort |
| 5 | [Executive-Readiness-Summary.md](Executive-Readiness-Summary.md) | Board-level synthesis |

## 6. Headline Findings

| Finding | Result |
|---|---|
| Systems in scope | 8 |
| **High-risk (Annex III point 4 — employment / worker management)** | **2** — Dispatch Optimisation Engine, Driver Performance Score |
| Lumina's role for high-risk systems | **Provider** (Lumina Fleet) **and** provider-deployer (Lumina Ride) |
| Prohibited-practice finding | 1 planned feature ("driver mood detection") halted under Art. 5(1)(f) |
| Transparency (Art. 50) obligations | 2 systems — chatbot, AI-generated driver messages |
| Overall readiness (high-risk systems) | **1.4 / 4** — "Initial" |
| Estimated remediation effort | **~2,950 person-days** over 14 months; est. €2.1–2.6m incl. tooling and external support |
| Planning deadline | **2 Dec 2027** (Annex III, per Reg. (EU) 2026/1744); target readiness **Q3 2027** to allow conformity assessment and customer onboarding |

## 7. Framework Alignment

| Source | Use |
|---|---|
| EU AI Act (Reg. (EU) 2024/1689) as amended by Reg. (EU) 2026/1744 | Primary legal reference — Arts. 2, 3, 5, 6, 8–15, 16, 25, 26, 50, Annex III |
| Commission Guidelines on AI system definition & prohibited practices (2025) | Definition and Art. 5 interpretation |
| NIST AI RMF 1.0 | Underlying control detail for each gap (MAP/MEASURE/MANAGE references in gap file) |
| ISO/IEC 42001 | Management-system scaffolding for Art. 17 QMS (roadmap) |
| Platform Work Directive (EU) 2024/2831 | Overlapping algorithmic-management obligations for drivers |

## 8. Repository Structure

```
lumina-mobility-eu-ai-act-readiness/
├── README.md
├── assets/banner.jpg
├── Applicability-and-Actor-Role-Assessment.md
├── Article-6-Classification.md
├── Gap-Assessment-Articles-9-14.md
├── Remediation-Roadmap.md
└── Executive-Readiness-Summary.md
```

## 9. Skills Demonstrated

EU AI Act interpretation · Actor-role analysis (provider/deployer/Art. 25) · Annex III & Art. 6(3) classification · Requirement-level gap assessment · Maturity scoring · Programme planning & effort estimation · Board communication · Regulatory change tracking (Digital Omnibus)

## 10. Disclaimer

Lumina Mobility is fictional. This is a governance portfolio exercise, not legal advice. Regulatory dates reflect Regulation (EU) 2026/1744 as published in July 2026; verify against the Official Journal before relying on them.

---

