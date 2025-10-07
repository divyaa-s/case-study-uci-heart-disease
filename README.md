📌 Project Overview

This project applies inferential statistics to the UCI Heart Disease dataset to answer three clinical questions:

1. Is mean resting blood pressure different from the clinical reference of 120 mmHg? (one-sample t-test)
2. Do cholesterol levels differ between males and females? (two-sample t-test, Welch)
3. Does maximum heart rate (thalch) differ across chest pain categories? (one-way ANOVA / F-test)

The analysis is implemented in Python (pandas, SciPy, statsmodels) and produces a compact results summary.

📊 Dataset Description

Name: UCI Heart Disease (Cleveland subset; cleaned)
Rows: ~834 patients (after cleaning)
Key variables (CleanedData sheet):
- age (years)
- sex (Male/Female)
- chest_pain (typical angina, atypical angina, non-anginal pain, asymptomatic)
- resting_bp (resting blood pressure, mmHg)
- cholesterol (serum cholesterol, mg/dL)
- thalch (maximum heart rate achieved)
- exercise_angina (True/False)
- st_depression, st_slope, rest_ecg, thal, vessels (other clinical attributes)
- target (disease presence/severity label; may be 0–4 in some versions)

Note: For the one-sample t-test, resting_bp values ≤ 0 are filtered out.

🎯 Hypotheses & Tests

**One-sample t-test (t statistic)**

->Variable: resting_bp

H₀: μ = 120 mmHg

H₁: μ ≠ 120 mmHg

Why: Compare a sample mean to a known reference when population σ is unknown.




**Two-sample t-test (Welch) (t statistic)**

-> Variable: cholesterol grouped by sex (Male vs Female)

H₀: μₘ = μ𝒻

H₁: μₘ ≠ μ𝒻

Why: Compare two independent groups on a continuous outcome; Welch is robust to unequal variances.



**One-way ANOVA (F statistic)**

-> Variable: thalch across chest_pain categories (k=4)

H₀: μ₁ = μ₂ = μ₃ = μ₄

H₁: At least one group mean differs

Why: Compare >2 groups on a continuous outcome using the F-test.

Significance level: α = 0.05
Decision rule: p < 0.05 → Reject H₀; p ≥ 0.05 → Fail to reject H₀.
