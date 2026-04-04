---
layout: default
title: "06 — Advanced Tools"
parent: Clinical
nav_order: 6
version: "1.0.0"
last_updated: "2026-03-30"
---

# 06 — Advanced Tools
{: .no_toc }

<details open markdown="block">
  <summary>Table of Contents</summary>
  {: .text-delta }
- TOC
{:toc}
</details>

---

## 1.0 Overview

The Sandusky Dyslipidemia Model employs advanced diagnostic tools beyond standard lipid panels to identify patients at increased cardiovascular risk and to guide treatment intensification under a "lower is better" philosophy. This document consolidates the clinical protocols for each advanced tool.

See the [Advanced Tools Decision Flowchart]({% link workflows/advanced-tools-decision-flow.md %}) for when to order each test.

## 2.0 Summary of Advanced Tools

| Tool | What It Measures | Primary Clinical Role |
|:-----|:-----------------|:---------------------|
| **Apolipoprotein B (ApoB)** | Atherogenic particle number | Treatment target; identifies residual risk when LDL-C at goal |
| **Labcorp NMR LipoProfile** | LDL-P, small dense LDL-P, particle size, LP-IR | Characterizes atherogenic dyslipidemia; complements ApoB |
| **Lipoprotein(a) \[Lp(a)\]** | Genetically determined atherogenic lipoprotein | One-time risk modifier; identifies inherited ASCVD risk |
| **Coronary Artery Calcium (CAC)** | Coronary atherosclerotic burden | Risk reclassification; de-risking when combined with ApoB |
| **Carotid Duplex** | Carotid stenosis and plaque | Standard indications; subclinical atherosclerosis |
| **CCTA** | Coronary anatomy and plaque characterization | Symptomatic patients with restricted eligibility |

## 3.0 Apolipoprotein B (ApoB)

### 3.1 Pathophysiology

Each atherogenic lipoprotein particle (VLDL, IDL, LDL, Lp(a)) carries exactly one ApoB molecule. Therefore, ApoB directly quantifies the total number of atherogenic particles in circulation, regardless of the cholesterol content per particle [1]. When LDL particles are small and cholesterol-depleted (common in metabolic syndrome, diabetes, and hypertriglyceridemia), LDL-C underestimates true atherogenic burden while ApoB remains accurate [2].

### 3.2 Ordering Protocol

| Scenario | Order ApoB? |
|:---------|:------------|
| All new patients at initial assessment | Recommended |
| LDL-C and non-HDL-C discordant (>10% difference in percentile ranking) | Yes |
| Metabolic syndrome or type 2 diabetes | Yes |
| Triglycerides 150–499 mg/dL | Yes |
| Patient at or near guideline LDL-C target | Yes — to assess for "lower is better" intensification |
| Monitoring response to therapy | Yes — repeat with each lipid panel |
| Established ASCVD | Yes — for ApoB-guided intensification |

### 3.3 Interpretation and Targets

| Risk Category | ApoB Target | Clinical Action if Above Target |
|:--------------|:------------|:-------------------------------|
| Very high (ASCVD) | < 65 mg/dL | Intensify therapy per [05 — Treatment Pathways]({% link clinical/05-treatment-pathways.md %}) |
| High | < 80 mg/dL | Intensify therapy |
| Intermediate | < 90 mg/dL | Consider intensification; shared decision-making |
| Low/Borderline | < 100 mg/dL | Risk enhancer if elevated; favors statin initiation |

### 3.4 ApoB and De-Risking

ApoB below the risk-appropriate target in combination with CAC = 0 is the **only** combination that permits de-risking (deferring statin therapy). See [04 — Risk Stratification, Section 7.4]({% link clinical/04-risk-stratification.md %}#74-de-risking-cac--0).

## 4.0 Labcorp NMR LipoProfile

### 4.1 Platform and Specimen Requirements

| Parameter | Details |
|:----------|:--------|
| Platform | Labcorp NMR LipoProfile (nuclear magnetic resonance spectroscopy) |
| Specimen | Serum or EDTA plasma |
| Fasting | Preferred (12 hours) for optimal triglyceride-related measurements; non-fasting acceptable for LDL-P |
| Order code | Labcorp test code 123810 (NMR LipoProfile) |

### 4.2 Key Reported Parameters

| Parameter | Reference Range | Clinical Significance |
|:----------|:----------------|:---------------------|
| **LDL-P** (LDL particle number) | < 1000 nmol/L (low risk); < 700 nmol/L (high risk target) | Total LDL particle concentration; correlates with ApoB; superior to LDL-C when discordant [3] |
| **Small LDL-P** | Varies | Proportion of small, dense LDL; marker of atherogenic dyslipidemia |
| **LDL size** (nm) | Pattern A: > 20.5 nm; Pattern B: ≤ 20.5 nm | Small dense LDL (Pattern B) associated with insulin resistance and higher ASCVD risk |
| **HDL-P (large)** | Varies | Research interest; no treatment target |
| **LP-IR** (Lipoprotein Insulin Resistance Index) | ≤ 45 (lower = less insulin resistant) | Composite score; identifies insulin resistance independent of glucose metrics |
| **VLDL-P** | Varies | Triglyceride-rich lipoprotein burden |

### 4.3 When to Order

| Clinical Scenario | Rationale |
|:------------------|:----------|
| Triglycerides 150–499 mg/dL | Characterize atherogenic dyslipidemia phenotype |
| Metabolic syndrome or type 2 diabetes | High prevalence of small dense LDL pattern |
| ApoB elevated but LDL-C concordant | NMR provides additional granularity |
| Persistent events despite LDL-C at target | Evaluate residual particle-mediated risk |
| Suspected insulin resistance without overt diabetes | LP-IR score assessment |

### 4.4 Clinical Decision Framework

1. **Elevated LDL-P with small dense predominance:** Confirms atherogenic dyslipidemia → intensify LDL-lowering therapy; address metabolic drivers (insulin resistance, visceral adiposity)
2. **Elevated LDL-P with normal LDL-C:** LDL-C underestimates risk → treat based on LDL-P/ApoB
3. **Normal LDL-P with elevated LDL-C:** LDL-C overestimates risk → reassuring; may use ApoB to confirm
4. **Elevated LP-IR:** Insulin resistance marker → does not directly change lipid pharmacotherapy but supports aggressive metabolic risk management

## 5.0 Lipoprotein(a) \[Lp(a)\]

### 5.1 Pathophysiology

Lp(a) is a modified LDL particle with an additional apolipoprotein(a) covalently bound to the ApoB-100 molecule. It is >90% genetically determined by the *LPA* gene locus. Elevated Lp(a) contributes to ASCVD risk through three mechanisms: atherogenesis (LDL-like), thrombosis (structural homology with plasminogen), and inflammation (carries oxidized phospholipids) [4, 5].

### 5.2 Measurement Protocol

| Parameter | Specification |
|:----------|:-------------|
| Unit | **nmol/L** (preferred; isoform-insensitive) |
| Frequency | **One-time measurement** (genetically determined; does not change meaningfully over time) |
| Timing | Not affected by fasting status, statin therapy, or acute illness |
| Repeat testing | Only if initial result was borderline (75–124 nmol/L) and a different assay methodology is being used |

### 5.3 Interpretation

| Lp(a) Level | Risk Category | Clinical Action |
|:-------------|:-------------|:----------------|
| < 75 nmol/L | Normal | No Lp(a)-specific action |
| 75–124 nmol/L | Mildly elevated | Document as risk modifier; lower threshold for statin initiation in borderline/intermediate risk |
| **≥ 125 nmol/L** | **Elevated** | Risk enhancer per 2026 guidelines [6]; aggressive LDL-C lowering; screen first-degree relatives; counsel on inherited nature |
| ≥ 250 nmol/L | Markedly elevated | Very high Lp(a)-mediated risk; maximal LDL-C lowering; consider niacin if tolerated (see [05 — Treatment Pathways, Section 10.0]({% link clinical/05-treatment-pathways.md %}#100-niacin-extended-release)) |

### 5.4 Patient Counseling Points

- Lp(a) is inherited and does not respond to diet, exercise, or statin therapy
- First-degree family members should be tested
- PCSK9 inhibitors reduce Lp(a) by ~20–30% (not an approved indication) [7]
- Specific Lp(a)-lowering therapies are in clinical development and may be available in the future

## 6.0 Coronary Artery Calcium (CAC) Scoring

### 6.1 In-House Protocol

| Parameter | Specification |
|:----------|:-------------|
| Modality | Non-contrast ECG-gated CT |
| Scoring method | Agatston score (area × density weighting) [8] |
| Availability | In-house at The Sandusky Dyslipidemia Model clinic |
| Radiation dose | < 1 mSv (low dose) |
| Contrast | None required |
| Preparation | No fasting required; no medication preparation |

### 6.2 Indications

See [04 — Risk Stratification, Section 7.1]({% link clinical/04-risk-stratification.md %}#71-when-to-order-cac) for detailed ordering criteria.

### 6.3 Score Interpretation and Action

| CAC Score | Category | Management Implications |
|:----------|:---------|:-----------------------|
| **0** | No coronary calcium | De-risking possible **only if ApoB also below target** [9] |
| **1–99** | Mild atherosclerosis | Statin therapy favored; standard risk-appropriate treatment |
| **100–299** | Moderate atherosclerosis | High-intensity statin; additional agents as needed to meet targets |
| **300–999** | Extensive atherosclerosis | Per 2026 guidelines: LDL-C lowering therapy recommended with statin as first-line [6] |
| **≥ 1000** | Very extensive atherosclerosis | Treat as equivalent to high-risk category; aggressive multi-agent therapy |

### 6.4 Age- and Sex-Based Percentiles

CAC scores should be interpreted relative to age- and sex-matched reference populations (MESA calculator) [10]. A score at or above the **75th percentile for age and sex** indicates greater-than-expected atherosclerotic burden and should shift the patient toward more aggressive treatment regardless of the absolute score.

### 6.5 Repeat CAC Scoring

Routine repeat CAC scoring is not recommended. CAC progression on statin therapy does not indicate treatment failure (statins stabilize plaque and increase calcium density). Repeat CAC may be considered after 5+ years in borderline patients where the initial score was 0 and risk reassessment is clinically warranted [11].

## 7.0 Carotid Duplex Ultrasonography

### 7.1 Indications

This clinic orders carotid duplex ultrasonography for standard clinical indications only:

| Indication | Details |
|:-----------|:--------|
| Cervical bruit on auscultation | Screen for hemodynamically significant carotid stenosis |
| Prior ischemic stroke or TIA | Evaluate carotid stenosis as potential source |
| Known carotid stenosis | Surveillance for progression |
| Pre-operative assessment | Per surgical team request |

### 7.2 Impact on Lipid Management

| Finding | Lipid Management Impact |
|:--------|:-----------------------|
| Normal / minimal plaque | No change to risk category based on carotid alone |
| Significant plaque (> 50% stenosis or heterogeneous plaque) | Reclassify to high-risk; high-intensity statin; aggressive LDL-C targets |
| > 70% stenosis or symptomatic | Manage as established ASCVD equivalent; surgical referral per guidelines |

## 8.0 Coronary CT Angiography (CCTA)

### 8.1 Eligibility

CCTA is **not** a routine screening tool. It is reserved for **symptomatic** patients meeting strict eligibility criteria:

| Criterion | Requirement |
|:----------|:------------|
| Symptoms | Present (chest pain, dyspnea, or anginal equivalent) |
| Pre-test probability | Low-to-intermediate for obstructive CAD |
| Cardiac rhythm | Sinus rhythm (no atrial fibrillation) |
| Body habitus | BMI ≤ 40 kg/m² |
| Prior coronary interventions | No prior stents (metal artifact) |

### 8.2 Findings and Lipid Management Impact

| Finding | Action |
|:--------|:-------|
| No coronary atherosclerosis | Reassuring; continue risk-appropriate management |
| Non-obstructive plaque (any location) | Initiate statin if not already on one; reclassify to at least intermediate risk |
| Non-obstructive plaque with high-risk features | Aggressive LDL-C lowering; close follow-up |
| Obstructive stenosis (≥ 50%) | Refer for functional testing or invasive angiography; treat lipids as established ASCVD |

### 8.3 High-Risk Plaque Features on CCTA

| Feature | Significance |
|:--------|:-------------|
| Positive (outward) remodeling | Vulnerable plaque marker [12] |
| Low-attenuation plaque (< 30 HU) | Lipid-rich necrotic core |
| Napkin-ring sign | Thin fibrous cap overlying necrotic core |
| Spotty calcification | Active plaque inflammation |

## 9.0 Integrated Decision Framework

The following table summarizes when each advanced tool adds value at different stages of the patient journey:

| Clinical Stage | ApoB | NMR | Lp(a) | CAC | Carotid | CCTA |
|:---------------|:------|:----|:------|:----|:--------|:-----|
| Initial assessment (all new patients) | Yes | Select | Yes (one-time) | Select | If indicated | No |
| Borderline/intermediate risk reclassification | Yes | If discordance | If not yet done | Yes | If indicated | No |
| On-treatment monitoring | Yes | Select | No (one-time) | No | No | No |
| Residual risk evaluation | Yes | Yes | Review prior | No | If indicated | No |
| Symptomatic evaluation | — | — | — | No | If indicated | If eligible |

**Legend:** "Yes" = routinely recommended. "Select" = ordered in specific clinical scenarios (see individual sections). "If indicated" = standard clinical indications only. "No" = not appropriate at this stage.

## 10.0 Version History

| Version | Date | Description |
|:--------|:-----|:------------|
| 1.0.0 | 2026-03-30 | Initial release |

---

## References

1. Sniderman AD, Thanassoulis G, Glavinovic T, et al. Apolipoprotein B particles and cardiovascular disease: a narrative review. *JAMA Cardiol*. 2019;4(12):1287–1295.
2. Mora S, Buring JE, Ridker PM. Discordance of low-density lipoprotein (LDL) cholesterol with alternative LDL-related measures and future coronary events. *Circulation*. 2014;129(5):553–561.
3. Otvos JD, Mora S, Shalaurova I, et al. Clinical implications of discordance between low-density lipoprotein cholesterol and particle number. *J Clin Lipidol*. 2011;5(2):105–113.
4. Kronenberg F, Mora S, Stroes ESG, et al. Lipoprotein(a) in atherosclerotic cardiovascular disease and aortic stenosis: a European Atherosclerosis Society consensus statement. *Eur Heart J*. 2022;43(39):3925–3946.
5. Tsimikas S, Fazio S, Ferdinand KC, et al. NHLBI Working Group recommendations to reduce lipoprotein(a)-mediated risk of cardiovascular disease and aortic stenosis. *J Am Coll Cardiol*. 2018;71(2):177–192.
6. 2026 ACC/AHA/Multisociety Guideline on the Management of Dyslipidemia. *J Am Coll Cardiol*. 2026.
7. Raal FJ, Giugliano RP, Sabatine MS, et al. Reduction in lipoprotein(a) with PCSK9 monoclonal antibody evolocumab (OSLER-2). *Lancet Diabetes Endocrinol*. 2016;4(7):569–578.
8. Agatston AS, Janowitz WR, Hildner FJ, et al. Quantification of coronary artery calcium using ultrafast computed tomography. *J Am Coll Cardiol*. 1990;15(4):827–832.
9. Blaha MJ, Cainzos-Achirica M, Greenland P, et al. Role of coronary artery calcium score of zero and other negative risk markers for cardiovascular disease. *Circulation*. 2019;140(16):e565–e579.
10. McClelland RL, Chung H, Detrano R, et al. Distribution of coronary artery calcium by race, gender, and age: results from the Multi-Ethnic Study of Atherosclerosis (MESA). *Circulation*. 2006;113(1):30–37.
11. Lehmann N, Erbel R, Mahabadi AA, et al. Value of progression of coronary artery calcification for risk prediction of coronary and cardiovascular events (Heinz Nixdorf Recall study). *Circulation*. 2018;137(7):665–672.
12. Motoyama S, Ito H, Sarai M, et al. Plaque characterization by coronary computed tomography angiography and the likelihood of acute coronary events in mid-term follow-up. *J Am Coll Cardiol*. 2015;66(4):337–346.
