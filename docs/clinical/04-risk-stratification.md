---
layout: default
title: "04 — Risk Stratification"
parent: Clinical
nav_order: 4
version: "1.0.0"
last_updated: "2026-03-30"
---

# 04 — Risk Stratification
{: .no_toc }

<details open markdown="block">
  <summary>Table of Contents</summary>
  {: .text-delta }
- TOC
{:toc}
</details>

---

## 1.0 Overview

Risk stratification is the central decision-making step in The Sandusky Dyslipidemia Model. It determines treatment intensity, the need for advanced testing, and follow-up frequency. This document describes the stepwise approach to risk assessment, integrating the AHA PREVENT equations, guideline-defined risk enhancers, and advanced tools.

See the [Risk Stratification Flowchart]({% link workflows/risk-stratification-flow.md %}) for a visual representation of this process.

## 2.0 Step 1 — Identify Established ASCVD

Before calculating risk, determine whether the patient has **established atherosclerotic cardiovascular disease (ASCVD)**:

| Condition | Qualifies as Established ASCVD |
|:----------|:-------------------------------|
| Prior myocardial infarction | Yes |
| Acute coronary syndrome (history) | Yes |
| Stable angina with obstructive CAD | Yes |
| Coronary revascularization (PCI or CABG) | Yes |
| Ischemic stroke | Yes |
| Transient ischemic attack (TIA) with carotid stenosis | Yes |
| Peripheral arterial disease (ABI < 0.9 or revascularization) | Yes |
| Carotid endarterectomy or carotid stenting | Yes |

**If established ASCVD is present:** The patient is classified as **very high risk** and proceeds directly to aggressive treatment (see [05 — Treatment Pathways]({% link clinical/05-treatment-pathways.md %})). PREVENT calculation is not required but may be performed for documentation.

## 3.0 Step 2 — AHA PREVENT Risk Calculation

For patients **without** established ASCVD, calculate 10-year and 30-year total cardiovascular disease (CVD) risk using the AHA Predicting Risk of cardiovascular disease EVENTs (PREVENT) equations [1].

### 3.1 PREVENT Calculator Inputs

| Input | Required | Source |
|:------|:---------|:-------|
| Age (30–79 years) | Yes | Patient history |
| Sex | Yes | Patient history |
| Systolic blood pressure (mm Hg) | Yes | Clinic measurement |
| Total cholesterol (mg/dL) | Yes | Laboratory |
| HDL-C (mg/dL) | Yes | Laboratory |
| Current diabetes status | Yes | History or HbA1c ≥ 6.5% |
| Current smoking status | Yes | Patient history |
| eGFR (mL/min/1.73 m²) | Yes | Laboratory (CKD-EPI) |
| BMI (kg/m²) | Yes | Clinic measurement |
| Antihypertensive medication use | Yes | Medication review |
| Statin use | Yes | Medication review |
| HbA1c (%) | Optional | Laboratory (improves prediction in diabetics) |
| UACR (mg/g) | Optional | Laboratory (improves prediction) |
| Social Deprivation Index (SDI) | Optional | Geographic/zip code lookup |

### 3.2 PREVENT Risk Categories

The 2026 ACC/AHA guidelines [2] define the following risk categories based on 10-year predicted ASCVD risk:

| 10-Year Risk | Category | Treatment Implications |
|:-------------|:---------|:----------------------|
| < 3% | **Low** | Lifestyle modification; pharmacotherapy generally not indicated |
| 3% to < 5% | **Borderline** | Consider risk enhancers; shared decision-making for statin therapy |
| 5% to < 10% | **Intermediate** | Moderate-to-high intensity statin indicated; evaluate risk enhancers |
| ≥ 10% | **High** | High-intensity statin; treat as high risk |

{: .note }
> The PREVENT equations produce **total CVD risk** (ASCVD + heart failure), not ASCVD risk alone. The PREVENT model also provides ASCVD-specific and HF-specific estimates. Use the total CVD risk for primary risk categorization per the 2026 guidelines [2]. An interactive calculator is available at [Tools — PREVENT Calculator]({% link tools/index.md %}).

### 3.3 30-Year Risk

For patients aged 30–59 years with low 10-year risk, the 30-year risk estimate provides additional context regarding lifetime exposure to atherogenic lipoproteins. Elevated 30-year risk (≥ 39%) may support earlier initiation of lifestyle modification and consideration of pharmacotherapy [1].

## 4.0 Step 3 — Evaluate Risk Enhancers

For patients in the **borderline** (3–4.9%) or **intermediate** (5–9.9%) risk categories, risk enhancers are used to inform shared decision-making about statin initiation and to identify candidates for advanced testing.

### 4.1 Risk Enhancers per 2026 ACC/AHA Guidelines

| # | Risk Enhancer | Notes |
|:--|:--------------|:------|
| 4.1.1 | Family history of premature ASCVD | Male first-degree relative < 55 years; female < 65 years |
| 4.1.2 | Persistently elevated LDL-C ≥ 160 mg/dL | Despite lifestyle measures |
| 4.1.3 | Metabolic syndrome | ≥ 3 of: waist circumference, elevated TG, low HDL-C, elevated BP, elevated fasting glucose |
| 4.1.4 | Chronic kidney disease | eGFR 15–59 mL/min/1.73 m² (not on dialysis) |
| 4.1.5 | Chronic inflammatory conditions | Rheumatoid arthritis, systemic lupus erythematosus, psoriasis, HIV |
| 4.1.6 | History of premature menopause | < 40 years |
| 4.1.7 | Pregnancy-associated conditions | Preeclampsia, pregnancy-associated hypertension |
| 4.1.8 | South Asian ancestry | Well-established excess ASCVD risk [3] |
| 4.1.9 | Elevated lipoprotein(a) | ≥ 125 nmol/L (see [Section 6.0](#60-lipoprotein-a-assessment)) |
| 4.1.10 | Elevated apolipoprotein B | Discordant with LDL-C (see [Section 5.0](#50-apolipoprotein-b-apob-assessment)) |
| 4.1.11 | Ankle-brachial index < 0.9 | Subclinical PAD |
| 4.1.12 | Elevated high-sensitivity troponin | If available, persistently elevated |

### 4.2 Clinical Action

- **≥ 1 risk enhancer present:** Favors statin initiation in borderline/intermediate risk patients. Consider advanced testing (CAC scoring, ApoB, Lp(a)) to further refine risk.
- **No risk enhancers:** Shared decision-making regarding statin therapy based on patient preferences and calculated risk.

## 5.0 Apolipoprotein B (ApoB) Assessment

ApoB provides a direct count of atherogenic lipoprotein particles (one ApoB molecule per VLDL, IDL, LDL, and Lp(a) particle). It is the preferred measure of atherogenic burden when LDL-C may underestimate risk [4, 5].

### 5.1 When to Measure ApoB

| Clinical Scenario | Rationale |
|:------------------|:----------|
| LDL-C and non-HDL-C are discordant | ApoB resolves which metric better reflects true atherogenic burden |
| Triglycerides 150–499 mg/dL | LDL-C calculation less accurate; ApoB is unaffected |
| Metabolic syndrome or type 2 diabetes | High prevalence of LDL-C/particle number discordance (more small dense particles) |
| Patient at or near guideline LDL-C target | ApoB used to identify residual risk and justify "lower is better" intensification |
| Obesity (BMI ≥ 30) | Frequent discordance between LDL-C and ApoB |
| After initiation of lipid-lowering therapy | ApoB may reveal inadequate particle lowering despite acceptable LDL-C |

### 5.2 ApoB Thresholds

The following thresholds are used in this clinic, aligned with the 2026 ACC/AHA guidelines [2] and the European Atherosclerosis Society (EAS) consensus [5]:

| Risk Category | ApoB Target |
|:--------------|:------------|
| Very high risk (established ASCVD) | < 65 mg/dL |
| High risk (10-year risk ≥ 10%, DM with risk factors) | < 80 mg/dL |
| Intermediate risk | < 90 mg/dL |
| "Lower is better" intensification | Lowest achievable with tolerated therapy |

### 5.3 Clinical Action on ApoB Result

- **ApoB above target despite LDL-C at goal:** This clinic treats this as evidence of residual atherogenic risk. Consider treatment intensification per the "lower is better" philosophy (see [05 — Treatment Pathways, Section 1.0]({% link clinical/05-treatment-pathways.md %}#10-treatment-philosophy)).
- **ApoB below target with LDL-C above goal:** Less common; reassuring. Continue current therapy; recheck.

## 6.0 Lipoprotein(a) Assessment

Lipoprotein(a) \[Lp(a)\] is a genetically determined, largely immutable risk factor for ASCVD and calcific aortic valve disease [6]. It is measured once per lifetime (repeat testing only if the initial result was borderline and a different assay is used).

### 6.1 Measurement

- **Preferred unit:** nmol/L (mass-independent, isoform-insensitive)
- **Threshold for elevated risk:** ≥ 125 nmol/L
- **When to measure:** All new patients at The Sandusky Dyslipidemia Model clinic (one-time measurement)

### 6.2 Clinical Action on Elevated Lp(a)

| Lp(a) Result | Clinical Action |
|:-------------|:----------------|
| < 75 nmol/L | Normal; no additional action attributable to Lp(a) |
| 75–124 nmol/L | Mildly elevated; document as risk modifier; no specific therapy but lower threshold for statin initiation |
| ≥ 125 nmol/L | **Elevated risk.** Counts as a risk enhancer per 2026 guidelines [2]. Drives more aggressive LDL-C lowering to offset Lp(a)-mediated risk. Counsel patient on inherited nature. Screen first-degree relatives. |

### 6.3 Lp(a)-Targeted Therapies

Lp(a)-targeted pharmacotherapies (muvalaplin, lepodisiran, olpasiran) are not currently included in this clinic's therapeutic plan. Phase 3 cardiovascular outcomes trials are ongoing. These agents may be incorporated in future versions as evidence matures and regulatory approvals are obtained [7].

### 6.4 Interim Management of Elevated Lp(a)

In the absence of specific Lp(a)-lowering agents, the approach is to aggressively reduce all modifiable atherogenic risk:

- Maximize LDL-C lowering (statin + ezetimibe ± PCSK9i/inclisiran)
- PCSK9 inhibitors reduce Lp(a) by approximately 20–30%, though this is not an FDA-approved indication [8]
- Address all other modifiable ASCVD risk factors
- Consider low-dose aspirin in higher-risk patients (shared decision-making)

## 7.0 Coronary Artery Calcium (CAC) Scoring

CAC scoring is available in-house and provides a direct measure of coronary atherosclerotic burden. It is the most powerful single predictor of ASCVD events in asymptomatic individuals [9, 10].

### 7.1 When to Order CAC

| Clinical Scenario | Rationale |
|:------------------|:----------|
| Borderline risk (3–4.9%) with uncertainty about statin initiation | CAC can reclassify risk upward or downward |
| Intermediate risk (5–9.9%) and patient hesitant about statin therapy | CAC = 0 may support deferral; CAC > 0 supports initiation |
| Patient or provider uncertainty about therapy despite risk calculation | CAC provides tangible, visual risk communication |

### 7.2 When NOT to Order CAC

| Scenario | Rationale |
|:---------|:----------|
| Established ASCVD | Already very high risk; CAC will not change management |
| Already committed to high-intensity statin | Risk reclassification will not alter plan |
| Age < 40 or > 75 years | Limited validation data at extremes of age |
| Prior coronary stenting or CABG | Stents and surgical clips artifact the score |

### 7.3 CAC Score Interpretation

| CAC Score (Agatston Units) | Interpretation | Clinical Action |
|:---------------------------|:---------------|:----------------|
| **0** | No detectable coronary calcium | See [Section 7.4 — De-Risking](#74-de-risking-cac--0) |
| **1–99** | Mild coronary atherosclerosis | Statin therapy favored, especially if ≥ 75th percentile for age/sex |
| **100–299** | Moderate coronary atherosclerosis | High-intensity statin recommended; consider treatment escalation |
| **≥ 300 to 999** | Extensive coronary atherosclerosis | LDL-C lowering therapy recommended with consideration of statin as first line per 2026 ACC/AHA guidelines [2] |
| **≥ 1000** | Very extensive coronary atherosclerosis | Aggressive multi-drug lipid-lowering; treat as equivalent to high-risk category |

### 7.4 De-Risking: CAC = 0

A CAC score of 0 has strong negative predictive value for near-term ASCVD events [9]. However, in this clinic, **de-risking (deferring statin initiation) is permitted only when BOTH conditions are met:**

1. **CAC = 0** (Agatston score)
2. **ApoB is below the risk-appropriate target** (i.e., "negative" — not elevated)

If CAC = 0 but ApoB is elevated, the patient retains an atherogenic particle burden that warrants treatment despite the absence of detectable calcification. Therapy should be initiated or continued.

{: .warning }
> **De-risking with CAC = 0 does NOT apply to:** patients with established ASCVD, LDL-C ≥ 190 mg/dL, familial hypercholesterolemia, or diabetes with additional risk factors. These patients require treatment regardless of CAC score.

## 8.0 Advanced Lipid Fractionation — Labcorp NMR LipoProfile

The Labcorp NMR LipoProfile provides nuclear magnetic resonance spectroscopy-based quantification of lipoprotein particles [11].

### 8.1 Key Parameters Reported

| Parameter | Clinical Utility |
|:----------|:-----------------|
| LDL particle number (LDL-P) | Total concentration of LDL particles; correlates with ApoB; superior to LDL-C for risk prediction when discordant [12] |
| Small LDL-P | Proportion of small, dense LDL particles; marker of atherogenic dyslipidemia |
| LDL particle size | Small dense LDL pattern associated with higher risk |
| HDL-P (large and small) | Research interest; no established treatment targets |
| VLDL-P | Reflects triglyceride-rich lipoprotein burden |
| LP-IR (Lipoprotein Insulin Resistance Index) | Composite index of insulin resistance derived from lipoprotein subclass patterns |

### 8.2 When to Order NMR LipoProfile

| Clinical Scenario | Rationale |
|:------------------|:----------|
| Triglycerides 150–499 mg/dL with suspected atherogenic dyslipidemia | Characterize particle phenotype |
| Metabolic syndrome or type 2 diabetes | High prevalence of small dense LDL-predominant pattern |
| ApoB elevated but LDL-C appears concordant | NMR provides additional granularity (particle number and size) |
| Persistent ASCVD events despite LDL-C at target | Evaluate residual particle-mediated risk |

### 8.3 Interpretation Guidance

NMR results should be interpreted in the context of the full lipid profile, ApoB, and clinical risk assessment. In general:

- **Elevated LDL-P (> 1000 nmol/L in low-risk, > 700 nmol/L in high-risk):** Supports treatment intensification, analogous to elevated ApoB
- **Small dense LDL-predominant pattern:** Characteristic of insulin-resistant states; treat underlying metabolic dysfunction and intensify LDL-lowering therapy
- **LP-IR score:** Useful for identifying insulin resistance; does not directly alter lipid pharmacotherapy decisions

## 9.0 Carotid Duplex Ultrasonography

### 9.1 Standard Indications

Carotid duplex ultrasonography is ordered for the following standard clinical indications:

| Indication | Notes |
|:-----------|:------|
| Carotid bruit on auscultation | Screen for hemodynamically significant stenosis |
| History of TIA or ischemic stroke | Evaluate for carotid stenosis as source |
| Pre-surgical assessment | Per surgical team request |
| Known carotid stenosis surveillance | Monitoring for progression |

### 9.2 Findings That Alter Lipid Management

- **Carotid stenosis ≥ 50%** or **significant carotid plaque:** Reclassifies patient to high-risk category regardless of calculated PREVENT score. High-intensity statin and aggressive LDL-C lowering indicated.

## 10.0 Coronary CT Angiography (CCTA)

### 10.1 Eligibility Criteria

CCTA is available for patients meeting **all** of the following:

| Criterion | Requirement |
|:----------|:------------|
| Symptoms | Symptomatic (chest pain, dyspnea, or equivalent) |
| Pre-test probability | Low-to-intermediate probability of obstructive CAD |
| Rhythm | Not in atrial fibrillation |
| Body habitus | BMI ≤ 40 kg/m² |
| Prior interventions | No prior coronary stents |

### 10.2 CCTA Findings That Alter Management

| Finding | Clinical Action |
|:--------|:----------------|
| Non-obstructive plaque (any) | Reclassify to at least intermediate risk; initiate statin therapy if not already on one |
| Obstructive stenosis ≥ 50% | Refer for functional testing or invasive angiography; treat as established ASCVD for lipid management |
| High-risk plaque features (positive remodeling, low-attenuation, napkin-ring sign) | Aggressive lipid-lowering therapy |

## 11.0 Integrated Risk Assessment Algorithm

After completing the steps above, the provider assigns a **final integrated risk category**:

| Final Risk Category | Criteria | LDL-C Target | ApoB Target |
|:--------------------|:---------|:-------------|:------------|
| **Low** | PREVENT < 3%, no enhancers, CAC = 0 + ApoB below target | < 130 mg/dL | < 100 mg/dL |
| **Borderline** | PREVENT 3–4.9%, no enhancers | < 130 mg/dL | < 100 mg/dL |
| **Intermediate** | PREVENT 5–9.9% or borderline with risk enhancers | < 100 mg/dL | < 90 mg/dL |
| **High** | PREVENT ≥ 10%, DM with risk factors, LDL-C ≥ 190 mg/dL, CAC ≥ 300 | < 70 mg/dL | < 80 mg/dL |
| **Very High** | Established ASCVD, recurrent events, multivessel CAD | < 55 mg/dL | < 65 mg/dL |

{: .important }
> Per the "lower is better" philosophy of this clinic, these targets represent **minimum thresholds**. If a patient tolerates therapy and ApoB remains above target despite LDL-C at goal, treatment intensification is warranted.

## 12.0 Version History

| Version | Date | Description |
|:--------|:-----|:------------|
| 1.0.0 | 2026-03-30 | Initial release |

---

## References

1. Khan SS, Matsushita K, Sang Y, et al. Development and validation of the American Heart Association's PREVENT equations. *Circulation*. 2024;149(6):e430–e449.
2. 2026 ACC/AHA/Multisociety Guideline on the Management of Dyslipidemia. *J Am Coll Cardiol*. 2026.
3. Volgman AS, Palaniappan LS, Aggarwal NT, et al. Atherosclerotic cardiovascular disease in South Asians in the United States: epidemiology, risk factors, and treatments. *Circulation*. 2018;138(1):e1–e34.
4. Sniderman AD, Thanassoulis G, Glavinovic T, et al. Apolipoprotein B particles and cardiovascular disease: a narrative review. *JAMA Cardiol*. 2019;4(12):1287–1295.
5. Boren J, Chapman MJ, Krauss RM, et al. Low-density lipoproteins cause atherosclerotic cardiovascular disease: pathophysiological, genetic, and therapeutic insights. A consensus statement from the European Atherosclerosis Society Consensus Panel. *Eur Heart J*. 2020;41(24):2313–2330.
6. Kronenberg F, Mora S, Stroes ESG, et al. Lipoprotein(a) in atherosclerotic cardiovascular disease and aortic stenosis: a European Atherosclerosis Society consensus statement. *Eur Heart J*. 2022;43(39):3925–3946.
7. O'Donoghue ML, Rosenson RS, Gencer B, et al. Small interfering RNA to lower lipoprotein(a) in cardiovascular disease. *N Engl J Med*. 2022;387(20):1855–1864.
8. Raal FJ, Giugliano RP, Sabatine MS, et al. Reduction in lipoprotein(a) with PCSK9 monoclonal antibody evolocumab (OSLER-2): a prespecified secondary analysis of a randomised, double-blind, placebo-controlled trial. *Lancet Diabetes Endocrinol*. 2016;4(7):569–578.
9. Blaha MJ, Cainzos-Achirica M, Greenland P, et al. Role of coronary artery calcium score of zero and other negative risk markers for cardiovascular disease. *Circulation*. 2019;140(16):e565–e579.
10. Budoff MJ, Young R, Burke G, et al. Ten-year association of coronary artery calcium with atherosclerotic cardiovascular disease (ASCVD) events: the Multi-Ethnic Study of Atherosclerosis (MESA). *Eur Heart J*. 2018;39(25):2401–2408.
11. Jeyarajah EJ, Cromwell WC, Otvos JD. Lipoprotein particle analysis by nuclear magnetic resonance spectroscopy. *Clin Lab Med*. 2006;26(4):847–870.
12. Otvos JD, Mora S, Shalaurova I, et al. Clinical implications of discordance between low-density lipoprotein cholesterol and particle number. *J Clin Lipidol*. 2011;5(2):105–113.
