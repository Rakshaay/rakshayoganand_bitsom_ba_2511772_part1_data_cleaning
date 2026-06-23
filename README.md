# Business Data Cleaning, Validation & Excel Reporting

## Problem Summary
You are working as a business analyst for a retail company.

The company has exported order-level sales data from multiple internal systems. The raw dataset contains issues such as inconsistent text formatting, date format problems, duplicate records, missing values, invalid discounts, calculation mismatches, and order status inconsistencies.

Your manager wants a clean, validated, analysis-ready version of the data along with summary reports that can be used for business review.

Your task is to clean the dataset, validate the business rules, document all issues found, and create summary reports using Excel.




## Dataset Description

The dataset contains order-level retail sales information including:

- Order ID
- Order Date
- Ship Date
- Customer Details
- Region, State and City
- Category and Sub-Category
- Ship Mode
- Quantity
- Unit Price
- Cost
- Discount
- Sales
- Profit
- Payment Status
- Order Status

The original dataset was preserved as `raw_orders.xlsx`, and all cleaning operations were performed on `cleaned_orders.xlsx`.

---

## Tools Used

- Microsoft Excel
- Excel Formulas (TRIM, PROPER, IF, IFERROR, COUNTIF, DATEVALUE, TEXT, MONTH, YEAR)
- Pivot Tables
- Conditional Formatting
- Find & Replace
- Flash Fill

---

## Cleaning Steps Performed

The following data cleaning steps were completed:

- Removed extra spaces from text fields
- Standardized text using proper case
- Standardized category and ship mode names
- Converted different date formats into a consistent format
- Filled missing Region values with "Unknown"
- Filled missing Ship Mode values with "Unknown"
- Replaced missing Discount values with 0 where applicable
- Identified duplicate order IDs
- Removed exact duplicate rows
- Flagged conflicting duplicate records
- Created calculated columns for sales, profit, profit margin, shipping delay, month and year

---

## Business Rules Applied

- Missing Region → Filled as "Unknown"
- Missing Ship Mode → Filled as "Unknown"
- Missing Discount → Treated as 0 when other sales fields were valid
- Negative Discount → Flagged as Invalid
- Discount above allowed range → Flagged as Invalid
- Cancelled Orders → Excluded from completed sales summary
- Failed Payments → Excluded from completed sales summary
- Refunded Orders → Reported separately
- Ship Date before Order Date → Flagged as Invalid Shipping Record

---

## Summary of Data Quality Issues Found

The following issues were identified and handled:

| Issue | Action |
|---------|--------------------------------|
| Missing Region | Filled with "Unknown" |
| Missing Ship Mode | Filled with "Unknown" |
| Missing Discount | Replaced with 0 where valid |
| Negative Discount | Flagged |
| Discount Above Limit | Flagged |
| Duplicate Order IDs | Identified and reviewed |
| Exact Duplicate Records | Removed |
| Invalid Date Sequence | Flagged |
| Cancelled Orders | Excluded from completed sales summary |
| Failed Payments | Excluded from completed sales summary |
| Refunded Orders | Summarized separately |

---

## Summary of Final Pivot Reports

The following Pivot Tables were created:

1. Sales and Profit by Region
2. Sales and Profit by Category & Sub-Category
3. Order Count by Ship Mode
4. Average Profit Margin by Customer Segment
5. Refunded, Cancelled and Failed Orders by Region
6. Monthly Sales Trend

Sorting and filtering were applied to selected Pivot Tables for better analysis.

---

## Key Business Insights

- South region generated the highest sales.
- Unknown region contributed the least sales.
- Office Supplies and Technology categories contributed significantly to revenue.
- Standard and First Class shipping modes handled most orders.
- Cancelled and failed payment orders reduced completed sales.
- Invalid discounts and duplicate records affected overall data quality.
- Monthly sales trends can be used for future business planning.

---

## Assumptions and Limitations

### Assumptions

- Missing Region and Ship Mode values were replaced with "Unknown".
- Missing Discount values were treated as 0 only when other sales fields were valid.
- Maximum valid discount considered was 50%.
- Cancelled and failed orders were retained for reporting but excluded from completed sales summaries.

### Limitations

- Some duplicate order IDs require manual verification.
- Invalid values without sufficient information were flagged instead of corrected.
- No external data source was used for validation.

---

## Screenshots Included

The repository contains screenshots of:

- Raw Dataset Preview
- Cleaned Dataset Preview
- Pivot Summary 1
- Pivot Summary 2

These screenshots demonstrate the data cleaning process and the final analysis reports.
<img width="1894" height="707" alt="image" src="https://github.com/user-attachments/assets/2285230c-418c-400c-a960-2b5a259941e5" />
## Raw_Order




---

## Repository Structure

```
part1_data_cleaning/
│
├── data/
│   ├── raw_orders.xlsx
│   └── cleaned_orders.xlsx
│
├── outputs/
│   ├── data_quality_report.xlsx
│   ├── pivot_summary.xlsx
│   └── cleaning_log.md
│
├── screenshots/
│   ├── raw_data_preview.png
│   ├── cleaned_data_preview.png
│   ├── pivot_summary_1.png
│   └── pivot_summary_2.png
│
└── README.md
```

---

## Conclusion

The raw retail dataset was successfully cleaned, validated, and transformed into an analysis-ready dataset. Data quality issues were documented, business rules were applied consistently, and Pivot Table reports were created to support business decision-making.
