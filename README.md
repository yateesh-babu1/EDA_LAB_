# EDA_LAB_
# Telecom Customer Churn Analysis

## Project Overview

This project focuses on preparing and exploring a telecom customer
dataset to understand customer behaviour and identify factors associated
with customer churn. The dataset contains customer usage details, plan
information, contract duration, overdue payments, and the target
variable `churn_next_month`.

## Dataset Features

The dataset includes the following columns:

-   `user_id` -- Customer identifier.
-   `monthly_minutes` -- Monthly call usage.
-   `monthly_data_mb` -- Monthly internet data usage in MB.
-   `monthly_sms` -- Monthly SMS usage.
-   `monthly_data_mb_dup` -- Duplicate data-usage column checked during
    preprocessing.
-   `contract_months` -- Customer contract duration in months.
-   `churn_next_month` -- Target variable indicating whether the
    customer churns.
-   `plan_type` -- Customer subscription plan.
-   `has_family_plan` -- Indicates whether the customer has a family
    plan.
-   `overdue_payments` -- Number of overdue payments.

## Tools and Libraries

-   Python
-   Pandas
-   NumPy
-   Matplotlib
-   Seaborn
-   Scikit-learn
-   Google Colab

## Data Preprocessing

The following preprocessing activities were performed:

1.  **Missing-value handling:** Replaced placeholder values such as `?`
    with missing values and converted numeric columns to numeric data
    types. Numerical missing values were filled using the mean where
    appropriate, while categorical values such as `plan_type` were
    filled using the mode. Rows with missing target labels
    (`churn_next_month`) were removed rather than assigning artificial
    labels.
2.  **Inconsistency handling:** Standardized inconsistent category
    labels in categorical columns such as `plan_type` and
    `has_family_plan`.
3.  **Duplicate removal:** Checked for and removed duplicate rows.
4.  **Duplicate-column handling:** Checked whether `monthly_data_mb_dup`
    duplicated `monthly_data_mb` and removed the duplicate column when
    appropriate.
5.  **Categorical encoding:** Applied one-hot encoding to `plan_type`
    and converted `has_family_plan` into numeric values where required.
6.  **Identifier handling:** Removed `user_id` from model features
    because it is an identifier rather than a customer-behaviour
    measurement.
7.  **Outlier handling:** Used the IQR method to identify numerical
    outliers and applied capping where appropriate.
8.  **Feature scaling:** Applied StandardScaler to numerical features
    when preparing data for machine learning.

> For model evaluation, split the data into training and testing sets
> before fitting imputers, outlier limits, or scalers. Fit preprocessing
> steps on the training data only, then apply the fitted transformations
> to the test data to avoid data leakage.

## Exploratory Data Analysis (EDA)

### 1. Univariate Analysis

Univariate analysis examined each variable separately using: -
Histograms to understand numerical distributions. - Pie charts to show
category proportions or grouped numerical ranges. - Boxplots to inspect
spread and potential outliers.

### 2. Bivariate Analysis

Bivariate analysis explored relationships between pairs of variables
using: - Count plot to compare customer counts across categories and
churn groups. - Scatter plot to inspect the relationship between monthly
usage and churn. - Boxplot to compare numerical distributions across
churn groups.

### 3. Multivariate Analysis

A correlation heatmap was created to examine relationships among
multiple numerical variables, including the churn target. It helps
identify correlated features and variables associated with churn.

## Project Workflow

1.  Load the dataset.
2.  Inspect the dataset structure and data types.
3.  Handle missing values and inconsistent entries.
4.  Remove duplicate records and redundant columns.
5.  Encode categorical variables and exclude identifier columns from
    model inputs.
6.  Detect and handle outliers.
7.  Perform exploratory data analysis.
8.  Scale numerical features as part of the machine-learning pipeline.
9.  Prepare the data for model training and evaluation.

## How to Run

1.  Open the project notebook in Google Colab.
2.  Upload the dataset or connect it from Google Drive.
3.  Run the notebook cells in order, starting with library imports and
    dataset loading.
4.  Review the preprocessing output and EDA visualizations.

## Expected Outcome

The project produces a cleaned dataset and visual summaries of customer
usage patterns and their relationship with churn. These results can
support the next stage of building and evaluating classification models
for customer churn prediction.

## Note

The notebook should be treated as an exploratory data analysis and
preprocessing workflow. Any conclusions about which factors drive churn
should be based on the actual charts and model results, rather than
assumed in advance.
