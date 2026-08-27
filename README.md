# 2.4_PA_Data_Cleaning_and_Visualization_PYTHON
# Data Cleaning and Descriptive Analytics in Python (Airbnb Dataset)

This repository contains Python scripts and Jupyter Notebooks for performing end-to-end data cleaning, descriptive statistical analysis, and data visualization on an Airbnb summary dataset.

---

## 📌 Project Overview

The objective of this project is to process raw Airbnb listing data by resolving data quality issues and running descriptive analytics using Python.

### Key Objectives

1. **Data Cleaning (`Task 1`)**: Identify and remove duplicates, correct textual typos, impute missing values using median calculations, filter outliers using the Interquartile Range (IQR) method, and export a cleaned Excel file.
2. **Descriptive Statistics (`Task 2`)**: Calculate core summary metrics, central tendencies, standard deviations, and correlation coefficients across listing attributes.
3. **Data Visualization (`Task 3`)**: Build visual representations including histograms, bar charts, trendline scatter plots, and correlation heatmaps.

---

## 📁 Dataset Description

* **Source File**: `AirBnBSummary_v2.xlsx`
* **Cleaned Output File**: `AirBnBSummary_v2_Python_Cleaned.xlsx`

| Column Name | Description |
| --- | --- |
| `id` | Unique identifier for the listing |
| `host_id` | Unique identifier for the host |
| `host_name` | Name of the listing host |
| `neighbourhood` | Geocoded neighborhood location |
| `room_type` | Type of property/room rented |
| `price` | Nightly price in USD |
| `minimum_nights` | Minimum stay duration required |
| `number_of_reviews` | Total reviews received |
| `availability_365` | Total available booking days per year |

---

## 🛠️ Requirements & Environment

Ensure you have Python 3.x and the following libraries installed:

```bash
pip install pandas numpy matplotlib seaborn openpyxl ipykernel

```

---

## 🚀 Notebook Structure & Execution

### **Task 1: Data Cleaning (`AirBnB_DataCleaning_Task1.ipynb`)**

* **Duplicates**: Identified via `df.duplicated()` and dropped using `drop_duplicates()`.
* **Typo Fixes**: Corrected casing variations in text fields (e.g., changing `"Private room"` to `"Private Room"`).
* **Missing Values**: Imputed missing numerical values with column medians via `fillna()`.
* **Outliers**: Identified outliers outside the $1.5 \times \text{IQR}$ range ($[Q_1 - 1.5 \times \text{IQR}, Q_3 + 1.5 \times \text{IQR}]$) and replaced them with the column median.
* **Export**: Cleaned dataset saved to `AirBnBSummary_v2_Python_Cleaned.xlsx`.

### **Task 2: Summary Statistics (`AirBnB_DataCleaning_Task2.ipynb`)**

Calculates the following key statistics on the cleaned dataset:

* Total listing count (`nunique()`)
* Price range: Minimum, Maximum, Mean, and Standard Deviation
* Median number of reviews
* Mode of `minimum_nights`
* Pearson correlation coefficient between `price` and `availability_365`

### **Task 3: Visualizations (`AirBnB_DataCleaning_Task3.ipynb`)**

Generates four primary visualizations:

1. **Histogram**: Distribution of `number_of_reviews`.
2. **Bar Chart**: Counts of `minimum_nights` requirements.
3. **Scatter Plot with Trendline**: Relationship between `availability_365` and `price`.
4. **Correlation Heatmap**: Matrix showing pairwise linear relationships between `price`, `minimum_nights`, `number_of_reviews`, and `availability_365`.

---

## 📊 Analytical Insights

* **Scatter Plot Trendline**: The slope of the regression line indicates how listing availability across the year (`availability_365`) influences nightly pricing.
* **Correlation Analysis**: The correlation heatmap reveals which variable pairs demonstrate strong linear relationships, aiding in further predictive modeling.
