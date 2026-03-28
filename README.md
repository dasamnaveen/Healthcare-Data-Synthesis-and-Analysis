# Healthcare-Data-Synthesis-and-Analysis
A comprehensive Python-based project demonstrating the end-to-end lifecycle of medical data: from synthetic generation of 'messy' clinical records to advanced cleaning, outlier handling, and exploratory visual analysis.

----

[](https://www.python.org/)
[](https://pandas.pydata.org/)
[](https://seaborn.pydata.org/)

## Project Overview

This project demonstrates an end-to-end data science workflow within the healthcare domain. It covers the full lifecycle of data: from the **programmatic synthesis** of a complex medical dataset to **robust data cleaning** and deep **Exploratory Data Analysis (EDA)**.

The project is unique because it starts with a custom script that intentionally injects "messy" real-world data issues (outliers, missing values, inconsistent formats), providing a rigorous test for the subsequent cleaning and analysis pipeline.

## Tech Stack

  * **Language:** Python
  * **Data Manipulation:** Pandas, NumPy
  * **Data Cleaning:** Feature-engine (Winsorizer)
  * **Visualization:** Matplotlib, Seaborn

## The Dataset

The analysis is performed on a synthetic dataset of **12,500 patient records** featuring 22 initial variables including:

  * **Demographics:** Age, Gender, Blood Type.
  * **Clinical Vitals:** BMI, Systolic/Diastolic BP, Cholesterol, Heart Rate, Glucose Levels.
  * **Logistics:** Medical Condition, Insurance Provider, Billing Amount, Admission Type, and Doctor details.

## Data Cleaning & Preprocessing

To transform the "raw" messy data into a clean, analysis-ready format, the following steps were implemented:

1.  **Duplicate Removal:** Identified and removed 100 duplicate rows.
2.  **Missing Value Treatment:** \* Imputed missing numerical values (BMI, Cholesterol, Glucose) using **Median Imputation**.
      * Handled missing categorical data (Medical Condition, Smoker Status) using **Mode Imputation**.
3.  **Outlier Handling:** \* Used **Winsorization** (IQR-based capping) to treat extreme outliers in skewed features like Systolic BP and Glucose Levels.
4.  **Standardization:** Resolved inconsistent categorical entries (e.g., merging 'M'/'Male' and 'F'/'Female') and standardized text casing.
5.  **Feature Engineering:** Extracted `Year`, `Month`, and `Weekday` from visit dates and created health status classifiers like `BP_Status` and `BMI_Class`.

## Key Insights & Visualizations

  * **Age Demographics:** Analyzed the distribution of patient ages using histograms to identify the most common age groups served by the hospital.
  * **Clinical Correlations:** Investigated health profiles by gender, revealing average BMI and Cholesterol levels across different patient segments.
  * **Billing Analysis:** Calculated total and average billing across different Insurance Providers (Aetna, Blue Cross, Cigna, Medicare, UnitedHealth).
  * **Hospital Operations:** Tracked condition prevalence across different hospital tiers and ranked doctor performance based on patient volume.

## How to Run

1.  Clone the repository:
    ```bash
    git clone https://github.com/YourUsername/Healthcare-Data-Synthesis-and-Analysis.git
    ```
2.  Install required libraries:
    ```bash
    pip install pandas numpy matplotlib seaborn feature-engine
    ```
3.  Run the Jupyter Notebook:
    ```bash
    jupyter notebook healthcare_eda_analysis.ipynb
    ```
