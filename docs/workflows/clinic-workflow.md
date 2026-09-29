---
layout: default
title: "Clinic Workflow"
parent: Workflows
nav_order: 1
version: "1.1.0"
last_updated: "2026-09-29"
---

# Clinic Workflow — Master Flowchart
{: .no_toc }

This workflow illustrates the end-to-end patient journey through The Sandusky Dyslipidemia Model clinic, from referral receipt to ongoing management. For detailed documentation of each step, see the corresponding clinical documents linked below.

---

## How to Read These Charts

The workflow is split into three charts that follow the patient in order. A dashed box at the end of a chart names the chart that picks up from there.

{% include workflow_legend.html %}

## Part 1 — Referral and Scheduling

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    A[Referral Received]:::entry --> B{Eligibility<br>Screen}
    B -->|Meets criteria| C[Schedule New<br>Patient Visit]:::admin
    B -->|Does not meet<br>criteria| D[Return to Referring<br>Provider with Explanation]:::admin

    C --> E{Priority<br>Assessment}
    E -->|Urgent: LDL ≥190,<br>post-ACS, TG ≥500| F[Schedule within<br>2 weeks]:::urgent
    E -->|Standard| G[Schedule within<br>4–6 weeks]:::admin

    F --> H[Pre-Visit:<br>Patient Instructions]:::admin
    G --> H

    H --> I[Nursing Intake<br>10 min]:::admin
    I --> J[Provider Encounter<br>25 min]:::assess
    J --> NEXT[Continue to Part 2:<br>Initial Visit]:::link
```

## Part 2 — Initial Visit and Treatment Plan

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    J[Provider Encounter<br>25 min]:::assess --> K[History &<br>Physical Exam]:::assess
    K --> L[Review Available<br>Labs & Records]:::assess
    L --> M[Document Risk<br>Factors & Enhancers]:::assess

    M --> N[PREVENT Risk<br>Calculation]:::assess
    N --> O{Risk Category<br>Assignment}

    O -->|Low risk<br>CAC=0 + ApoB neg| P[Consider<br>De-risking]:::entry
    O -->|Borderline/<br>Intermediate| Q[Evaluate Risk<br>Enhancers]:::caution
    O -->|High/Very High<br>or ASCVD| R[Aggressive<br>Treatment]:::urgent

    P --> S[Lifestyle<br>Counseling]:::assess
    Q --> T{Advanced Testing<br>Indicated?}
    R --> U[Initiate/Optimize<br>Pharmacotherapy]:::treat

    T -->|Yes| V[Order Advanced<br>Tools]:::treat
    T -->|No| U
    V --> W["ApoB / NMR /<br>Lp(a) / CAC"]:::assess
    W --> X[Reassess Risk<br>Category]:::assess
    X --> U

    U --> Y[Treatment Plan<br>Documented]:::treat
    S --> Y

    Y --> Z[Order Labs for<br>Next Visit]:::admin
    Z --> AA[Schedule<br>Follow-Up]:::admin
    AA --> NEXT[Continue to Part 3:<br>Follow-Up Cycle]:::link
```

## Part 3 — Follow-Up Cycle

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    AA[Schedule<br>Follow-Up]:::admin --> AB{Follow-Up<br>Type}
    AB -->|New med or<br>dose change| AC[4–8 weeks]:::admin
    AB -->|Titrating,<br>not stable| AD[3–6 months]:::admin
    AB -->|At goal,<br>stable| AE[Annually]:::admin

    AC --> AF[Follow-Up Visit<br>20 min]:::assess
    AD --> AF
    AE --> AF

    AF --> AG{At Treatment<br>Goal?}
    AG -->|Yes| AH[Continue Current<br>Therapy]:::entry
    AG -->|No| AI[Escalate per<br>Treatment Pathway]:::caution

    AH --> AA
    AI --> U[Back to Part 2:<br>Initiate/Optimize<br>Pharmacotherapy]:::link
```

## Workflow Cross-References

| Workflow Step | Detailed Documentation |
|:--------------|:----------------------|
| Eligibility Screen | [02 — Patient Eligibility]({% link clinical/02-patient-eligibility.md %}) |
| History & Physical Exam | [03 — Initial Assessment, Sections 2.0–4.0]({% link clinical/03-initial-assessment.md %}) |
| PREVENT Risk Calculation | [04 — Risk Stratification]({% link clinical/04-risk-stratification.md %}) |
| Risk Category Assignment | [04 — Risk Stratification]({% link clinical/04-risk-stratification.md %}) |
| Advanced Tools | [06 — Advanced Tools]({% link clinical/06-advanced-tools.md %}) |
| Treatment Plan | [05 — Treatment Pathways]({% link clinical/05-treatment-pathways.md %}) |
| Follow-Up Protocol | [12 — Follow-Up Protocol]({% link clinical/12-follow-up-protocol.md %}) |

## Special Pathways

The following specialty pathways branch from the master workflow at specific decision points:

| Pathway | Entry Point | Flowchart |
|:--------|:------------|:----------|
| Familial Hypercholesterolemia | LDL-C ≥ 190, tendon xanthomas, or family history of FH | [FH Pathway Flow]({% link workflows/fh-pathway-flow.md %}) |
| Statin Intolerance | Reported statin intolerance during history or treatment | [Statin Intolerance Flow]({% link workflows/statin-intolerance-flow.md %}) |
| Treatment Escalation | Not at goal after initial or adjusted therapy | [Treatment Escalation Flow]({% link workflows/treatment-escalation-flow.md %}) |
| Risk Stratification Detail | PREVENT calculation and advanced testing decisions | [Risk Stratification Flow]({% link workflows/risk-stratification-flow.md %}) |
| Advanced Tools Decision | Which advanced test to order and when | [Advanced Tools Decision Flow]({% link workflows/advanced-tools-decision-flow.md %}) |

---

## Version History

| Version | Date | Description |
|:--------|:-----|:------------|
| 1.0.0 | 2026-03-30 | Initial release |
| 1.1.0 | 2026-09-29 | Split into smaller charts so text renders at full size; fixed line breaks that printed as literal escape codes; accessible color palette and shared legend |
