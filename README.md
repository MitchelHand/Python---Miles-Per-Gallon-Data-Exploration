# Python Data Analysis Project: Vehicle MPG Dataset Exploration

## Overview

This repository features a series of data analysis exercises conducted in Python, utilizing the Pandas library to explore and derive insights from a vehicle Miles Per Gallon (MPG) dataset. This project demonstrates practical skills in data manipulation, feature engineering, statistical analysis, and conditional data selection, all crucial for effective data-driven decision-making.

## Objective

The primary objective of this project was to perform various data transformations and analyses on a vehicle dataset to answer specific questions about vehicle characteristics, fuel economy, and distribution patterns. This involved creating new data features, calculating key metrics, and filtering data based on defined criteria.

## Key Skills Demonstrated

* 🐍 **Python Programming:** Fundamental scripting and data handling in Python.
* 🐼 **Pandas Data Manipulation:** Proficient use of the Pandas library for data loading, inspection, and transformation.
* ⚙️ **Feature Engineering:** Creating new, meaningful columns from existing data (e.g., `is_automatic`, `fuel_economy`).
* 📊 **Data Aggregation & Statistics:** Performing calculations like `sum()`, `mean()`, and `median()` on DataFrame columns.
* 🎯 **String Operations:** Applying string methods (`.str.lower()`, `.str.contains()`) for text-based data cleaning and feature extraction.
* 🔍 **Boolean Masking:** Advanced filtering of DataFrames based on complex logical conditions.
* 📈 **Data Interpretation:** Deriving actionable insights from manipulated and analyzed data.

## Project Exercises & Insights

The following exercises were successfully completed, showcasing a range of Pandas and Python techniques:

### 1. Identify Automatic Transmissions

**Task:** Create a new column named `is_automatic` that holds a Boolean value indicating if a given vehicle has an automatic transmission.

**Code:**
```python
mpg['is_automatic'] = mpg['trans'].str.lower().str.contains('auto')
```

**Technique:** String manipulation and boolean assignment. The `trans` column is converted to lowercase, and then checked for the presence of the substring 'auto'.

**Insight:** This demonstrates the ability to derive new categorical features from existing textual data, which can be invaluable for subsequent analysis or machine learning tasks.

### 2. Count Automatic Vehicles

**Task:** Use the `is_automatic` column to sum up the number of automatic vehicles in this dataset.

**Code:**
```python
mpg["is_automatic"].sum()
```

**Technique:** Aggregation on a boolean column. In Pandas, `True` is treated as `1` and `False` as `0` for numerical operations, allowing a direct sum to count `True` occurrences.

**Insight:** Quickly quantifies a specific characteristic across the dataset, providing a rapid overview of vehicle transmission types. The result (157 automatic vehicles) provides a concrete statistic.

### 3. Percentage of Subcompact Vehicles

**Task:** Determine what percentage of the vehicles are subcompacts.

**Code:**
```python
subcompact_percentage = (mpg["class"] == "subcompact").mean() * 100
print(f"Percentage of subcompact vehicles: {subcompact_percentage:.2f}%")
```

**Technique:** Boolean masking combined with mean calculation. Filtering for 'subcompact' creates a boolean series, and `.mean()` calculates the proportion of `True` values, which is then converted to a percentage.

**Insight:** Provides a clear demographic breakdown of the vehicle types within the dataset (14.96% subcompacts), useful for market analysis or fleet composition understanding.

### 4. Calculate Combined Fuel Economy

**Task:** Add a new column named `fuel_economy` to the `mpg` dataframe, representing a weighted average of city (55%) and highway (45%) fuel values.

**Code:**
```python
mpg["fuel_economy"] = (mpg["cty"] * 0.55) + (mpg["hwy"] * 0.45)
```

**Technique:** Arithmetic operations on DataFrame columns. This involves element-wise multiplication and addition to create a new derived metric.

**Insight:** Demonstrates the ability to create custom performance metrics that reflect real-world usage patterns, providing a more holistic view of vehicle efficiency than just city or highway MPG alone.

### 5. Vehicles Above Median Fuel Economy

**Task:** Use Boolean masking to find all vehicles with a `fuel_economy` above the median `fuel_economy`.

**Code:**
```python
median_fuel = mpg["fuel_economy"].median()
above_median = mpg[mpg["fuel_economy"] > median_fuel]
```

**Technique:** Two-step boolean masking. First, the median of the `fuel_economy` column is calculated. Second, this median is used as a threshold to filter the DataFrame, returning only rows where `fuel_economy` exceeds the median.

**Insight:** This highlights the capability to perform statistical analysis and then use the results to segment data, identifying high-performing (or low-performing) subsets of a dataset.

## Tools and Environment

* 🐍 **Python:** The core programming language used for all data analysis.
* 🐼 **Pandas Library:** The primary data manipulation and analysis library.
* ☁️ **Google Colab:** The interactive environment used for executing the Python code and presenting results, indicating familiarity with cloud-based development platforms.

## Conclusion

This project demonstrates a solid foundation in Python and Pandas for practical data analysis. From feature engineering and statistical aggregation to advanced data filtering, the exercises showcase my ability to extract meaningful insights and prepare data for further analysis or reporting. I am adept at transforming raw data into actionable intelligence.

---

**Contact:** Mitchel Hand / [LinkedIn Profile Link](https://www.linkedin.com/in/mitchel-hand-5a802430b/) / mitchelhanddesign@hotmail.com

![image](https://github.com/user-attachments/assets/4c3e3c14-bf9e-4531-a3cf-8ba8c271de0b)
