---
layout: default
title: "Risk Stratification Flow"
parent: Workflows
nav_order: 2
version: "1.0.0"
last_updated: "2026-03-30"
---

# Risk Stratification Flowchart

Visual representation of the risk stratification process described in [04 — Risk Stratification]({% link clinical/04-risk-stratification.md %}).

---

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#ffffff
    classDef assess fill:#264653,stroke:#1d3557,color:#ffffff
    classDef caution fill:#e76f51,stroke:#c1440e,color:#ffffff
    classDef urgent fill:#d62828,stroke:#9d0208,color:#ffffff
    classDef admin fill:#6c757d,stroke:#495057,color:#ffffff
    classDef outcome fill:#2196F3,stroke:#1565C0,color:#ffffff
    classDef derisk fill:#52b788,stroke:#2d6a4f,color:#ffffff

    START[Patient Assessed]:::entry --> ASCVD{Established\nASCVD?}

    ASCVD -->|Yes| VERYHIGH[Very High Risk\nLDL-C < 55 mg/dL\nApoB < 65 mg/dL]:::urgent
    ASCVD -->|No| LDL190{LDL-C\n≥ 190 mg/dL?}

    LDL190 -->|Yes| FHEVAL[Evaluate for FH\nSee FH Pathway]:::caution
    FHEVAL --> HIGH[High Risk\nLDL-C < 70 mg/dL\nApoB < 80 mg/dL]:::urgent
    LDL190 -->|No| PREVENT[Calculate\nPREVENT Risk]:::assess

    PREVENT --> RISKCAT{10-Year\nRisk Category}

    RISKCAT -->|≥ 10%| HIGH
    RISKCAT -->|5–9.9%| INTERMEDIATE[Intermediate Risk]:::caution
    RISKCAT -->|3–4.9%| BORDERLINE[Borderline Risk]:::caution
    RISKCAT -->|< 3%| LOW[Low Risk]:::entry

    INTERMEDIATE --> ENHANCERS{Risk\nEnhancers\nPresent?}
    BORDERLINE --> ENHANCERS

    ENHANCERS -->|Yes, ≥ 1| ADVANCED{Order Advanced\nTesting}:::assess
    ENHANCERS -->|No| SDM[Shared Decision\nMaking re: Statin]:::assess

    ADVANCED --> APOB[ApoB]:::assess
    ADVANCED --> LPA[Lp*a*\nif not done]:::assess
    ADVANCED --> CAC[CAC Score]:::assess

    APOB --> INTEGRATE[Integrate\nAll Results]:::assess
    LPA --> INTEGRATE
    CAC --> INTEGRATE

    INTEGRATE --> CACRESULT{CAC\nResult?}

    CACRESULT -->|CAC = 0| APOBCHECK{ApoB Below\nTarget?}
    CACRESULT -->|CAC 1–99| UPINT[Reclassify\nUpward]:::caution
    CACRESULT -->|CAC 100–299| HIGHMOD[High-Intensity\nStatin]:::urgent
    CACRESULT -->|CAC ≥ 300| HIGHAGG[Aggressive\nLDL-C Lowering\nPer 2026 Guidelines]:::urgent

    APOBCHECK -->|Yes| DERISK[De-Risk:\nDefer Statin\nLifestyle Focus]:::derisk
    APOBCHECK -->|No| TREAT[ApoB Elevated:\nInitiate Therapy\nDespite CAC = 0]:::caution

    UPINT --> FINALCAT[Assign Final\nRisk Category]:::outcome
    HIGHMOD --> FINALCAT
    HIGHAGG --> FINALCAT
    TREAT --> FINALCAT
    SDM --> FINALCAT

    LOW --> LPA2[Measure Lp*a*\nif not done]:::assess
    LPA2 --> LPARESULT{Lp*a*\n≥ 125 nmol/L?}
    LPARESULT -->|Yes| ENHANCERS
    LPARESULT -->|No| LOWFINAL[Confirmed Low Risk\nLifestyle Modification]:::derisk

    VERYHIGH --> TX[Proceed to\nTreatment Pathway]:::outcome
    HIGH --> TX
    FINALCAT --> TX
    DERISK --> FOLLOWUP[Follow-Up\nPer Protocol]:::admin
    LOWFINAL --> FOLLOWUP

    TX --> TXPATH["See 05 — Treatment\nPathways"]:::outcome
```

---

## Key Decision Points

| Node | Clinical Document Reference |
|:-----|:---------------------------|
| Established ASCVD check | [04 — Risk Stratification, Section 2.0]({% link clinical/04-risk-stratification.md %}#20-step-1--identify-established-ascvd) |
| PREVENT calculation | [04 — Risk Stratification, Section 3.0]({% link clinical/04-risk-stratification.md %}#30-step-2--aha-prevent-risk-calculation) |
| Risk enhancers | [04 — Risk Stratification, Section 4.0]({% link clinical/04-risk-stratification.md %}#40-step-3--evaluate-risk-enhancers) |
| ApoB assessment | [04 — Risk Stratification, Section 5.0]({% link clinical/04-risk-stratification.md %}#50-apolipoprotein-b-apob-assessment) |
| Lp(a) assessment | [04 — Risk Stratification, Section 6.0]({% link clinical/04-risk-stratification.md %}#60-lipoprotein-a-assessment) |
| CAC scoring | [04 — Risk Stratification, Section 7.0]({% link clinical/04-risk-stratification.md %}#70-coronary-artery-calcium-cac-scoring) |
| De-risking (CAC=0 + ApoB negative) | [04 — Risk Stratification, Section 7.4]({% link clinical/04-risk-stratification.md %}#74-de-risking-cac--0) |
| FH evaluation | [07 — FH Pathway]({% link clinical/07-fh-pathway.md %}) |

---

## Version History

| Version | Date | Description |
|:--------|:-----|:------------|
| 1.0.0 | 2026-03-30 | Initial release |
