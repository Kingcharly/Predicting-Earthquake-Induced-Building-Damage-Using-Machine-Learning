# Predicting-Earthquake-Induced-Building-Damage-Using-Machine-Learning
To build a classification model that predicts the damage grade of a building based on its structural and geospatial features.

## Phase 1: Data Exploration and Preprocessing

The first phase of the project involved a comprehensive exploration and preprocessing of the dataset to ensure quality and readiness for feature engineering and model development. This phase focused on understanding the structure of the data, identifying potential issues, and preparing the dataset for further analysis.

### 1.1 Data Source

The dataset was obtained from the publicly available "Building Damage Assessment Dataset" for the 2015 Nepal Earthquake.The data was gotten frome Kaggle. Special Thanks to the dataset creator: @sanskar_negi.

### 1.2 Data Overview

The dataset contained structural and post-disaster characteristics of buildings affected by an earthquake. Key features included:

- **Identifiers**: `building_id`, `district_id`, `ward_id`, etc.
- **Numerical variables**: `age_building`, `plinth_area_sq_ft`, `height_ft_pre_eq`, `count_floors_pre_eq`, etc.
- **Categorical variables**: `foundation_type`, `roof_type`, `land_surface_condition`, `plan_configuration`, etc.
- **Target variable**: `damage_grade` (a categorical label indicating severity of damage from Grade 1 to Grade 5)

A total of 762,106 records and 21 features were present in the initial dataset.

The dataset was inspected for its shape, data types, and initial content. Unique IDs such as `building_id` were identified as non-informative for prediction and marked for exclusion in modeling phases.

### 1.3 Data Inspection and Cleaning

Initial inspection involved:
- Previewing Dataset structure and Data types
- Identifying and addressing missing values, duplicates and inconsistencies
- Removing identifiers

Findings:
- Certain features such as `damage_grade`, `technical_solution_proposed`, `position`, `plan_configuration`, were found to contain missing or inconsistent values and were flagged for cleaning and removed.
- Categorical features such as `foundation_type`, `ground_floor_type`, etc. with ***Other*** were subsetted
- Removing irrelevant identifiers (e.g., `building_id`, `ward_id`) 
- Numerical features were examined for extreme outliers (e.g., buildings with unrealistically high ages or zero height).
- Fixing systematic data entry errors where post-earthquake floors and heights were recorded as higher than their pre-earthquake values. A data swapping technique was applied to correct these inconsistencies.


### 1.4 Target Variable Exploration

`damage_grade`, the target variable, was found to be **categorical** with five ordinal classes. The class distribution was visualized to check for imbalance. It was observed that damage grades were sufficient with no class imbalance

### 1.5 Feature Understanding

Each feature was analyzed for its relationship with `damage_grade`:

- **Categorical features** were cross-tabulated with the target to observe patterns (e.g., some foundation types were more likely to appear in higher damage grades).
- **Numerical features** such as `age_building` and `plinth_area_sq_ft` were grouped by `damage_grade` to compute summary statistics. Older buildings, for example, tended to have higher damage severity.
- Visualizations such as box plots, bar charts, and histograms helped clarify these relationships.

### 1.6 Preliminary Feature Relevance Check

- Older buildings also tended to suffer more damage, highlighting `age_building` as a critical feature.
- Buildings constructed on Flat slopes or with less resilient materials (e.g., mud mortar - Stone/Brick) showed higher grades of damage.

---

### Outcome of Phase 1:

- Cleaned and structured dataset ready for feature engineering.
- Identified informative and uninformative features.
- Documented data imbalance in the target variable.
- Gained foundational understanding of feature-target relationships.

This phase established the necessary groundwork for the next phase: **Feature Engineering and Transformation**.
