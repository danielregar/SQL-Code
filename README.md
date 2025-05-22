# 🧼 Layoffs Data Cleaning & Analysis (SQL Project)

This project focuses on cleaning and analyzing a real-world dataset of global tech and non-tech layoffs from **2023 to March 2025**. The original dataset was sourced from [Kaggle](https://www.kaggle.com/datasets/happyude/world-layoffs?select=layoffs.csv) and contains raw records with inconsistencies, missing values, and formatting issues.

---

## 🧾 Dataset Overview

The original dataset contains the following columns:

- `company`: Company name
- `location`: Office location(s)
- `industry`: Industry sector
- `total_laid_off`: Number of employees laid off
- `percentage_laid_off`: Proportion of total workforce affected
- `stage`: Company growth stage (e.g., Seed, Series A, IPO)
- `country`: Country of operation
- `funds_raised`: Total capital raised
- `date`: Layoff date (timestamp format)

---
## 📋 Data Quality Assessment (DQA)

Before data cleaning, I conducted a structured assessment to identify issues such as blanks, formatting inconsistencies, and unclean values. This process is documented in a tracker used to decide what can be fixed and what needs to be acknowledged.

👉 [View Data Cleaning Tracker (Google Sheets)][(https://your-link-here)](https://docs.google.com/spreadsheets/d/1NNZJWQno_U9dFFm1f18Wg5Pw5XtRt5RqfB-u9HJzqFo/edit?usp=sharing)

This tracker helps:
- Identify column-level issues
- Quantify affected rows and % impact
- Document resolutions or limitations
---

## 🧹 Data Cleaning Steps

Performed using MySQL to ensure data is structured and analysis-ready.

### 1. Duplicate Removal
- Used `ROW_NUMBER()` with `PARTITION BY` to identify and remove duplicate records.

### 2. Data Standardization
- Trimmed extra spaces from text fields.
- Cleaned `location` values to remove inconsistent formatting (e.g., `[‘City’, 'Non-U.S.']`).
- Converted `date` values from text to date `YYYY-MM-DD`.
- Rounded and cleaned `percentage_laid_off` values.

### 3. Handling Null & Blank Values
- Replaced empty `industry` with `'Other'`.
- Replaced missing `stage` with `'Unknown'`.
- Removed or NULL-ed invalid percentage values (e.g., `0%`).

### 4. Column Cleanup
- Removed intermediate columns used for transformation (`row_num`, raw `date`).

---

## 📊 Exploratory Data Analysis (EDA)

After cleaning, SQL-based EDA was conducted to uncover insights into global layoff patterns.

### 🔍 Key EDA Queries:
- 📈 Total layoffs: Count, sum, average, and maximum layoffs across all events.
- 🗓️ Layoffs over time: Monthly and quarterly trends.
- 🏢 Repeated layoffs: Companies with multiple layoff events.
- 🌍 Distribution: Layoffs by industry, country, and company stage.
- 🔁 Rolling totals: Cumulative layoffs tracked globally and per industry over time.

### 💡 Highlights:
- Identifies the most affected industries and countries.
- Tracks how layoff events evolved month-by-month.
- Detects companies with repeated layoff patterns.
- Compares layoffs across funding stages (e.g., Public vs. Seed).


---

## 📂 Project Structure

- SQL script for data cleaning
- SQL script for exploratory data analysis
- `README.md` — Project documentation (this file)

---

## 🛠️ Tools Used

- **MySQL**
- SQL Window Functions (`ROW_NUMBER()`, `PARTITION BY`, `OVER`)
- Date manipulation, CTEs, and conditional logic

---

## 👨‍💻 Author

**Daniel Siregar**  


---
