# Cleaning Log

## Issues Found
- Missing values in region, ship mode, and discount columns.
- Negative discount values.
- Discount values above the allowed range.
- Cancelled, failed payment, and refunded orders requiring special handling.
- Records where the ship date was earlier than the order date.

## Cleaning Actions Performed
- Replaced missing region values with "Unknown".
- Replaced missing ship mode values with "Unknown".
- Replaced missing discount values with 0 when other sales fields were valid.
- Standardized text fields and date formats.
- Identified and handled duplicate records.
- Created calculated columns for analysis and validation.

## Business Rules Applied
- Missing region values were filled with "Unknown" and documented in the data quality report.
- Missing ship mode values were filled with "Unknown" and documented in the data quality report.
- Missing discount values were treated as 0 only when other sales fields were valid.
- Negative discount values were flagged as Invalid.
- Discounts above the allowed range were flagged as Invalid.
- Cancelled orders were retained but excluded from the final completed sales summary.
- Failed payment orders were retained but excluded from the final completed sales summary.
- Refunded orders were retained and summarized separately.
- Records with ship dates earlier than order dates were flagged as Invalid Shipping Records.

## Assumptions Made
- Missing discount values were considered as 0 only when quantity, unit price, and cost information were available.
- "Unknown" was used as the standard replacement for missing categorical values.

## Records Removed
- Only exact duplicate rows were removed after verification.

## Records Flagged
- Duplicate order IDs with conflicting information were flagged for manual review.
- Invalid discounts and invalid shipping records were flagged for quality checks.

## Limitations
- Flagged records may require manual verification before business decisions are made.
- The cleaning process is based only on the provided dataset and business rules. 


| **Field / Business Rule**    | **Action Taken**                                | **Count** |
| ---------------------------- | ----------------------------------------------- | --------: |
| Region                       | Filled missing values with **"Unknown"**        |    **25** |
| Ship Mode                    | Filled missing values with **"Unknown"**        |    **21** |
| Discount                     | Replaced missing values with **0** (when valid) |    **18** |
| Negative Discount            | Flagged as **Invalid**                          |    **15** |
| Discount Above Allowed Range | Flagged as **Invalid**                          |    **15** |
| Cancelled Orders             | Excluded from the final completed sales summary |   **145** |
| Failed Payments              | Excluded from the final completed sales summary |    **69** |
| Refunded Orders              | Summarized separately for analysis              |    **71** |
| Ship Date Before Order Date  | Flagged as **Invalid Shipping Record**          |    **91** |

