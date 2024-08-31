# A/B Testing in Digital Marketing

## Overview
This project investigates the effectiveness of three different Facebook ad campaigns conducted by an anonymous organization in 2017. By leveraging A/B testing, the analysis aims to determine if the observed differences in conversion rates across these campaigns are statistically significant and attributable to the campaigns themselves rather than random variation. The goal is to determine whether differences in campaign performance are statistically significant, suggesting true causality.

## Objective and Hypothesis
**Objective:** Assess and compare the performance of three different ad campaigns on Facebook.

**Hypothesis:** There is a statistically significant difference in conversion rates between the campaigns.

## Data Source
The dataset is sourced from Kaggle’s “[Sales Conversion Optimization](https://www.kaggle.com/datasets/loveall/clicks-conversion-tracking/data)”.

## Methodology

### Data Preprocessing
- Imported necessary libraries such as `pandas`, `numpy`, `seaborn`, `matplotlib`, and statistical libraries from `scipy`.
- Conducted an initial data overview to understand the structure, missing values, and summary statistics.
- Identified and addressed data inconsistencies, such as rows where `Clicks` were zero but `Total_Conversion` was positive.

### Feature Engineering
- Created new features to enhance the predictive power of the dataset:
  - **Click-Through Rate (CTR):** Calculated as `Clicks / Impressions` to measure the effectiveness of the ad in generating clicks.
  - **Cost per Click (CPC):** Computed as `Spent / Clicks` to evaluate the cost-efficiency of the ads.
  - **Conversion Rate (CR):** Derived as `Total_Conversion / Clicks` to assess the success rate of clicks leading to conversions.
- Binned age groups into categories to facilitate analysis of ad performance across different age segments.
- Encoded categorical variables like gender to use in statistical models.

### Exploratory Data Analysis (EDA)
- Analyzed the distribution of key variables such as age, gender, impressions, clicks, and conversions.
- Visualized the relationship between ad spend and conversion rates.
- Explored the newly created features to uncover additional insights.

### A/B Testing
- Performed statistical tests (Shapiro-Wilk, Levene’s, Mann-Whitney U) to assess normality, variance, and significance.
- Conducted a comparison between campaigns to identify statistically significant differences in performance.

### Results
- Provided a detailed analysis of the effectiveness of each campaign, including statistical significance.
- Visualized the differences in conversion rates across campaigns to support the findings.

## Conclusion
The project successfully identified significant differences between the campaigns, offering actionable insights into which campaign performed best and why. The results support the hypothesis that not all campaigns perform equally, and certain factors like audience targeting and ad spend play crucial roles.

## Challenges and Limitations
- **Data Quality:** Some entries contained logical inconsistencies, such as conversions without clicks, which required cleaning.
- **Sample Size:** The dataset’s size may limit the generalizability of the results.
- **Model Assumptions:** Assumptions in statistical tests may not hold perfectly, affecting the reliability of p-values.

## Appendix
- **Tools Used:** Python (pandas, numpy, scipy, seaborn, matplotlib)
- **Key Metrics:** Conversion Rate, Click-Through Rate, Cost per Click
- **Statistical Tests:** Shapiro-Wilk Test, Mann-Whitney U Test


Explore the notebook to see the full analysis.
