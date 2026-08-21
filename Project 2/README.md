
EXPLORATORY DATA ANALYSIS (EDA) — E-Commerce Order Dataset

OVERVIEW
This project is Part 2 of a data analytics internship series at DecodeLabs. Building on the cleaned dataset from Project 1, the goal was to explore the data to understand its underlying patterns, trends, and distributions — using descriptive statistics, trend analysis, and outlier detection.

DATASET
- Source: Cleaned dataset from Project 1 (`Cleaned Data` sheet, `Dataset_Cleaned.xlsx`)
- Size: 1,200 rows × 14 columns
- Key numeric fields analyzed:** Quantity, UnitPrice, TotalPrice

TOOL USED
- Microsoft Excel (formulas: `AVERAGE`, `MEDIAN`, `COUNT`, `SUMPRODUCT`, `SUMIF`, `COUNTIF`, `QUARTILE`)

PROCESS
1. Basic Statistics
- Calculated Mean, Median, Count, Min, Max, and Standard Deviation for `TotalPrice`, `Quantity`, and `UnitPrice`.
- `TotalPrice`: Mean ₦1,053.97, Median ₦823.62
- `Quantity`: Mean 2.95, Median 3
- `UnitPrice`: Mean ₦356.41, Median ₦364.21

2. Trend Analysis
- By month: Built a monthly breakdown of total sales, order count, and average order value (aggregated across all years in the dataset). June recorded the highest total sales (₦170,616.13); September recorded the lowest (₦69,321.65).
- By product: Built the same breakdown across all 7 product categories. `Chair` and `Printer` generated the highest total sales; `Phone` was the lowest performer.

3. Outlier Detection
- Applied the **IQR (Interquartile Range) method to `TotalPrice`:
  - Q1 = ₦410.52, Q3 = ₦1,578.48, IQR = ₦1,167.96
  - Upper bound = ₦3,330.41, Lower bound = -₦1,341.41 (no realistic lower cutoff)
- Result: 8 orders identified as high-value outliers; 0 orders below the lower bound.

4. Key Findings
- `TotalPrice` is right-skewed: the mean sits well above the median, meaning a small number of high-value orders pull the average upward relative to what a typical order actually costs.
- Both `Quantity` and `UnitPrice` are individually well-balanced (mean ≈ median for each), which means the skew in `TotalPrice` isn't driven by either factor alone — it comes from certain orders combining above-average quantity and above-average price at the same time.
- Sales show a clear monthly pattern, peaking in June and dipping in September — worth further investigation into whether this reflects a seasonal trend or is specific to this dataset.
- The IQR method flagged 8 orders as statistically unusual, all on the high side, giving a defensible, non-arbitrary way to identify orders worth a closer look.

REPOSITORY CONTENT
| File | Description |---|--- | `Dataset_Cleaned.xlsx` | Workbook containing Raw Data, Cleaned Data, Data Quality Summary, and EDA sheets |

NEXT STEPS
This analysis feeds into Project 3: SQL Data Analysis, translating these same questions (filtering, grouping, aggregating) into structured SQL queries.


Part of a Data Analytics Internship at DecodeLabs.
