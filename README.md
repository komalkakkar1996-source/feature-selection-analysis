# feature-selection-analysis
Feature Selection Analysis on Student Exam  Performance using 9 ML methods | Python | Scikit-learn

# Feature Selection Analysis — Student Exam Performance

## Overview
Comprehensive feature selection analysis on a dataset of 
630,000 students to identify the most important variables 
influencing exam performance.

Applied 9 feature selection techniques across 3 categories 
with RFECV used first to scientifically determine the optimal 
number of features.

## Dataset
- 630,000 rows × 13 columns
- Target variable: exam_score
- Features: study_hours, class_attendance, sleep_hours, 
  sleep_quality, study_method, facility_rating, 
  exam_difficulty, gender, course, age, internet_access

> Full dataset not publicly available.
> sample_train.csv (500 rows) included for demonstration.

## Approach
1. Baseline model with all 23 features → R² benchmark
2. RFECV → scientifically found 17 optimal features
3. 9 Feature selection methods applied (k=17)
4. Final model → before vs after comparison

## Methods Used

| Category | Methods |
|---|---|
| Filter | Correlation, Variance Threshold, Chi-Square, Mutual Information, VIF |
| Wrapper | RFECV, RFE, Sequential Feature Selection |
| Embedded | Lasso, Random Forest |

## Key Results

| Metric | Baseline | Final |
|---|---|---|
| Features | 23 | 17 |
| Test R² | 0.7780 | 0.7781 |
| Overfitting | No | No |
| Complexity | High | Low  |

-  6 redundant features removed (26% reduction)
-  Zero performance loss
-  study_hours selected by ALL 9 methods
-  No overfitting detected

## RFECV Deep Dive
RFECV revealed 3 zones:
- Learning Zone (1-10 features): R² grows rapidly
- Saturation Zone (11-17): Only 0.0128% gain
- Noise Zone (18-23): R² drops

> Production insight: 11 features achieve same R²
> with just 0.0128% difference — ideal for deployment.

## Tech Stack
Python | Scikit-learn | Pandas | NumPy | Matplotlib | Seaborn

## Author
**Komal Kakkar**
[LinkedIn](https://www.linkedin.com/in/komalkakkar01/)
