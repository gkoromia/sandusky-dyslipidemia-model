---
layout: default
title: "Statin Intolerance Flow"
parent: Workflows
nav_order: 6
version: "1.1.0"
last_updated: "2026-09-29"
---

# Statin Intolerance Pathway Flowchart

Visual representation of the statin intolerance evaluation and management pathway described in [08 — Statin Intolerance]({% link clinical/08-statin-intolerance.md %}).

---

The pathway is split into four charts: ruling out secondary causes, checking the CK level, the one-time rechallenge, and the statin-free regimen.

{% include workflow_legend.html %}

## Part 1 — Evaluation and Secondary Causes

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    REPORT[Patient Reports<br>Statin Intolerance]:::entry

    REPORT --> EVAL[Characterize<br>Symptoms]:::assess
    EVAL --> SECONDARY[Rule Out Secondary<br>Causes of Myalgia]:::assess

    SECONDARY --> SECCHECK{Secondary<br>Cause Found?}
    SECCHECK -->|Yes — Hypothyroid,<br>Vit D deficiency,<br>drug interaction, etc.| TREAT_SEC[Address Secondary<br>Cause First]:::caution
    TREAT_SEC --> RETRY[Reattempt Original<br>Statin After<br>Cause Resolved]:::assess
    RETRY --> RETRY_RESULT{Tolerated<br>Now?}
    RETRY_RESULT -->|Yes| CONTINUE[Continue Statin<br>Therapy]:::entry
    RETRY_RESULT -->|No| RC[Part 3:<br>One-Time Rechallenge]:::link

    SECCHECK -->|No secondary<br>cause identified| CK[Continue to Part 2:<br>CK Level]:::link
```

## Part 2 — CK Level

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    CK_CHECK{CK Level?}

    CK_CHECK -->|CK > 10× ULN| RHABDO[Discontinue Statin<br>IV Fluids<br>Monitor Renal Function]:::urgent
    CK_CHECK -->|CK 4–10× ULN| MYOPATHY[True Myopathy<br>Discontinue Statin<br>Recheck CK 2–4 weeks]:::caution
    CK_CHECK -->|"CK &lt; 4× ULN<br>or not checked"| MYALGIA[Myalgia Without<br>Myopathy<br>Most Common]:::assess

    MYOPATHY --> WAIT[Wait for CK<br>Normalization]:::admin
    WAIT --> RC[Part 3:<br>One-Time Rechallenge]:::link
    MYALGIA --> RC

    RHABDO --> RHABDO_RESOLVE[After Recovery:<br>Do NOT rechallenge<br>Proceed directly to<br>Statin-Free Regimen]:::caution
    RHABDO_RESOLVE --> SF[Part 4:<br>Statin-Free Regimen]:::link
```

## Part 3 — One-Time Rechallenge

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    IN[From Part 1 or 2:<br>myalgia, resolved myopathy,<br>or failed retry]:::link --> RC_START

    RC_START[Select Different Statin<br>Prefer rosuvastatin<br>or pitavastatin]:::assess
    RC_START --> RC_DOSE[Start Lowest<br>Available Dose<br>Consider alternate-day]:::treat
    RC_DOSE --> RC_TRIAL[Trial Period<br>4–8 weeks]:::admin
    RC_TRIAL --> RC_CHECK[Assess<br>Tolerability]:::assess

    RC_CHECK --> RC_RESULT{Tolerated?}

    RC_RESULT -->|Yes| TITRATE[Titrate to Highest<br>Tolerated Dose]:::entry
    TITRATE --> LIPIDS1[Recheck Lipids<br>+ ApoB 4–8 weeks]:::admin
    LIPIDS1 --> GOAL1{At Target?}
    GOAL1 -->|Yes| MAINTAIN[Maintain Regimen]:::entry
    GOAL1 -->|No| ADD_EZE[Add Ezetimibe<br>10 mg daily]:::treat

    RC_RESULT -->|No| CONFIRMED[Confirmed Statin<br>Intolerance<br>Document per<br>Section 6.0]:::caution
    CONFIRMED --> SF[Part 4:<br>Statin-Free Regimen]:::link
```

## Part 4 — Statin-Free Regimen

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#fff
    classDef assess fill:#264653,stroke:#16303a,color:#fff
    classDef treat fill:#1565c0,stroke:#0d47a1,color:#fff
    classDef caution fill:#c2410c,stroke:#9a3412,color:#fff
    classDef urgent fill:#b42318,stroke:#7a1a12,color:#fff
    classDef admin fill:#5f6770,stroke:#454c53,color:#fff
    classDef link fill:#fff,stroke:#264653,stroke-width:2px,stroke-dasharray:5 4,color:#264653

    IN[From Part 2 after rhabdomyolysis,<br>or Part 3 confirmed intolerance]:::link --> SF1

    SF1[Start Ezetimibe 10 mg<br>+ Bempedoic Acid 180 mg<br>or Nexlizet combo]:::treat
    SF1 --> SF_LABS[Recheck Lipids<br>+ ApoB 4–8 weeks]:::admin
    SF_LABS --> SF_GOAL{At Target?}
    SF_GOAL -->|Yes| SF_MAINTAIN[Maintain<br>Statin-Free Regimen]:::entry
    SF_GOAL -->|No| SF_ESCALATE[Add PCSK9i<br>or Inclisiran]:::treat

    SF_ESCALATE --> PA[Prior Authorization<br>Required]:::admin
    PA --> SF_LABS2[Recheck Lipids<br>+ ApoB 4–8 weeks]:::admin
    SF_LABS2 --> SF_GOAL2{At Target?}
    SF_GOAL2 -->|Yes| SF_FINAL[Maintain<br>Full Regimen]:::entry
    SF_GOAL2 -->|No| SF_MAX[Maximum Statin-Free:<br>Ezetimibe + Bempedoic Acid<br>+ PCSK9i or Inclisiran<br>Reassess adherence & FH]:::urgent
```

---

## Key Decision Points

| Node | Clinical Document Reference |
|:-----|:---------------------------|
| Symptom characterization | [08 — Statin Intolerance, Section 3.1]({% link clinical/08-statin-intolerance.md %}#31-characterize-the-symptoms) |
| Secondary cause evaluation | [08 — Statin Intolerance, Section 3.2]({% link clinical/08-statin-intolerance.md %}#32-rule-out-secondary-causes-of-myalgia) |
| CK assessment | [08 — Statin Intolerance, Section 3.3]({% link clinical/08-statin-intolerance.md %}#33-creatine-kinase-ck-assessment) |
| Rechallenge protocol | [08 — Statin Intolerance, Section 4.0]({% link clinical/08-statin-intolerance.md %}#40-one-time-rechallenge-protocol) |
| Statin-free regimen | [08 — Statin Intolerance, Section 5.0]({% link clinical/08-statin-intolerance.md %}#50-statin-free-regimen) |
| Documentation | [08 — Statin Intolerance, Section 6.0]({% link clinical/08-statin-intolerance.md %}#60-documentation-requirements) |
| Prior authorization | [11 — Prior Authorization]({% link clinical/11-prior-authorization.md %}) |

---

## Version History

| Version | Date | Description |
|:--------|:-----|:------------|
| 1.0.0 | 2026-03-30 | Initial release |
| 1.1.0 | 2026-09-29 | Split into smaller charts so text renders at full size; fixed line breaks that printed as literal escape codes; accessible color palette and shared legend |
