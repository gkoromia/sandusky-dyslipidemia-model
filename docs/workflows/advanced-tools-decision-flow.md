---
layout: default
title: "Advanced Tools Decision Flow"
parent: Workflows
nav_order: 4
version: "1.0.0"
last_updated: "2026-03-30"
---

# Advanced Tools Decision Flowchart

Visual guide for determining which advanced diagnostic tool(s) to order based on clinical scenario. See [06 — Advanced Tools]({% link clinical/06-advanced-tools.md %}) for detailed protocols.

---

```mermaid
flowchart TD
    classDef entry fill:#2d6a4f,stroke:#1b4332,color:#ffffff
    classDef assess fill:#264653,stroke:#1d3557,color:#ffffff
    classDef caution fill:#e76f51,stroke:#c1440e,color:#ffffff
    classDef urgent fill:#d62828,stroke:#9d0208,color:#ffffff
    classDef admin fill:#6c757d,stroke:#495057,color:#ffffff
    classDef tool fill:#2196F3,stroke:#1565C0,color:#ffffff

    START[Clinical Question\nRequiring Advanced\nTesting]:::entry --> Q1{What is the\nclinical question?}

    Q1 -->|Atherogenic particle\nburden| APOB_PATH
    Q1 -->|Inherited risk\nfactor| LPA_PATH
    Q1 -->|Subclinical\natherosclerosis| IMAGING_PATH
    Q1 -->|Atherogenic\ndyslipidemia\ncharacterization| NMR_PATH
    Q1 -->|Symptomatic\ncoronary evaluation| CCTA_PATH

    subgraph APOB_PATH [ApoB Pathway]
        APOB_Q{Scenario?}:::assess
        APOB_Q -->|LDL-C / non-HDL-C\ndiscordance| APOB[Order ApoB]:::tool
        APOB_Q -->|MetSyn or T2DM| APOB
        APOB_Q -->|TG 150–499 mg/dL| APOB
        APOB_Q -->|At/near LDL-C goal\nassess residual risk| APOB
        APOB_Q -->|On-treatment\nmonitoring| APOB
    end

    subgraph LPA_PATH [Lp*a* Pathway]
        LPA_Q{Lp*a* Previously\nMeasured?}:::assess
        LPA_Q -->|No| LPA[Order Lp*a*\nnmol/L]:::tool
        LPA_Q -->|Yes| LPA_DONE[Use Prior Result\nNo repeat needed]:::admin
    end

    subgraph NMR_PATH [NMR LipoProfile Pathway]
        NMR_Q{Scenario?}:::assess
        NMR_Q -->|TG 150–499 +\nsuspected atherogenic\ndyslipidemia| NMR[Order Labcorp\nNMR LipoProfile]:::tool
        NMR_Q -->|MetSyn / T2DM\nwith discordant\nLDL-C vs ApoB| NMR
        NMR_Q -->|Persistent events\ndespite LDL-C\nat target| NMR
        NMR_Q -->|Suspected insulin\nresistance| NMR
    end

    subgraph IMAGING_PATH [Imaging Pathway]
        IMG_Q{Patient\nCategory?}:::assess
        IMG_Q -->|Borderline/intermediate\nrisk, statin decision\nuncertain| CAC[Order CAC\nScore]:::tool
        IMG_Q -->|Cervical bruit,\nprior stroke/TIA,\nknown stenosis| CAROTID[Order Carotid\nDuplex]:::tool
        IMG_Q -->|Established ASCVD\nor committed to\nhigh-intensity statin| NOIMG[No imaging\nneeded for\nrisk stratification]:::admin
    end

    subgraph CCTA_PATH [CCTA Pathway]
        CCTA_Q{Meets ALL\ncriteria?}:::assess
        CCTA_CRIT[• Symptomatic\n• Low-intermediate\n  pre-test probability\n• Not in AFib\n• BMI ≤ 40\n• No prior stents]:::assess
        CCTA_Q -->|Yes, all met| CCTA[Order CCTA]:::tool
        CCTA_Q -->|No, ≥ 1 not met| NOCCTA[CCTA Not\nAppropriate\nConsider alternatives]:::caution
        CCTA_CRIT --> CCTA_Q
    end

    APOB --> INTERPRET[Interpret Results\nin Context of\nFull Risk Profile]:::assess
    LPA --> INTERPRET
    NMR --> INTERPRET
    CAC --> INTERPRET
    CAROTID --> INTERPRET
    CCTA --> INTERPRET

    INTERPRET --> ACTION[Update Risk\nCategory and\nTreatment Plan]:::entry
```

---

## Quick Reference: When to Order Each Test

| Test | Order When | Do NOT Order When |
|:-----|:-----------|:-----------------|
| **ApoB** | New patients; discordance; MetSyn/DM; at/near target; monitoring | — (broadly useful) |
| **Lp(a)** | All new patients (one-time) | Already measured (genetically determined) |
| **NMR LipoProfile** | Atherogenic dyslipidemia suspected; TG 150–499; discordant results; persistent events | Routine screening; clear-cut cases |
| **CAC Score** | Borderline/intermediate risk; statin decision uncertainty | Established ASCVD; age < 40 or > 75; prior stents/CABG |
| **Carotid Duplex** | Bruit; prior stroke/TIA; known stenosis surveillance | Routine screening without clinical indication |
| **CCTA** | Symptomatic + low-intermediate risk + sinus rhythm + BMI ≤ 40 + no stents | Asymptomatic; AFib; BMI > 40; prior stents |

---

## Version History

| Version | Date | Description |
|:--------|:-----|:------------|
| 1.0.0 | 2026-03-30 | Initial release |
