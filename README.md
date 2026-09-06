# 🦠 Ebola Outbreak Data Analysis (2014–2016)

## 📌 Project Overview

This project presents an end-to-end exploratory data analysis (EDA) of the **2014–2016 Ebola outbreak** using Python.

The analysis focuses on cleaning, validating, restructuring, analyzing, and visualizing epidemiological data reported across affected countries.

The objective is to transform raw reporting data into a clean and reproducible analytical dataset and extract meaningful insights about:

- the evolution of Ebola cases over time,
- cumulative cases and deaths,
- differences between affected countries,
- Case Fatality Ratio (CFR),
- missing values and reporting inconsistencies.

---

## 🎯 Project Objectives

The main objectives of this project are to:

- Explore and understand the structure of the raw dataset.
- Clean and standardize epidemiological data.
- Validate duplicates and reporting-series consistency.
- Reshape data from long to wide format.
- Identify and treat missing values.
- Analyze cumulative Ebola cases and deaths.
- Calculate the Case Fatality Ratio (CFR).
- Compare the epidemiological profiles of affected countries.
- Produce clear and interpretable data visualizations.

---

## 📊 Dataset

The dataset contains Ebola epidemiological reporting data covering the period:

**29 August 2014 – 23 March 2016**

The original dataset contains:

- **17,585 observations**
- **4 variables**

Main variables:

| Variable | Description |
|---|---|
| `Indicator` | Epidemiological indicator |
| `Country` | Country or reporting series |
| `Date` | Reporting date |
| `value` | Reported numerical value |

The analysis focuses primarily on two indicators:

- Cumulative number of confirmed, probable and suspected Ebola cases
- Cumulative number of confirmed, probable and suspected Ebola deaths

The dataset is based on **World Health Organization (WHO)** reporting and was distributed through the **Humanitarian Data Exchange (HDX)**.

---

## 🛠️ Technologies & Skills

### Programming

- Python

### Data Analysis

- Pandas
- NumPy

### Data Visualization

- Matplotlib
- Seaborn

### Analytical Skills Demonstrated

- Data Cleaning
- Data Validation
- Exploratory Data Analysis (EDA)
- Missing Value Analysis
- Data Transformation
- Long-to-Wide Reshaping
- GroupBy Operations
- Data Aggregation
- Time-Series Exploration
- Case Fatality Ratio Calculation
- Data Visualization
- Epidemiological Data Analysis

---

## 🔄 Data Analysis Pipeline

The project follows a structured analytical workflow:

### 1. Data Loading & Exploration

The raw dataset is imported and inspected to understand its dimensions, variables, data types, and reporting structure.

### 2. Data Cleaning

Text fields are standardized and reporting dates are converted to a consistent datetime format.

### 3. Data Integrity Validation

The dataset is checked for:

- missing values,
- exact duplicates,
- country/date/indicator collisions,
- distinct reporting series.

Special attention is given to reporting series such as:

- `Liberia` / `Liberia 2`
- `Guinea` / `Guinea 2`

### 4. Indicator Selection

The analysis focuses on cumulative Ebola cases and cumulative Ebola deaths.

### 5. Temporal Analysis

The evolution of cumulative cases is examined over time, particularly for:

- Guinea
- Liberia
- Sierra Leone

Secondary reporting series are analyzed separately.

### 6. Data Reshaping

The dataset is transformed from **long format to wide format** using Pandas pivot operations.

### 7. Missing Value Treatment

After reshaping, **8 missing case values** are identified.

The surrounding observations are examined before applying bounded linear interpolation within each country's reporting series.

### 8. Case Fatality Ratio

The final Case Fatality Ratio is calculated as:

**CFR (%) = (Final Deaths / Final Cases) × 100**

### 9. Comparative Analysis

Countries are compared using:

- time-series plots,
- horizontal bar charts,
- grouped bar charts,
- normalized heatmaps.

---

## 🔎 Key Findings

### Epidemic Magnitude

The Ebola outbreak was highly concentrated in three main reporting series:

- **Sierra Leone**
- **Liberia**
- **Guinea**

At the latest observation:

| Country | Cumulative Cases | Cumulative Deaths |
|---|---:|---:|
| Sierra Leone | 14,122 | 3,955 |
| Liberia | 10,666 | 4,806 |
| Guinea | 3,804 | 2,536 |

**Sierra Leone recorded the highest cumulative number of cases**, while **Liberia recorded the highest cumulative number of deaths** among the three main countries.

### Case Fatality Ratio

Among the three main reporting series:

| Country | Final CFR |
|---|---:|
| Guinea | ~66.7% |
| Liberia | ~45.1% |
| Sierra Leone | ~28.0% |

Guinea therefore shows the highest final CFR among the three major reporting series.

High CFR percentages observed in some smaller reporting series should be interpreted cautiously because they are based on very small numbers of cases.

### Data Quality

The analysis also identified important data-quality considerations:

- multiple reporting series exist for some countries;
- retrospective corrections occur in cumulative reporting;
- 8 missing case observations appeared after reshaping;
- missing observations were analyzed in their temporal context before imputation.

---

## 📈 Visualizations

The notebook includes several visual analyses:

- Evolution of cumulative Ebola cases over time
- Analysis of secondary reporting series
- Case Fatality Ratio by country
- Final cumulative cases and deaths
- Comparison of Guinea, Liberia, and Sierra Leone
- Normalized epidemiological heatmap

These visualizations help reveal differences in epidemic magnitude, mortality, and reporting patterns.

---

## 📁 Repository Structure

```text
Ebola-outbreak-data-analysis/
│
├── data/
│   └── ebola_data_db_format.csv
│
├── ebola_outbreak_analysis.ipynb
│
└── README.md
