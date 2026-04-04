---
layout: default
title: "FH Pathway Flow"
parent: Workflows
nav_order: 5
version: "1.0.0"
last_updated: "2026-03-30"
---

# Familial Hypercholesterolemia Pathway Flowchart

Visual representation of the FH evaluation and management pathway described in [07 — FH Pathway]({% link clinical/07-fh-pathway.md %}).

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

    TRIGGER[FH Suspected\nLDL-C ≥ 190 mg/dL\nTendon xanthomas\nFamily history]:::entry

    TRIGGER --> SECONDARY[Rule Out\nSecondary Causes]:::assess
    SECONDARY --> DLCN[Calculate DLCN\nScore]:::assess

    DLCN --> SCORE{DLCN\nScore?}

    SCORE -->|≥ 8\nDefinite FH| DEFINITE[Definite FH]:::urgent
    SCORE -->|6–7\nProbable FH| PROBABLE[Probable FH]:::caution
    SCORE -->|3–5\nPossible FH| POSSIBLE[Possible FH]:::assess
    SCORE -->|< 3\nUnlikely| STANDARD[Standard\nDyslipidemia\nManagement]:::success

    DEFINITE --> GENETIC[Order Genetic\nTesting]:::outcome
    PROBABLE --> GENETIC
    POSSIBLE --> CONSIDER{Clinical\nSuspicion\nStrong?}
    CONSIDER -->|Yes| GENETIC
    CONSIDER -->|No| TREATPOSS[Treat Based on\nRisk Profile]:::assess

    GENETIC --> RESULT{Mutation\nIdentified?}

    RESULT -->|Yes — LDLR,\nAPOB, or PCSK9| CONFIRMED[FH Confirmed\nGenetically]:::urgent
    RESULT -->|No mutation\nfound| CLINICAL[Clinical FH\nDLCN ≥ 6\nStill Valid]:::caution

    CONFIRMED --> CASCADE[Initiate Cascade\nScreening]:::outcome
    CLINICAL --> CASCADE

    CASCADE --> FAMILY[Screen First-Degree\nRelatives]:::admin
    FAMILY --> FAMMETHOD{Index Patient\nMutation Known?}
    FAMMETHOD -->|Yes| TARGETED[Targeted Genetic\nTest in Relatives]:::outcome
    FAMMETHOD -->|No| LIPIDSCREEN[Lipid Panel +\nDLCN in Relatives]:::outcome

    TARGETED --> FAMRESULT{Relative\nAffected?}
    LIPIDSCREEN --> FAMRESULT
    FAMRESULT -->|Yes| FAMREFER[Refer Relative\nfor Treatment]:::admin
    FAMRESULT -->|No| FAMCLEAR[Reassure;\nNo Further Action]:::success

    CONFIRMED --> SEVERITY{Suspected\nSeverity?}
    CLINICAL --> SEVERITY

    SEVERITY -->|HeFH\nLDL-C typically\n190–400 mg/dL| HEFH_TX[HeFH Treatment]:::outcome
    SEVERITY -->|Suspected HoFH\nLDL-C > 400\nor ≥ 300 on statin| HOFH[Refer to Tertiary\nLipid Center]:::urgent

    HEFH_TX --> TX1[Step 1: High-intensity\nstatin\nAtorvastatin 80 mg or\nRosuvastatin 40 mg]:::assess
    TX1 --> TX2[Step 2: Add\nezetimibe 10 mg]:::assess
    TX2 --> TX3[Step 3: Add\nPCSK9i or inclisiran]:::outcome
    TX3 --> GOAL{LDL-C < 70\nApoB < 80?}
    GOAL -->|Yes| MAINTAIN[Maintain Regimen\nMonitor q3–6 months]:::success
    GOAL -->|No| TX4[Step 4: Add\nbempedoic acid\nConsider referral]:::urgent

    HOFH --> HOFH_INIT[Initiate statin +\nezetimibe + PCSK9i\nwhile awaiting referral]:::urgent
```

---

## Key Decision Points

| Node | Clinical Document Reference |
|:-----|:---------------------------|
| DLCN Score calculation | [07 — FH Pathway, Section 3.0]({% link clinical/07-fh-pathway.md %}#30-clinical-diagnosis--dutch-lipid-clinic-network-dlcn-score) |
| Genetic testing | [07 — FH Pathway, Section 4.0]({% link clinical/07-fh-pathway.md %}#40-genetic-testing) |
| Cascade screening | [07 — FH Pathway, Section 5.0]({% link clinical/07-fh-pathway.md %}#50-cascade-screening) |
| HeFH treatment | [07 — FH Pathway, Section 6.0]({% link clinical/07-fh-pathway.md %}#60-treatment-of-heterozygous-fh-hefh) |
| HoFH referral | [07 — FH Pathway, Section 7.0]({% link clinical/07-fh-pathway.md %}#70-severe-fh-and-homozygous-fh-hofh) |
| Secondary causes | [09 — Secondary Dyslipidemia]({% link clinical/09-secondary-dyslipidemia.md %}) |

---

## Version History

| Version | Date | Description |
|:--------|:-----|:------------|
| 1.0.0 | 2026-03-30 | Initial release |
