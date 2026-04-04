---
layout: default
title: "Treatment Escalation Flow"
parent: Workflows
nav_order: 3
version: "1.0.0"
last_updated: "2026-03-30"
---

# Treatment Escalation Flowchart

Visual representation of the stepwise treatment escalation algorithm described in [05 — Treatment Pathways, Section 11.0]({% link clinical/05-treatment-pathways.md %}#110-treatment-escalation-algorithm).

---

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#ffffff
    classDef assess fill:#264653,stroke:#1d3557,color:#ffffff
    classDef caution fill:#e76f51,stroke:#c1440e,color:#ffffff
    classDef urgent fill:#d62828,stroke:#9d0208,color:#ffffff
    classDef admin fill:#6c757d,stroke:#495057,color:#ffffff
    classDef outcome fill:#2196F3,stroke:#1565C0,color:#ffffff
    classDef success fill:#52b788,stroke:#2d6a4f,color:#ffffff

    START[Treatment Plan\nInitiated]:::entry --> STEP1

    subgraph STEP1 [Step 1: Maximize Statin]
        S1A[Initiate or uptitrate\nhighest tolerated\nintensity statin]:::assess
    end

    STEP1 --> LABS1[Recheck lipids + ApoB\n4–8 weeks]:::admin
    LABS1 --> GOAL1{LDL-C AND ApoB\nat target?}

    GOAL1 -->|Yes| MAINTAIN1[Continue Current\nTherapy]:::success
    GOAL1 -->|No| INTOL1{Statin\nIntolerant?}

    INTOL1 -->|Yes| SINPATH[See Statin\nIntolerance Pathway]:::caution
    INTOL1 -->|No| STEP2

    subgraph STEP2 [Step 2: Add Ezetimibe]
        S2A[Add ezetimibe\n10 mg daily]:::assess
    end

    STEP2 --> LABS2[Recheck lipids + ApoB\n4–8 weeks]:::admin
    LABS2 --> GOAL2{LDL-C AND ApoB\nat target?}

    GOAL2 -->|Yes| MAINTAIN2[Continue Statin +\nEzetimibe]:::success
    GOAL2 -->|No| STEP3

    subgraph STEP3 [Step 3: Add Advanced Agent]
        S3DEC{Select Agent\nBased on Clinical\nScenario}:::assess
        S3DEC -->|Max LDL-C reduction\nneeded| PCSK9[PCSK9 Inhibitor\nEvolocumab or\nAlirocumab]:::outcome
        S3DEC -->|Adherence concern\nor prefers in-office| INCL[Inclisiran\nDay 0, Day 90,\nthen q6 months]:::outcome
        S3DEC -->|Prefers oral\nor statin-intolerant| BEMP[Bempedoic Acid\n± Ezetimibe combo]:::outcome
    end

    PCSK9 --> PA1[Prior Authorization\nRequired]:::admin
    INCL --> PA2[Prior Authorization\nRequired]:::admin
    BEMP --> LABS3

    PA1 --> LABS3[Recheck lipids + ApoB\n4–8 weeks]:::admin
    PA2 --> LABS3

    LABS3 --> GOAL3{LDL-C AND ApoB\nat target?}

    GOAL3 -->|Yes| MAINTAIN3[Continue Current\nRegimen]:::success
    GOAL3 -->|No| STEP4

    subgraph STEP4 [Step 4: Combination Advanced Therapy]
        S4A[Add second advanced\nagent to regimen]:::urgent
        S4B[Reassess:\n• Adherence\n• Secondary causes\n• FH evaluation]:::assess
        S4A --> S4B
    end

    STEP4 --> LABS4[Recheck lipids + ApoB\n4–8 weeks]:::admin
    LABS4 --> GOAL4{LDL-C AND ApoB\nat target?}

    GOAL4 -->|Yes| MAINTAIN4[Continue\nCombination Therapy]:::success
    GOAL4 -->|No| STEP5

    subgraph STEP5 [Step 5: Residual Risk]
        S5A{Identify Residual\nRisk Source}:::assess
        S5A -->|ApoB elevated\ndespite LDL-C at goal| S5B[Continue\nintensification]:::urgent
        S5A -->|TG 135–499 +\nASCVD or high risk| S5C[Add Icosapent\nEthyl 2g BID]:::outcome
        S5A -->|Lp*a* ≥ 125 nmol/L| S5D[Document as risk\nmodifier; maximize\nall other therapies]:::caution
    end

    MAINTAIN1 --> FU[Follow-Up\nPer Protocol]:::admin
    MAINTAIN2 --> FU
    MAINTAIN3 --> FU
    MAINTAIN4 --> FU
    STEP5 --> FU

    FU --> FUTYPE{Patient\nStability}
    FUTYPE -->|Newly stabilized| FU3[q3–6 months]:::admin
    FUTYPE -->|Established stable| FU12[Annually]:::admin
    FUTYPE -->|Dose change| FU48[4–8 weeks]:::admin
```

---

## Medication Summary by Step

| Step | Agent(s) Added | Expected Additional LDL-C Reduction |
|:-----|:---------------|:------------------------------------|
| 1 | High-intensity statin | 50% or more from baseline |
| 2 | Ezetimibe | Additional 15–20% |
| 3a | PCSK9 inhibitor | Additional 50–60% |
| 3b | Inclisiran | Additional ~50% |
| 3c | Bempedoic acid | Additional 15–25% |
| 4 | Combination of Step 3 agents | Varies |
| 5 | Icosapent ethyl (TG indication) | TG reduction; ASCVD event reduction |

## Prior Authorization Cross-Reference

PCSK9 inhibitors and inclisiran require prior authorization. See [11 — Prior Authorization]({% link clinical/11-prior-authorization.md %}) for templates and documentation requirements.

---

## Version History

| Version | Date | Description |
|:--------|:-----|:------------|
| 1.0.0 | 2026-03-30 | Initial release |
