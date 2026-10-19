# 🛍️ Customer Behavior Analysis | Python, SQL & Power BI

![Project](https://img.shields.io/badge/Project-Customer%20Analytics-blue)
![Python](https://img.shields.io/badge/Python-Pandas%20%7C%20NumPy-yellow)
![SQL](https://img.shields.io/badge/SQL-Data%20Analysis-blue)
![Power BI](https://img.shields.io/badge/Power%20BI-Interactive%20Dashboard-F2C811)
![Analytics](https://img.shields.io/badge/Domain-Customer%20Analytics-green)

## 📌 Project Overview

Customer behavior analysis helps businesses understand how customers interact with products, what influences their purchasing decisions, and how purchasing patterns differ across customer segments.

This project explores customer purchasing data to identify patterns in spending, product preferences, review ratings, and subscription behavior.

Using Python, SQL, and Power BI, the project demonstrates a structured data analytics workflow, including data preparation, exploratory data analysis, SQL-based investigation, and dashboard development.

The objective is to transform customer data into meaningful information that can support business reporting and customer-focused decision-making.

## 🎯 Project Objectives

* Understand customer purchasing behavior.
* Explore purchasing patterns across available customer segments.
* Analyze purchase amounts and spending distributions.
* Examine product category performance.
* Investigate customer review ratings.
* Analyze subscription status and related purchasing patterns.
* Identify trends and relationships within the available data.
* Develop an interactive Power BI dashboard.
* Present findings through clear visualizations and business-oriented metrics.

## 🛠️ Tools & Technologies

| Tool             | Purpose                                                  |
| ---------------- | -------------------------------------------------------- |
| Python           | Data cleaning and exploratory data analysis              |
| Pandas           | Data manipulation and analysis                           |
| NumPy            | Numerical operations                                     |
| SQL              | Filtering, grouping, aggregation, and analytical queries |
| Power BI         | Dashboard creation and data visualization                |
| Power Query      | Data transformation, if used                             |
| DAX              | Measures and KPI calculations, if used                   |
| Jupyter Notebook | Python analysis, if used                                 |
| GitHub           | Project documentation and portfolio hosting              |

## 📂 Project Structure

```text
customer-behavior-analysis/
│
├── README.md
│
├── dataset/
│   └── customer_data.csv
│
├── python/
│   └── customer_behavior_analysis.ipynb
│
├── sql/
│   └── customer_behavior_analysis.sql
│
├── powerbi/
│   └── customer_behavior_dashboard.pbix
│
└── screenshots/
    └── customer_behavior_dashboard.png
```

*This is a suggested structure. Replace the example filenames with your actual project files.*

## 📊 Dataset Description

The project uses customer purchasing data to investigate customer preferences and purchasing patterns.

Depending on the actual dataset, the analysis may include:

* Customer demographics.
* Product categories.
* Purchase amounts.
* Review ratings.
* Subscription status.
* Purchase frequency or related behavioral attributes.
* Other available customer and transaction fields.

The exact dataset schema determines which questions can be answered.

Before analysis, the data should be checked for missing values, duplicate records, inconsistent categories, incorrect data types, and invalid numerical values.

Do not publish private customer information or datasets that you are not authorized to share.

## 🧹 Data Cleaning & Preparation

Data preparation is performed to improve the consistency and reliability of the analysis.

### Key activities

1. Inspect the dataset structure and column names.
2. Review data types and summary statistics.
3. Identify missing values.
4. Check for duplicate records.
5. Investigate inconsistent categorical values.
6. Validate purchase amounts and review ratings.
7. Prepare appropriate columns for analysis.
8. Validate the cleaned dataset before visualization.

### Example Python code

```python
import pandas as pd
import numpy as np

# Load the dataset
df = pd.read_csv("dataset/customer_data.csv")

# Inspect the first five rows
print(df.head())

# Check dataset dimensions
print("Dataset shape:", df.shape)

# Review column names
print(df.columns.tolist())

# Inspect data types and non-null counts
df.info()

# Check missing values
print(df.isnull().sum())

# Check duplicate rows
print("Duplicate rows:", df.duplicated().sum())

# Generate descriptive statistics
print(df.describe(include="all"))
```

These examples should be adapted to the actual dataset and its column names.

## 🐍 Python Exploratory Data Analysis

Python is used to explore customer data, understand distributions, and identify patterns that may be useful for further analysis.

### Areas of analysis

* Customer segment distributions.
* Purchase amount distributions.
* Product category comparisons.
* Review rating distributions.
* Subscription status comparisons.
* Relationships between available numerical variables.
* Missing-value and duplicate-record analysis.

### Example: Analyze purchase amounts

```python
# Replace Purchase Amount with the actual column name
purchase_summary = df["Purchase Amount"].describe()

print(purchase_summary)
```

### Example: Analyze product categories

```python
# Replace Category with the actual column name
category_summary = (
    df.groupby("Category")
      .size()
      .sort_values(ascending=False)
)

print(category_summary)
```

### Example: Compare subscription groups

```python
# Replace Subscription Status and Purchase Amount
# with the actual column names in your dataset.

subscription_summary = (
    df.groupby("Subscription Status")["Purchase Amount"]
      .agg(["count", "mean", "median", "sum"])
)

print(subscription_summary)
```

These snippets are examples. The actual column names, missing-value handling, and analysis should match the dataset.

## 🗄️ SQL Analysis

SQL is used to investigate customer behavior through structured queries.

The analysis can explore purchasing patterns, product categories, review ratings, and subscription groups.

### Example analytical questions

* How many records are available?
* Which product categories appear most frequently?
* What is the average purchase amount?
* How do purchase amounts differ across subscription groups?
* What is the distribution of review ratings?
* Which customer groups have the highest average spending?
* Are there missing or repeated records requiring investigation?

### Example SQL queries

The following queries assume a table named `customer_data`. Update the table and column names to match your actual database.

#### 1. View sample records

```sql
SELECT *
FROM customer_data
LIMIT 10;
```

#### 2. Count total records

```sql
SELECT COUNT(*) AS total_records
FROM customer_data;
```

#### 3. Analyze product categories

```sql
SELECT
    Category,
    COUNT(*) AS total_records
FROM customer_data
GROUP BY Category
ORDER BY total_records DESC;
```

#### 4. Calculate average purchase amount

```sql
SELECT
    AVG(`Purchase Amount`) AS average_purchase_amount
FROM customer_data;
```

#### 5. Compare subscription groups

```sql
SELECT
    `Subscription Status`,
    COUNT(*) AS total_records,
    AVG(`Purchase Amount`) AS average_purchase_amount
FROM customer_data
GROUP BY `Subscription Status`;
```

#### 6. Analyze review ratings

```sql
SELECT
    `Review Rating`,
    COUNT(*) AS rating_count
FROM customer_data
GROUP BY `Review Rating`
ORDER BY `Review Rating`;
```

#### 7. Find repeated customer identifiers

```sql
SELECT
    `Customer ID`,
    COUNT(*) AS record_count
FROM customer_data
GROUP BY `Customer ID`
HAVING COUNT(*) > 1
ORDER BY record_count DESC;
```

Repeated customer identifiers do not necessarily indicate duplicate records. A customer may legitimately make multiple purchases.

## 📈 Power BI Dashboard

Power BI provides an interactive way to explore customer purchasing data and present the results visually.

### Potential KPIs

| KPI                       | Description                                                            |
| ------------------------- | ---------------------------------------------------------------------- |
| Total Records             | Number of records included in the analysis                             |
| Total Customers           | Number of distinct customers, if a reliable customer identifier exists |
| Average Purchase Amount   | Average of valid purchase amounts                                      |
| Total Purchase Amount     | Sum of purchase amounts, where the data supports this calculation      |
| Average Review Rating     | Average of valid review ratings                                        |
| Subscription Distribution | Distribution of records or customers by subscription status            |

The precise KPI definitions should reflect the dataset. For example, a record count should not be labeled as a unique customer count.

### Potential visualizations

* KPI cards for summary metrics.
* Bar charts for product category comparisons.
* Column charts for customer segment comparisons.
* Charts showing review rating distributions.
* Subscription status comparisons.
* Slicers for available customer attributes.
* Tables showing detailed analytical results.

### Dashboard Screenshot

After uploading a screenshot of your actual Power BI report, display it here:

```markdown
![Customer Behavior Dashboard](screenshots/customer_behavior_dashboard.png)
```

A screenshot helps recruiters understand your analytical work without opening Power BI Desktop.

## 🔍 Business Questions

This project can investigate questions such as:

1. Which product categories have the most records?
2. What is the average purchase amount?
3. How do purchase amounts differ across customer groups?
4. How are review ratings distributed?
5. What proportion of records belongs to each subscription group?
6. Which customer segments show different purchasing patterns?
7. Are there unusual values or data quality issues?
8. What patterns are visible when the dashboard is filtered?
9. Which customer attributes are associated with differences in purchasing behavior?
10. What additional analysis would help the business understand its customers?

These questions should be answered using actual query results and validated dashboard findings.

## 💡 Key Insights & Findings

Document the results obtained from the completed analysis in this section.

Examples of findings to investigate include:

* Product categories with the highest record counts.
* Differences in average purchase amounts across groups.
* The distribution of customer review ratings.
* Subscription-group differences in purchasing metrics.
* Missing values or duplicate records affecting data quality.
* Customer segments with distinct purchasing patterns.

Do not assume that one group spends more or performs better than another without checking the actual results.

## 🔄 Project Workflow

**Step 1 — Data Collection:** Obtain the dataset and understand its structure.

**Step 2 — Data Cleaning:** Investigate missing values, duplicates, and inconsistencies.

**Step 3 — Python Analysis:** Explore distributions, summarize data, and investigate customer patterns.

**Step 4 — SQL Analysis:** Query the dataset and calculate relevant metrics.

**Step 5 — Power BI Dashboard:** Visualize the results through KPIs, charts, and interactive filters.

**Step 6 — Validation:** Check calculations and confirm that the dashboard reflects the underlying data.

**Step 7 — Documentation:** Record the methods, findings, and project files in GitHub.

## 🎓 Skills Demonstrated

### Technical Skills

* Python data analysis.
* Pandas and NumPy.
* SQL queries and aggregations.
* Data cleaning and preprocessing.
* Exploratory data analysis.
* KPI calculation.
* Power BI dashboard development.
* Data visualization.

### Analytical Skills

* Customer behavior analysis.
* Purchasing pattern investigation.
* Segment comparisons.
* Data quality assessment.
* Analytical problem-solving.
* Business-focused reporting.
* Communicating findings clearly.

## 🚀 Future Improvements

Potential improvements include:

* Add advanced SQL queries using CTEs and window functions.
* Develop additional Power BI measures.
* Improve dashboard interactivity.
* Add more detailed customer segmentation.
* Automate repeatable data preparation steps.
* Include a data dictionary.
* Document validated findings and recommendations.
* Add reproducible setup instructions.

These improvements can be added as the project develops.

## 💻 How to Explore This Project

1. Clone or download the repository.
2. Read this README to understand the project.
3. Open the Python notebook in Jupyter Notebook or a compatible environment.
4. Run the SQL scripts using a compatible database and the correct table schema.
5. Open the `.pbix` report in Power BI Desktop if included.
6. Review the dashboard screenshots and documented findings.

## 👨‍💻 About the Author

**Mohammed Azhan**
Aspiring Data Analyst

Interested in analyzing data and developing meaningful business insights using Python, SQL, Microsoft Excel, and Power BI.

### Technical Skills

* Microsoft Excel
* SQL
* Python
* Power BI
* Data Cleaning
* Exploratory Data Analysis
* Data Visualization

### Connect With Me

* **GitHub:** https://github.com/azhan-12
* **LinkedIn:** https://www.linkedin.com/in/mohammed-azhan-82078a348/

---

⭐ If you find this project useful, consider giving the repository a star.

Thank you for visiting my Customer Behavior Analysis project!
