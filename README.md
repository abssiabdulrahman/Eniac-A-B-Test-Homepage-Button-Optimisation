# Eniac A/B Test — Homepage Button Optimisation

## Can Changing a Button's Colour and Copy Improve User Engagement?

---

## Project Introduction

This project was completed as part of my data analytics training and focuses on evaluating the results of an A/B test through statistical hypothesis testing.

The case simulates Eniac, a premium Apple-focused e-commerce company, testing four variations of their homepage call-to-action button. Since the button was only attracting around 2% of visitors, the goal was to identify whether a different design could meaningfully improve click-through rates.

Through this project, I applied Python, statistical testing, and business reasoning to support a data-driven design decision.

---

## Project Objective

The main objective of this project was to analyse the results of a four-variant A/B test and determine which button version performs best.

Key questions included:

- Which button version had the highest click-through rate?
- Are the differences statistically significant or due to chance?
- Does colour or copy have a stronger impact?
- Which version produces the best downstream user behaviour?

---

## Experiment Design

Four versions of the homepage button were tested simultaneously:

| Version | Colour | Copy | Role |
|---------|--------|------|------|
| A | White | SHOP NOW | Baseline (control) |
| B | Red | SHOP NOW | Colour change only |
| C | White | SEE DEALS | Copy change only |
| D | Red | SEE DEALS | Both changed |

- **Test period:** November 2 – 16, 2021 (14 days / 2 full business cycles)
- **Total traffic:** ~100,000 visits split evenly across all versions
- **Primary metric:** Click-Through Rate (CTR)
- **Secondary metrics:** Drop-off rate, Homepage-return rate
- **Statistical threshold:** α = 0.05 (95% confidence)
- **Minimum Detectable Effect:** 20%
- **Statistical Power:** 80%

---

## Project Workflow

This project followed three main steps:

### 1️ Data Exploration (Python / pandas)

I explored four CSV snapshot files, one per button version, and extracted the key metrics needed for analysis.

Main tasks included:

- Loading and inspecting each dataset
- Extracting total page visits from snapshot metadata
- Identifying the button row and its click count
- Calculating CTR for each version
- Building a summary comparison table

Notebook file:
`eniac_ab_test_analysis.ipynb`

---

### 2️ Statistical Testing (scipy)

I tested whether the observed differences in CTR were statistically significant using a chi-square test of independence.

Steps included:

- Building a contingency table (clicks vs no-clicks per version)
- Running the overall chi-square test
- Applying Bonferroni correction for pairwise post-hoc tests
- Identifying which specific pairs of versions differ significantly

---

### 3️ Secondary Metric Analysis

Since two versions could not be separated on CTR alone, I used additional metrics to make the final decision.

Metrics analysed:

- Drop-off rate — how many users abandon the conversion process
- Homepage-return rate — how many users return to the homepage after clicking

---

## Key Outcome

The analysis confirmed statistically significant differences between most button versions.

Key findings:

- **Version C (White SEE DEALS) had the highest CTR at 2.12%**
- **Version D (Red SEE DEALS) had the lowest CTR at 0.76%**
- White buttons received roughly **2× more clicks** than red buttons across both copy variants
- A vs C was the only non-significant pair — secondary metrics showed Version C performing slightly better
- Version C had a **lower drop-off rate (67% vs 78%)** and **lower homepage-return rate (39% vs 45%)**

---

## My Recommendation

Despite Version C showing slightly better numbers across all metrics, **my recommendation is to keep Version A — the original White "SHOP NOW" button.**

The CTR difference between A and C is only 0.10 percentage points (2.02% vs 2.12%).

Making a change to a live production website carries real costs — development time, QA, deployment risk, and potential disruption to users who are already familiar with the current button. Given that the gain does not clearly justify those costs, the most practical and risk-aware decision is to stay with the existing version.

---

## What I Learned

This project helped me strengthen both technical and business skills.

Key learnings:

- Performing chi-square tests of independence with scipy
- Applying the Bonferroni correction for multiple comparisons
- Understanding when primary metrics alone are not enough to make a decision
- Recognising that statistical significance is not the same as practical significance
- Translating statistical results into a clear, cautious business recommendation

As a student, this project improved my confidence in moving from raw experimental data to a justified, evidence-based conclusion.

---

## Tools Used

- Python (pandas, numpy, scipy, matplotlib, seaborn)
- Jupyter Notebook
- VS Code

---

## Project Details

Dataset: Eniac A/B test snapshot data (November 2021)
Project completed: May 2026
Project type: Hypothesis testing / Experimental analysis
