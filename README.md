DATA CLEANING AND PREPERATION (E-Commerce Order Dataset)

OVERVIEW:
This project is Part 1 of a data analytics internship series at DecodeLabs. The goal was to take a raw e-commerce order dataset and prepare it for analysis by identifying and resolving data quality issues — missing values, duplicates, and formatting inconsistencies.

DATASET
1. Source: Provided e-commerce order dataset (Dataset_for_Data_Analytics.xlsx)
2. Size: 1,200 rows × 14 columns
3. Fields include: OrderID, Date, CustomerID, Product, Quantity, UnitPrice, ShippingAddress, PaymentMethod, OrderStatus, TrackingNumber, ItemsInCart, CouponCode, ReferralSource, TotalPrice

Tools Used
- Microsoft Excel (formulas, conditional formatting, and manual QA checks)

PROCESS:
1. Missing Values
- Used conditional formatting and `COUNTBLANK()` to audit every column for blanks.
- Found 309 blank values (25.75%) in the `CouponCode` column.
- Determined these represented customers who did not use a coupon, rather than lost data, and replaced blanks with `"No Coupon"` to make the missingness explicit instead of ambiguous.

2. Duplicates
- Checked all 1,200 `OrderID` values for repeats using a running `COUNTIF()` check.
- Result: 0 duplicate orders found.

3. Formatting
- Verified the `Date` column was stored as true dates (not text).
- Verified numeric columns (`Quantity`, `UnitPrice`, `TotalPrice`) were stored as true numbers.
- Checked all text columns for hidden leading/trailing whitespace using `TRIM()`.
- Result: no formatting corrections were needed — all fields were already clean.

4. Data Integrity Check
- Cross-checked that `TotalPrice = Quantity × UnitPrice` for every row.
- Result: 0 mismatches across all 1,200 rows.

KEY FINDINGS
- The dataset required minimal structural cleaning — its main issue was a single column of ambiguous missing values, which was resolved with a clear labeling decision rather than dropping data.
- Verifying "clean" data (duplicates, formats, calculations) was as important a step as fixing the one real issue found, since it confirms the dataset is trustworthy for the next phase of analysis.

REPOSITORY CONTENTS
| File | Description |---|---| `Dataset_Cleaned.xlsx` | Workbook containing Raw Data, Cleaned Data, and Data Quality Summary sheets |

NEXT STEPS
This cleaned dataset feeds into Project 2: Exploratory Data Analysis, which covers descriptive statistics, trend analysis, and outlier detection.

Part of a Data Analytics Internship at DecodeLabs.
