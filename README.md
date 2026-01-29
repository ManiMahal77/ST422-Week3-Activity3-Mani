# Week 3: Subscription Churn Analysis

**Author:** Mani Mahal

**Date:** 29th January 2026

## 1. Project Summary
This repository contains an analysis of customer subscription data. The primary objective is to describe the customer base and compare active subscribers against those who have churned (cancelled).

The workflow is designed to be reproducible. It generates a summary table (Table 1) and visualisations of fee distributions and regional churn rates. The code is robust to dataset updates; it can handle version updates (e.g., v1 to v2) provided the column structure remains consistent.

## 2. Data Description
The analysis relies on subscription data located in the `data/raw/` directory.

* **Unit of analysis:** Each row represents a single customer subscription.
* **Key outcome variable:** `churned_90d` (Binary: 0 = Active, 1 = Churned).
* **Grouping variables:** The report stratifies data by `region` and `plan_type`.

For a full list of variables and definitions, please refer to `DATA DICTIONARY.md` in the root folder.

## 3. Dependencies
This project uses `renv` to manage R package dependencies and ensure version consistency.

The analysis relies on the following R packages:

* **Data Manipulation & Import:** `tidyverse` (including `dplyr`, `readr`, `ggplot2`), and `rio`.
* **Tables & Reporting:** `gtsummary`, `gt`, `kableExtra`, `knitr`, and `rmarkdown`.

You do not need to install these manually; the `renv.lock` file contains the exact versions required.

## 4. Run Steps
Follow these steps to reproduce the analysis on a new machine:

1.  **Clone the repository** to your local machine.
2.  **Open the project** by double-clicking `st422-week3.Rproj`.
3.  **Restore the environment** by running the following command in the R console:
    ```r
    renv::restore()
    ```
    *Note: This may take a few minutes to install the required packages.*
4.  **Generate the report** by running:
    ```r
    rmarkdown::render("reports/week3_report.Rmd")
    ```

## 5. Expected Outputs
Upon successful execution, the code will populate the `outputs/` folder with the following files:

* **Tables:**
    * `outputs/tables/table1.csv`: A summary table of tenure, fees, and NPS scores stratified by churn status.
* **Figures:**
    * `outputs/figures/fig1_fee_dist.png`: A boxplot showing monthly fees by plan type.
    * `outputs/figures/fig2_churn_region.png`: A bar chart showing the proportion of churn across different regions.

## 6. Assumptions and Limitations
* **Missing Data:** The variable `nps_score` contains missing values in the v1 dataset. The analysis currently handles this by reporting valid entries only; no imputation has been performed.
* **File Paths:** The report assumes the input file is located at `../data/raw/`. If the input filename changes (e.g., to `v2`), you must update the filename variable in the configuration chunk of `week3_report.Rmd`.
* **OS:** This workflow was developed and tested on Windows 11.
