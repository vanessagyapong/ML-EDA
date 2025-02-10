# Cleaned Dataset: ML-EDA Project

## Overview

This dataset contains information about users of various dating apps, their demographics, preferences, and experiences. It was collected to analyze user behavior, satisfaction, and feature preferences to improve matchmaking and app functionality.

## Data Dictionary

Below is a description of each column in the dataset:

| Column Name               | Data Type | Description |
|---------------------------|-----------|-------------|
| `User_ID`                 | Integer   | Unique identifier for each user |
| `Age`                     | Integer   | Age of the user |
| `Gender`                  | Categorical | Gender identity of the user (standardized) |
| `Location`                | String    | City or region where the user is based |
| `Education`               | String    | Highest level of education completed |
| `Occupation`              | String    | Current job or employment status |
| `Primary_App`             | Categorical | Main dating app the user engages with |
| `Secondary_Apps`          | String    | Other dating apps the user uses |
| `Usage_Frequency`         | Categorical | How often the user accesses dating apps (e.g., Daily, Weekly, Monthly) |
| `Daily_Usage_Time`        | String    | Approximate daily usage time (e.g., 30 minutes, 1 hour, etc.) |
| `Reason_for_Using`        | Categorical | Primary reason for using dating apps (e.g., Finding a Partner, Casual Fun) |
| `Satisfaction`            | Integer   | Satisfaction level (scale of 1-5) |
| `Challenges`              | String    | Common challenges faced while using dating apps (e.g., Safety Concerns) |
| `Desired_Features`        | String    | Features users wish to see in dating apps (e.g., Video Calls, AI Recommendations) |
| `Preferred_Communication` | Categorical | Preferred mode of communication (e.g., Text, Video Calls) |
| `Partner_Priorities`      | String    | What users prioritize in a potential partner (e.g., Personality, Interests) |

## Data Cleaning Steps

The dataset underwent the following cleaning steps:

### Handling Missing Values

- Identified missing values using `df.isnull().sum()`.
- Numerical Columns: Filled missing values using the median.
- Categorical Columns: Filled missing values using the mode (most frequent value) for better consistency.

### Removing Duplicates

- Checked for duplicate rows using `df.duplicated().sum()`.
- Removed all duplicate rows using `df.drop_duplicates(inplace=True)`.

### Standardizing Categorical Data

- Converted all text fields to lowercase and stripped whitespace.
- Ensured consistent formatting (e.g., `Male` and `male` were unified).
- Mapped rare categories to a broader category (`Other` for uncommon values).

### Detecting and Handling Outliers

- Numerical Columns: Used box plots and the IQR method to detect outliers.
- Handling Strategy:
  - Extreme values in `Daily_Usage_Time` were capped to reasonable limits.
  - `Satisfaction` scores outside the 1-5 range were corrected.

Feature Engineering
•Usage Frequency: Label encoded Usage_Frequency into numerical values (e.g., Daily = 3, Weekly = 2, Monthly = 1).
•Active App Count: Created a new feature, Active_App_Count, representing the number of dating apps a user is actively using (either 1 or 2).

### Version Control

- The cleaned dataset was committed as Version 1 in GitHub with the commit message:
  "Cleaned dataset: removed duplicates, handled missing values, and standardized categories."

## Next Steps

- Perform exploratory data analysis (EDA) to visualize relationships between variables.
- Feature engineering and selection for machine learning model training.
- Apply predictive modeling to analyze user behavior and preferences.

---
**Author**: Vanessa Gyapong  
**Repository**: [GitHub - ML-EDA](https://github.com/vanessagyapong/ML-EDA)
