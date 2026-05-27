Malaria Risk Factor Analysis

Project Overview

This project analyzes malaria risk factors using a simulated dataset designed to reflect real-world public health data challenges such as missing values, inconsistencies, outliers, and duplicates.

The analysis demonstrates a complete data analytics workflow in R, including:

  Data generation
Data cleaning and preprocessing
Exploratory Data Analysis (EDA)
Statistical testing
Logistic regression modeling
Model evaluation

  Objective

To identify and quantify key risk factors associated with malaria infection using statistical and machine learning techniques.

  Dataset Description

The dataset was synthetically generated (n = 1000) to mimic real-world malaria survey data.

  Key Features:
Demographics: age, sex, residence, wealth
Symptoms: fever, headache, vomiting, fatigue
Environmental factors: stagnant water, sprayed house, bed net use
Health access: distance to health facility
Risk indicators: pregnancy, under-5 status, recent travel, previous malaria
Target variable: malaria (Positive/Negative)
Realistic Data Issues Introduced:
Missing values (age, temperature, distance)
Outliers (extreme age & temperature values)
Inconsistent categorical labels (e.g., "male ", "FEMALE", "MID")
Duplicate records

 Tools & Libraries
R
tidyverse (dplyr, ggplot2, tidyr)
janitor (data cleaning)
stringr (text cleaning)
gtsummary, flextable (reporting)
psych, e1071 (skewness)
car (VIF - multicollinearity)
caret (model evaluation)
plotly, patchwork (visualization)
epiR, rcompanion (Cram??r???s V)

  Data Cleaning Process

Key preprocessing steps included:

1. Standardizing Categorical Variables
Trimmed whitespace and normalized case
Re-coded inconsistent labels (e.g., "F", "female" ??? "Female")
2. Handling Missing Values
Age ??? replaced using mean
Temperature ??? replaced using mean
Distance ??? replaced using median
Categorical variables ??? replaced using mode
Sex & pregnancy ??? assigned "Unknown" where necessary
3. Outlier Treatment
Age restricted to 0???60
Temperature restricted to 30???42??C
Outliers replaced with NA then imputed
4. Removing Duplicates
Exact duplicate rows removed
5. Data Type Conversion
Binary variables converted to factors ("Yes"/"No")
Target variable converted to:
Negative (0)
Positive (1)

  Exploratory Data Analysis (EDA)
Univariate Analysis
Histograms for:
Age
Temperature
Distance to health facility
Density plots to assess distribution
Skewness calculation
Bivariate Analysis
Boxplots comparing:
Age vs Malaria
Temperature vs Malaria
Distance vs Malaria
Categorical Analysis
Cross-tabulations:
Symptoms vs Malaria
Environmental factors vs Malaria
Proportional comparisons

  Statistical Analysis
1. Chi-Square Tests

Used to test association between categorical variables and malaria.

Computed p-values
Measured effect size using Cram??r???s V
Strength Interpretation:
< 0.1 ??? Very Weak
< 0.3 ??? Weak
< 0.5 ??? Moderate
??? 0.5 ??? Strong
2. Wilcoxon Rank-Sum Test

Used for numeric variables:

Age
Temperature
Distance to health facility

To compare distributions across malaria status.

3. Multicollinearity Check

Variance Inflation Factor (VIF) used to assess correlation between predictors:

Symptoms
Environmental factors
Demographics

Logistic Regression Model
Model Specification:
malaria ~ age + temperature + headache + fatigue + 
          stagnant_water + bednet + sprayed_house
Outputs:
Model coefficients
Odds ratios (exp(coef))
Confidence intervals
VIF scores

  Model Evaluation
Predicted probabilities generated
Classification threshold: 0.5
Confusion matrix used to compare:
Predicted vs Actual outcomes

  Key Insights
Fever, headache, and fatigue are strongly associated with malaria
Stagnant water increases malaria risk
Bed net usage and house spraying reduce infection likelihood
Higher temperature is linked to positive malaria cases
Access to healthcare (distance) influences outcomes

  Challenges Encountered
Handling inconsistent categorical data
Managing missing values without bias
Treating extreme outliers
Ensuring model stability (multicollinearity)