---
layout: default
title: "PREVENT Calculator"
parent: Tools
nav_order: 3
version: "1.0.0"
last_updated: "2026-04-03"
---

# AHA PREVENT Risk Calculator

The Sandusky Dyslipidemia Model uses the official American Heart Association (AHA) PREVENT calculator for estimating 10-year and 30-year total cardiovascular disease (CVD) risk, including ASCVD and heart failure components.

{: .note }
> **Citation:** Khan SS, Matsushita K, Sang Y, et al. Development and validation of the American Heart Association's PREVENT equations. *Circulation*. 2024;149(6):e430–e449.

<div style="text-align: center; margin: 40px 0;">
  <a href="https://professional.heart.org/en/guidelines-and-statements/prevent-calculator" target="_blank" rel="noopener noreferrer"
     style="display: inline-block; padding: 16px 48px; font-size: 1.15em; font-weight: bold; background: #264653; color: white; border-radius: 8px; text-decoration: none;">
    Open AHA PREVENT Calculator →
  </a>
  <p style="margin-top: 12px; font-size: 0.9em; color: #555;">Opens on the American Heart Association website</p>
</div>

## About the PREVENT Equations

The PREVENT (Predicting Risk of CVD EVENTs) equations were developed and validated by the American Heart Association and published in *Circulation* (2024). They replace the older Pooled Cohort Equations (PCE) as the preferred risk estimation tool in the **2026 ACC/AHA/Multisociety Guidelines on the Management of Dyslipidemia**.

Key features of the PREVENT equations:

- Estimates **10-year and 30-year total CVD risk** (ASCVD + heart failure combined)
- Also provides ASCVD-specific and HF-specific risk estimates
- Incorporates **eGFR** and **BMI** as predictors — better accounting for CKD and obesity
- Validated in diverse U.S. populations
- Does **not** require race/ethnicity as an input (unlike the PCE)

## Required Inputs

| Input | Range |
|:------|:------|
| Age | 30–79 years |
| Sex | Male / Female |
| Systolic blood pressure (mm Hg) | — |
| Total cholesterol (mg/dL) | — |
| HDL-C (mg/dL) | — |
| eGFR (mL/min/1.73 m²) | — |
| BMI (kg/m²) | — |
| Current smoker | Yes / No |
| Diabetes | Yes / No |
| On antihypertensive medication | Yes / No |
| On statin | Yes / No |

**Optional:** HbA1c (if diabetic), urine albumin-to-creatinine ratio (UACR)

## Risk Categories (2026 ACC/AHA Guidelines)

| 10-Year Total CVD Risk | Category | Implication |
|:-----------------------|:---------|:------------|
| < 3% | **Low** | Lifestyle modification; pharmacotherapy generally not indicated |
| 3% to < 5% | **Borderline** | Evaluate risk enhancers; shared decision-making for statin therapy |
| 5% to < 10% | **Intermediate** | Moderate-to-high intensity statin indicated; evaluate risk enhancers |
| ≥ 10% | **High** | High-intensity statin; aggressive lipid lowering |

{: .warning }
> The PREVENT calculator estimates **population-level** risk. Final risk category assignment at The Sandusky Dyslipidemia Model integrates the PREVENT score with risk enhancers, ApoB, Lp(a), and CAC scoring per [04 — Risk Stratification]({% link clinical/04-risk-stratification.md %}).

## References

1. Khan SS, Matsushita K, Sang Y, et al. Development and validation of the American Heart Association's PREVENT equations. *Circulation*. 2024;149(6):e430–e449.
2. 2026 ACC/AHA/Multisociety Guideline on the Management of Dyslipidemia. *J Am Coll Cardiol*. 2026.
