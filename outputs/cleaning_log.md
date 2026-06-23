# Data Cleaning Log

# 1. List of Issues Found

The raw dataset contained multiple data quality issues, including:

- Inconsistent text formatting
- Extra leading and trailing spaces
- Mixed date formats
- Missing region values
- Missing ship mode values
- Missing discount values
- Negative discount values
- Discount values above the allowed range
- Duplicate order IDs
- Exact duplicate records
- Ship dates earlier than order dates
- Cancelled, refunded and failed order records

---

# 2. Cleaning Actions Performed

The following cleaning steps were performed on the dataset:

- Used TRIM() to remove extra spaces.
- Used PROPER() to standardize text formatting.
- Standardized region, category, ship mode and other text fields.
- Converted different date formats into a single consistent format (dd-mmm-yyyy).
- Filled missing region values with "Unknown".
- Filled missing ship mode values with "Unknown".
- Replaced missing discount values with 0 only when other sales fields were valid.
- Identified duplicate order IDs.
- Removed only exact duplicate records.
- Flagged conflicting duplicate records for manual review.
- Created calculated columns for sales, profit, profit margin, shipping delay, month and year.

---

# 3. Business Rules Applied

- Missing Region → Filled with "Unknown".
- Missing Ship Mode → Filled with "Unknown".
- Missing Discount → Replaced with 0 when other sales fields were valid.
- Negative Discount → Flagged as Invalid.
- Discount above allowed range → Flagged as Invalid.
- Cancelled Orders → Excluded from completed sales summary.
- Failed Payments → Excluded from completed sales summary.
- Refunded Orders → Summarized separately.
- Ship Date before Order Date → Flagged as Invalid Shipping Record.

---

# 4. Assumptions Made

- Unknown values were retained instead of deleting records.
- Maximum valid discount considered was 50%.
- Missing discounts were treated as 0 only when quantity, unit price and cost values were available.
- Cancelled and failed orders were kept in the dataset for reporting purposes but excluded from completed sales summaries.

---

# 5. Records Removed

- Exact duplicate rows were removed after verification.
- No conflicting duplicate order IDs were deleted automatically.

---

# 6. Records Flagged

The following records were flagged for review:

- Duplicate order IDs with conflicting information
- Negative discount values
- Discount values above allowed range
- Ship dates earlier than order dates
- Missing mandatory information
- Failed payment records
- Cancelled orders
- Refunded orders

---

# 7. Limitations

- Business rules were applied based only on the available dataset.
- Some conflicting duplicate records may require manual verification.
- Invalid values were flagged instead of corrected when sufficient information was not available.
- No external data source was used for validation.

---

# Conclusion

The cleaned dataset is standardized, validated and ready for business analysis. All identified issues have either been corrected or clearly flagged for further review while preserving the integrity of the original data.
