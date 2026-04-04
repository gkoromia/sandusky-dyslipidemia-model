---
layout: default
title: "Clinic Workflow"
parent: Workflows
nav_order: 1
version: "1.0.0"
last_updated: "2026-03-30"
---

# Clinic Workflow — Master Flowchart
{: .no_toc }

This workflow illustrates the end-to-end patient journey through The Sandusky Dyslipidemia Model clinic, from referral receipt to ongoing management. For detailed documentation of each step, see the corresponding clinical documents linked below.

---

## Master Clinic Workflow

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#ffffff
    classDef assess fill:#264653,stroke:#1d3557,color:#ffffff
    classDef caution fill:#e76f51,stroke:#c1440e,color:#ffffff
    classDef urgent fill:#d62828,stroke:#9d0208,color:#ffffff
    classDef admin fill:#6c757d,stroke:#495057,color:#ffffff
    classDef outcome fill:#2196F3,stroke:#1565C0,color:#ffffff

    A[Referral Received]:::entry --> B{Eligibility\nScreen}
    B -->|Meets criteria| C[Schedule New\nPatient Visit]:::admin
    B -->|Does not meet\ncriteria| D[Return to Referring\nProvider with Explanation]:::admin

    C --> E{Priority\nAssessment}
    E -->|Urgent:\nLDL ≥190, post-ACS,\nTG ≥500| F[Schedule within\n2 weeks]:::urgent
    E -->|Standard| G[Schedule within\n4–6 weeks]:::admin

    F --> H[Pre-Visit:\nPatient Instructions]:::admin
    G --> H

    H --> I[Nursing Intake\n10 min]:::admin
    I --> J[Provider Encounter\n25 min]:::assess

    J --> K[History &\nPhysical Exam]:::assess
    K --> L[Review Available\nLabs & Records]:::assess
    L --> M[Document Risk\nFactors & Enhancers]:::assess

    M --> N{PREVENT Risk\nCalculation}:::assess
    N --> O{Risk Category\nAssignment}

    O -->|Low risk\nCAC=0 + ApoB neg| P[Consider\nDe-risking]:::entry
    O -->|Borderline/\nIntermediate| Q[Evaluate Risk\nEnhancers]:::caution
    O -->|High/Very High\nor ASCVD| R[Aggressive\nTreatment]:::urgent

    P --> S[Lifestyle\nCounseling]:::assess
    Q --> T{Advanced Testing\nIndicated?}
    R --> U[Initiate/Optimize\nPharmacotherapy]:::outcome

    T -->|Yes| V[Order Advanced\nTools]:::outcome
    T -->|No| U
    V --> W[ApoB / NMR /\nLp*a* / CAC]:::assess
    W --> X[Reassess Risk\nCategory]:::assess
    X --> U

    U --> Y[Treatment Plan\nDocumented]:::outcome
    S --> Y

    Y --> Z[Order Labs for\nNext Visit]:::admin
    Z --> AA[Schedule\nFollow-Up]:::admin

    AA --> AB{Follow-Up\nType}
    AB -->|New med or\ndose change| AC[4–8 weeks]:::admin
    AB -->|Titrating,\nnot stable| AD[3–6 months]:::admin
    AB -->|At goal,\nstable| AE[Annually]:::admin

    AC --> AF[Follow-Up Visit\n20 min]:::assess
    AD --> AF
    AE --> AF

    AF --> AG{At Treatment\nGoal?}
    AG -->|Yes| AH[Continue Current\nTherapy]:::entry
    AG -->|No| AI[Escalate per\nTreatment Pathway]:::caution

    AH --> AA
    AI --> U
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
