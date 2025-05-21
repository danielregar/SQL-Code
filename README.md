# 🧼 Layoffs Data Cleaning (SQL Project)

This project focuses on cleaning a real-world dataset of tech and non-tech layoffs worldwide, covering 2023 to March 2025. The original dataset was sourced from [Kaggle]https://www.kaggle.com/datasets/happyude/world-layoffs?select=layoffs.csv, and contains raw records with inconsistencies, missing data, and formatting issues.

---

## 🧾 Dataset Overview

The original dataset includes the following fields:

- `company`: Company name
- `location`: Office location
- `industry`: Industry type
- `total_laid_off`: Number of employees laid off
- `percentage_laid_off`: Proportion of the workforce affected
- `stage`: Company growth stage (e.g., Series A, Series B)
- `country`: Country of operation
- `funds_raised`: Capital raised by the company
- `date`: Layoff date

---

## 🧹 Data Cleaning Steps

1. **Duplicate Removal**
   - Used `ROW_NUMBER()` to identify and delete duplicate records based on key columns.

2. **Standardization**
   - Trimmed and cleaned company and location names.
   - Extracted and standardized date format to `YYYY-MM-DD`.
   - Converted and rounded `percentage_laid_off` values.

3. **Handling Null or Blank Values**
   - Replaced empty `industry` with `'Other'`.
   - Replaced empty `stage` with `'Unknown'`.
   - Removed or NULL-ed invalid `percentage_laid_off` values (e.g., 0%).

4. **Column Cleanup**
   - Removed intermediate columns used for transformation (`row_num`, raw `date` string).

---

## 📂 File Structure

- `layoffs_data_cleaning.sql` — Full SQL script for cleaning the data
- `README.md` — Project description and explanation (this file)

---

## 📊 Tools Used

- MySQL
- SQL Window Functions (`ROW_NUMBER`, `PARTITION BY`)
- CTEs, string functions, date manipulation

---

## 🧠 Author

Daniel Siregar  
