# Article 6 Classification
**Lumina Mobility B.V.** · Document ID: LM-AIA-002 · Version 1.0 · Date: 2026-09-17 · Classification: Confidential

---

## 1. Method

```mermaid
flowchart TD
    A[AI system] --> B{Art. 5 prohibited practice?}
    B -- Yes --> P[Prohibited — cease]
    B -- No --> C{Safety component of / product under<br/>Annex I harmonisation law? Art. 6(1)}
    C -- Yes --> H1[High-risk — Annex I route]
    C -- No --> D{Listed in Annex III? Art. 6(2)}
    D -- No --> E{Art. 50 transparency trigger?}
    D -- Yes --> F{Art. 6(3) derogation applies?<br/>and NO profiling of natural persons}
    F -- Yes, documented --> G[Not high-risk<br/>document & register per Art. 6(4), 49(2)]
    F -- No --> H2[HIGH-RISK — Annex III]
    E -- Yes --> L[Limited risk — transparency]
    E -- No --> M[Minimal risk — voluntary codes]
```

**Art. 6(3) derogation:** an Annex III system is not high-risk if it does not pose a significant risk of harm, because it only (a) performs a narrow procedural task, (b) improves the result of a completed human activity, (c) detects decision-making patterns without replacing/influencing a prior human assessment, or (d) performs a preparatory task. **The derogation never applies where the system performs profiling of natural persons** (Art. 6(3), final subparagraph, referencing GDPR Art. 4(4)).

## 2. Relevant Annex III Points Considered

| Annex III point | Text (paraphrased) | Relevance |
|---|---|---|
| **4(b)** Employment, workers management | AI intended to make decisions affecting terms of work-related relationships, promotion or termination; **to allocate tasks based on individual behaviour or personal traits or characteristics**; or to monitor and evaluate performance and behaviour of persons in such relationships | **Core test for S1, S2, S4** — platform drivers are in "work-related relationships" regardless of employment status |
| 1(a) Remote biometric identification | Excludes biometric **verification** whose sole purpose is confirming a person is who they claim to be | S5 |
| 2 Critical infrastructure | Safety components in management/operation of road traffic | S7 considered |
| 5(b) Creditworthiness | Credit scoring (excludes fraud detection) | S4 considered — not applicable (not credit) |

## 3. Classification Results

| ID | System | Art. 5 | Annex I | Annex III point | Art. 6(3) derogation? | Profiling? | **Classification** |
|---|---|---|---|---|---|---|---|
| S1 | Dispatch Optimisation Engine | No | No | **4(b)** — allocates rides using driver-specific acceptance probability, historic behaviour and S2 tier | No — determines task allocation | **Yes** | **HIGH-RISK** |
| S2 | Driver Performance Score | No | No | **4(b)** — monitors & evaluates performance; used in incentive eligibility and deactivation | No | **Yes** | **HIGH-RISK** |
| S3 | Dynamic Pricing | No | No | None (pricing to riders not listed; affects drivers' earnings indirectly, not individually) | n/a | Aggregate only | **Minimal risk** |
| S4 | Fraud & Account-Integrity | No | No | **4(b) assessed** — rider-side: not listed. Driver-side: flags lead to temporary suspension pending human review | **Yes — 6(3)(d) preparatory** *only if* suspension is not automatic | **Yes** (driver behaviour) | **HIGH-RISK (driver-side)** — profiling bars derogation; *see sensitivity note* |
| S5 | Identity Verification | No | No | 1(a) excluded — 1:1 verification | n/a | No | **Not high-risk** (GDPR Art. 9 still applies) |
| S6 | Support Chatbot | No | No | None | n/a | No | **Limited risk — Art. 50(1)** |
| S7 | ETA & Route | No | No | 2 considered — not a safety component of road-traffic management | n/a | No | **Minimal risk** |
| S8 | Demand Heatmap | No | No | None — same forecast to all drivers in an area | n/a | No | **Minimal risk** |

### 3.1 Sensitivity note on S4
Driver-side fraud scoring evaluates individual behaviour and triggers suspension (a decision affecting the work relationship) — this falls under 4(b), and because it profiles drivers, Art. 6(3) cannot apply. However, the gap assessment scope was set by the brief to the **two primary systems (S1, S2)**. **Recommendation:** treat S4 driver-side as high-risk and fold it into the S2 workstream (shared data, shared oversight design) — reflected in the roadmap as WS-7. Rider-side fraud detection remains minimal risk.

### 3.2 Why S1 is high-risk even though it "just routes rides"
A dispatch engine that used only distance and availability might be argued not to allocate "based on individual behaviour or personal traits". Lumina's engine includes **driver-specific acceptance probability, cancellation history and S2 tier as features**, and drivers in lower tiers receive measurably fewer high-value trips (internal analysis: −18% average fare value for Tier C). This is task allocation based on individual behaviour — squarely 4(b).

**Design alternative evaluated:** removing behavioural features would likely take S1 out of Annex III but reduce matching efficiency by an estimated 4–6%. Presented to the board as an option; not recommended as a compliance strategy because S2 would remain high-risk and the governance investment is largely shared.

## 4. Classification Summary

| Classification | Systems |
|---|---|
| Prohibited | 0 in operation (1 planned feature halted — see LM-AIA-001 AF-2) |
| **High-risk (Annex III)** | **S1, S2** (+ S4 driver-side, recommended) |
| Limited risk (Art. 50) | S6 |
| Minimal risk | S3, S7, S8 |
| Not high-risk, other law applies | S5 |

## 5. Documentation & Review
- This classification is the documented assessment for Art. 6(4) purposes (no system relies on the derogation, so Art. 49(2) registration of non-high-risk Annex III systems is not triggered).
- Re-classify on: new features using driver-level data, new use of outputs by customers, Commission delegated acts amending Annex III or Art. 6(3) conditions, or new Commission guidelines on high-risk classification.
