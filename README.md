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
- **Univariate Analysis:** Analyzed the distribution of key variables such as age, gender, impressions, clicks, and conversions.
  <img src="https://github.com/Anokhi-hirsch/A-B-testing-on-Ad-campaigns/blob/main/visualization/univariate%20distribution.png" alt="Univariate Distribution" width="800"/>
- **Multivariate Analysis:** Conducted a correlation analysis using a heatmap to explore the relationships between different variables to uncover additional insights.
  <img src="https://github.com/Anokhi-hirsch/A-B-testing-on-Ad-campaigns/blob/main/visualization/multivariate%20analysis%20heatmap.png" alt="Multivariate Analysis Heatmap" width="800"/>

### A/B Testing  
Purpose: The main goal of A/B testing here is to determine whether the observed differences between the ad campaigns (in terms of metrics like Conversion Rate, Click-Through Rate, and Cost Per Click) are statistically significant or simply due to chance.   
The detailed steps can be given by:

1. Residuals normality check of groups using Shapiro-Wilk test.  
    - If normal, check for variance homogenity of groups using Levene's test.  
        - If homogenous, perform pair-wise T-test.  
        - If not homogenous, perform pair-wise Welch's test.  
    - If not normal, perform pair-wise Mann Whitney U test.  
2. Apply Bonferroni correction to conclude the test.    

- Performed statistical tests (Shapiro-Wilk, Mann-Whitney U) to assess normality, and significance.
- Applied Bonferroni correction by lowering the significance level to 0.0167.
- Used Mann-Whitney U test for comparison between campaigns to identify statistically significant differences in performance.

### Results
- Given detailed analysis of the effectiveness of each campaign, the difference in CR, CTR and CPC between 936-1178 and 1178-916 is statistically significant and should be considered, while the difference of the KPIs between 916-936 is only due to chance.
- Campaigns 936 and 916 demonstrated significantly higher conversion rates compared to Campaign 1178. This indicates that these two campaigns are more effective in turning impressions into conversions.
- Both 936 and 916 also showed superior click-through rates, suggesting they were more engaging and successful in capturing user interest compared to Campaign 1178.
- Despite a higher budget allocation, Campaign 1178 underperformed in terms of conversion rate and engagement (CTR) relative to its cost. This suggests that the additional spending did not translate into proportional performance improvements.
- The most engaged demographic was identified as the 30-34 age group. This suggests that this segment is the most responsive to the company’s ad campaigns.  
In conclusion, the project successfully identified significant differences between three campaigns, offering actionable insights into which campaign performed best and why. The results support the hypothesis that not all campaigns perform equally, and certain factors like audience targeting and ad spend play crucial roles.

## Challenges and Limitations
- **Data Quality:** Some entries contained logical inconsistencies, such as conversions without clicks, which required cleaning.
- **Sample Size:** The dataset’s size may limit the generalizability of the results.

## Appendix
- **Tools Used:** Python (pandas, numpy, scipy, seaborn, matplotlib)
- **Key Metrics:** Conversion Rate, Click-Through Rate, Cost per Click
- **Statistical Tests:** Shapiro-Wilk Test, Mann-Whitney U Test

Explore [the notebook] to see the full analysis.
