---
layout: default
title: "Risk Stratification Flow"
parent: Workflows
nav_order: 2
version: "1.1.0"
last_updated: "2026-09-29"
---

# Risk Stratification Flowchart

Visual representation of the risk stratification process described in [04 — Risk Stratification]({% link clinical/04-risk-stratification.md %}).

---

The process is split into six short charts. Parts 1 and 2 sort every patient into a starting risk category. Parts 3–6 continue for patients whose category needs more testing before treatment is decided.

{% include workflow_legend.html %}

## Part 1 — Established ASCVD or LDL-C ≥ 190

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    START[Patient Assessed]:::entry --> ASCVD{Established<br>ASCVD?}

    ASCVD -->|Yes| VERYHIGH["Very High Risk<br>LDL-C &lt; 55 mg/dL<br>ApoB &lt; 65 mg/dL"]:::urgent
    ASCVD -->|No| LDL190{LDL-C<br>≥ 190 mg/dL?}

    LDL190 -->|Yes| FHEVAL[Evaluate for FH<br>See FH Pathway]:::caution
    FHEVAL --> HIGH["High Risk<br>LDL-C &lt; 70 mg/dL<br>ApoB &lt; 80 mg/dL"]:::urgent
    LDL190 -->|No| P2[Continue to Part 2:<br>PREVENT Risk]:::link

    VERYHIGH --> TX["Proceed to<br>Treatment Pathway<br>(document 05)"]:::treat
    HIGH --> TX
```

## Part 2 — PREVENT Risk Category

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    PREVENT[Calculate<br>PREVENT Risk]:::assess --> RISKCAT{10-Year<br>Risk Category}

    RISKCAT -->|≥ 10%| HIGH["High Risk<br>LDL-C &lt; 70 mg/dL<br>ApoB &lt; 80 mg/dL"]:::urgent
    RISKCAT -->|5–9.9%| INTERMEDIATE[Intermediate<br>Risk]:::caution
    RISKCAT -->|3–4.9%| BORDERLINE[Borderline<br>Risk]:::caution
    RISKCAT -->|"&lt; 3%"| LOW[Low Risk]:::entry

    HIGH --> TX["Proceed to<br>Treatment Pathway<br>(document 05)"]:::treat
    INTERMEDIATE --> P3[Continue to Part 3:<br>Risk Enhancers]:::link
    BORDERLINE --> P3
    LOW --> P6[Continue to Part 6:<br>Confirm Low Risk]:::link
```

## Part 3 — Risk Enhancers and Advanced Testing

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    IN[Borderline or<br>Intermediate Risk]:::caution --> ENHANCERS{Risk<br>Enhancers<br>Present?}

    ENHANCERS -->|Yes, ≥ 1| ADVANCED[Order Advanced<br>Testing]:::treat
    ENHANCERS -->|No| SDM[Shared Decision<br>Making re: Statin]:::assess

    ADVANCED --> APOB[ApoB]:::assess
    ADVANCED --> LPA["Lp(a)<br>if not done"]:::assess
    ADVANCED --> CAC[CAC Score]:::assess

    APOB --> INTEGRATE[Integrate<br>All Results]:::assess
    LPA --> INTEGRATE
    CAC --> INTEGRATE
    INTEGRATE --> P4[Continue to Part 4:<br>CAC Result]:::link

    SDM --> FINALCAT[Assign Final<br>Risk Category]:::treat
    FINALCAT --> TX["Proceed to<br>Treatment Pathway<br>(document 05)"]:::treat
```

## Part 4 — Interpreting the CAC Score

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    CACRESULT{CAC<br>Result?}

    CACRESULT -->|CAC = 0| P5[Continue to Part 5:<br>ApoB Check]:::link
    CACRESULT -->|CAC 1–99| UPINT[Reclassify<br>Upward]:::caution
    CACRESULT -->|CAC 100–299| HIGHMOD[High-Intensity<br>Statin]:::urgent
    CACRESULT -->|CAC ≥ 300| HIGHAGG[Aggressive<br>LDL-C Lowering<br>Per 2026 Guidelines]:::urgent

    UPINT --> FINALCAT[Assign Final<br>Risk Category]:::treat
    HIGHMOD --> FINALCAT
    HIGHAGG --> FINALCAT
    FINALCAT --> TX["Proceed to<br>Treatment Pathway<br>(document 05)"]:::treat
```

## Part 5 — CAC = 0: De-Risking Check

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    CAC0[CAC = 0]:::entry --> APOBCHECK{ApoB Below<br>Target?}

    APOBCHECK -->|Yes| DERISK[De-Risk:<br>Defer Statin<br>Lifestyle Focus]:::entry
    APOBCHECK -->|No| TREAT[ApoB Elevated:<br>Initiate Therapy<br>Despite CAC = 0]:::caution

    DERISK --> FOLLOWUP[Follow-Up<br>Per Protocol]:::admin
    TREAT --> FINALCAT[Assign Final<br>Risk Category]:::treat
    FINALCAT --> TX["Proceed to<br>Treatment Pathway<br>(document 05)"]:::treat
```

## Part 6 — Confirming Low Risk

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    LOW[Low Risk<br>PREVENT &lt; 3%]:::entry --> LPA2["Measure Lp(a)<br>if not done"]:::assess
    LPA2 --> LPARESULT{"Lp(a)<br>≥ 125 nmol/L?"}
    LPARESULT -->|Yes| ENH[Go to Part 3:<br>Evaluate Risk Enhancers]:::link
    LPARESULT -->|No| LOWFINAL[Confirmed Low Risk<br>Lifestyle Modification]:::entry
    LOWFINAL --> FOLLOWUP[Follow-Up<br>Per Protocol]:::admin
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
| 1.1.0 | 2026-09-29 | Split into smaller charts so text renders at full size; fixed line breaks that printed as literal escape codes; accessible color palette and shared legend |
