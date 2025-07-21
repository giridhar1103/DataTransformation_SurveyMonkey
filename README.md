# 📊 DataTransformation_SurveyMonkey

## 📝 About the Project

This project demonstrates how to take complex, multi-layered survey data exported from [SurveyMonkey](http://surveymonkey.com/) and transform it into a **tidy**, **analysis-ready** format. It walks through both **Manual preprocessing (Excel)** and **automated cleaning and reshaping (Python/pandas)**.

The data contains multiple-choice questions, each with multiple sub-responses, typical of real-world survey formats. Raw exports from SurveyMonkey are often wide, messy, and not directly usable for analytics. This project shows how to turn that into a clean dataset using reproducible steps.

---

## 📦 Data Overview

The raw dataset includes:
- Respondent metadata (e.g. Start Date, Email Address)
- Multiple questions, each potentially spanning several columns.
- Answers in wide format: each question and sub-question is its own column.

---

## 🔄 Transformation Workflow

### 🧮 Step 1: Manual Preprocessing (Excel)
Before jumping into code, we make some manual tweaks in Excel to prepare the data:
- **Pivot the first two rows** to create a cleaner header structure.
- Ensure that each column represents a single **question-subquestion pair**.
- Validate that every **response column has the correct question heading**.
- Save this cleaned-up sheet as `"Edited_Data"`.

### 🐍 Step 2: Automated Processing in Python
The real transformation starts in `DataManipulation1.ipynb`:

#### ✅ Cleaning
- Drop non-essential columns: `Start Date`, `End Date`, `Email Address`, etc.
- Keep only identifying columns and question-answer data.

#### 🔁 Reshaping with `melt()`
- Convert the dataset from **wide to long format** using `pandas.melt()`.
- This ensures each row represents **one respondent’s answer to one question**.
- Resulting columns: `Respondent ID`, other metadata, `Question+Subquestion`, `Answer`.

#### 🔗 Merging with Metadata
- Use a secondary `"Questions"` sheet to enrich the data:
  - Add question labels, types, and other annotations.
  - Merge on a custom `Question+Subquestion` key.

#### 🧠 Extra Enhancements
- Group responses using `groupby()` to analyze frequency per question.
- Join with another table (`same_answer`) to flag duplicate/identical answers.
- Handle missing values and finalize data structure.

---

## 📊 Output

The final output is a **long-format tidy DataFrame**, ideal for:
- Visualizations
- Statistical analysis
- Dashboards or BI tools
- Export to SQL, CSV, or JSON
- 
---


## 🧠 Concepts Illustrated

- Wide vs. Long data formats
- Tidy data principles
- `pandas.melt()` for unpivoting
- `groupby()` and aggregation
- Safe merging with composite keys
- NaN handling and data enrichment

---
