# LendingClub Loan Data — Week 2 EDA Report

This repository contains the Week 2 deliverable of the Data Science Internship: a comprehensive Exploratory Data Analysis (EDA) of the LendingClub consumer-loan dataset.

## About the project

The dataset analyzed in this report is the output of the Week 1 data-cleaning pipeline, built from the publicly available LendingClub LoanStats3a export. The cleaned dataset contains 42,535 loans and 55 features spanning loan characteristics, borrower demographics, credit-bureau attributes and engineered ratios. The analysis combines descriptive statistics, univariate and multivariate visualizations, and eight formal hypothesis tests to uncover the structural patterns, trends and relationships that govern credit-risk outcomes in this dataset.

The central business question for any lending dataset is: which borrowers default, and why? This EDA answers that question with three converging lines of evidence. Default risk is strongly stratified by LendingClub grade, rising from roughly 6% for grade-A loans to nearly 25% for grade-F loans. Loan purpose carries independent signal: small-business loans default at 24% while wedding loans default below 7%. All eight hypothesis tests conducted (two-sample t-tests, one-way ANOVA, chi-square tests of independence and Pearson correlation tests) are statistically significant at the 0.05 level, confirming the observed relationships are real rather than sampling artifacts. The findings lay the foundation for the Week 3 predictive-modeling task.

## Contents

| File | Description |
|---|---|
| `EDA_Report.pdf` | Full 35-page EDA report with cover, TOC, 20 visualizations, hypothesis-test results and inferences |
| `week2_eda.ipynb` | Google-Colab-ready Jupyter notebook reproducing the entire analysis |
| `cleaned_dataset.csv` | Week 1 cleaned dataset (input to this EDA) |

## Key findings

- **Default rate**: 13.33% (5,670 of 42,535 loans)
- **Grade predicts default**: monotonic increase from grade A (6%) to grade F (25%)
- **Purpose carries signal**: small-business (24%) vs wedding (~7%)
- **Multicollinearity**: loan amount ↔ installment (r = 0.94)
- **Hypothesis tests**: 8/8 statistically significant at α = 0.05

## Methodology

1. **Descriptive statistics** — central tendency, dispersion, skewness, kurtosis for 15 numeric features
2. **Univariate analysis** — histograms, boxplots, QQ plots for distribution shape and normality
3. **Categorical analysis** — frequency distributions for grade, home ownership, verification status, purpose
4. **Bivariate analysis** — correlation matrix, scatter plots, group comparisons
5. **Multivariate analysis** — pair plots, cross-tabulation heatmaps, origination trends
6. **Hypothesis testing** — Welch t-test, one-way ANOVA, chi-square tests of independence, Pearson correlation

## How to reproduce

1. Upload `week2_eda.ipynb` to [Google Colab](https://colab.research.google.com/)
2. Upload `cleaned_dataset.csv` to the Colab working directory
3. Runtime → Run all

**Requirements**: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`

```bash
pip install pandas numpy matplotlib seaborn scipy
```

## Tools and libraries

- Python 3.10
- pandas, NumPy — data manipulation
- Matplotlib, Seaborn — visualization
- SciPy — hypothesis testing
- ReportLab — PDF report generation

## Dataset source

LendingClub LoanStats3a — publicly available consumer-loan data covering originations from 2007 to 2011.
