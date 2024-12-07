# Oasis_Task1
# Retail Sales Dataset Analysis

This README summarizes the key steps and findings from the analysis of the retail sales dataset. 

## Setup and Libraries Used
- Libraries: `pandas`, `numpy`, `matplotlib` and `seaborn`.
- Environment: Used Jupyter Notebook for exploratory and visual analysis.

## Data Overview
- Dataset: `retail_sales_dataset.csv`
- Shape: Contains rows and columns with details of sales transactions.
- Key columns: `Date`, `Product Category`, `Quantity`, `Price per Unit`, `Total Amount`, and `Gender`.
### Key Initial Insights
1. **Missing Values:**
   - Checked using `df.isnull().sum()`.
2. **Data Types:**
   - Columns inspected with `df.info()` and `df.dtypes`.
   - Converted `Date` to datetime format.

## Key Statistics
1. **Central Tendency & Spread:**
   - Mean age of customers: `df['Age'].mean()`
   - Median quantity purchased: `df['Quantity'].median()`
   - Standard deviation of price per unit: `df['Price per Unit'].std()`
   - Descriptive stats: `df.describe()`
2. **Totals:**
   - Total quantity sold: `df['Quantity'].sum()`
   - Total revenue generated: `df['Total Amount'].sum()`.

## Exploratory Data Analysis (EDA)
1. **Value Counts:**
   - Frequency of `Product Category`: 
     ```python
     df['Product Category'].value_counts()
     ```
2. **Visualizations:**
   - **Pie Chart** for product category distribution.
   - **Bar Charts** using `seaborn` for `Gender` and `Quantity`.
   - **Line Plot** to show `Total Amount` trends over time.
   - **Histogram** of `Price per Unit` for distribution.

## Revenue Analysis
1. **Revenue Calculation:**
   - Created a new column `Total Amount = Quantity * Price per Unit`.
   - Summed up total revenue: `Total Revenue Generated: $<amount>`.

2. **Trends Over Time:**
   - Analyzed yearly, quarterly, and monthly sales using:
     ```python
     total_amount_by_year = df.groupby('Year')['Total Amount'].sum()
     total_amount_by_quarter = df.groupby(['Year', 'Quarter'])['Total Amount'].sum()
     total_amount_by_month = df.groupby(['Year', 'Month'])['Total Amount'].sum()
     ```
   - Visualized using bar charts for yearly, quarterly, and monthly changes.

## Time Series Analysis
1. **Date Extraction:**
   - Extracted `Year`, `Quarter`, and `Month` from the `Date` column for time-series analysis.
2. **Average Price Over Time:**
   - Grouped by `Date` to calculate mean `Price per Unit` over time.

## Product Category Insights
1. Grouped and summed `Quantity` by `Product Category`.
2. Sorted categories by total sales for comparative insights.

### Key Findings:
1. **Top Categories:** Clothing, Electronics, and Beauty are among the most purchased product categories.
2. **Revenue Trends:** Significant increases in revenue during specific months and quarters.
3. **Price Distribution:** Most unit prices cluster around the lower end, with a few high-value products.

## Visualizations
- Included plots for frequency distributions, time-series trends, and category-wise summaries to provide insights.

## plot Heatmap:
- Compute correlation matrix for numerical columns.

## Thank You! 🎉
This analysis provided insights into customer behavior, product performance, and revenue trends, enabling data-driven decision-making for business strategies.
