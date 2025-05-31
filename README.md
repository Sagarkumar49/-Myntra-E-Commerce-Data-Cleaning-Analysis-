# 📊 Myntra E-Commerce Data Cleaning & Analysis

A comprehensive data standardization and business insights project using Excel

## 📌 Business Context

- Myntra, a leading Indian fashion e-commerce platform, requires clean and consistent product data to:

- Ensure accurate pricing displays for customers

- Optimize discount strategies

- Maintain inventory reliability
This project addresses data quality issues in their product catalog through systematic cleaning and analysis.

## 🛠️ Technical Approach

1. Data Cleaning & Standardization
Tools Used: Excel Formulas, Data Tools
Key Operations:

| Task                          | Method                                                                 | Outcome                     |
|-------------------------------|-----------------------------------------------------------------------|-----------------------------|
| **Duplicate Removal**         | `Data Tab > Remove Duplicates`                                        | Zero duplicates found       |
| **Discount Format Standardization** | `Find & Replace` + Formula: `=IF(ISNUMBER(SEARCH("Rs",L2)),L2,L2*13)` | Unified "500 OFF" format    |
| **Null Value Handling**       | Filled using category averages: `=IF(AND([@DP]="",[@DO]=""),AVERAGEIF(...))` | 100% complete price data |
| **Size Options**              | Replaced blanks with `"Not Available"`                                | Eliminated missing entries  |

2. Advanced Analysis
Key Formulas:

```excel
=AVERAGEIF(Ratings, ">4", OriginalPrice)  → ₹1,849 (Avg. premium product price)  
=COUNTIF(DiscountOffer, ">50%")          → 33,155 high-discount products  
=IF([@DiscountOffer]>50%, "High", "Low") → Discount tier labeling
```
3. Lookup Operations
```excel
=VLOOKUP(11226634, Table2, {2,10,15}, FALSE)  → Retrieved brand/price/rating  
=INDEX(Table2[DiscountPrice], MATCH(6744434, Table2[Product_id], 0)) → ₹599  
```
## 📈 Key Insights

1. Pricing Strategy:

  - Products with ratings >4 averaged 46% higher prices than others.

  - Over 33K products had discounts >50%, indicating aggressive sales tactics.

2. Data Quality Impact:

  - Standardized discounts reduced customer confusion in price displays.

  - Category-average imputation improved inventory valuation accuracy.

## 📂 Dataset Overview

Columns Processed:

- Product_id (Unique identifier)

- OriginalPrice (Pre-discount value)

- DiscountPrice (Cleaned using null-handling logic)

- DiscountOffer (Standardized to % or fixed amount)

- SizeOption (Nulls → "Not Available")

- Ratings (Used for premium product analysis)

Sample Data Snippet:

| Product_id	| OriginalPrice	| DiscountOffer	| SizeOption  |
|-------------|---------------|---------------|-------------|
| 11226634	  | ₹1,999	      | 55% OFF	      | S, M, L     |
| 6744434	    | ₹1,299	      |₹599	          | Not Available |

## 🚀 Project Impact

- Business: Enabled accurate discount tracking and pricing strategy adjustments.

- Technical: Demonstrated Excel's capability for e-commerce data wrangling.

- Portfolio: Showcases end-to-end data cleaning → analysis workflow.

## 📚 Lessons Learned

1. Data Validation Matters: Inconsistent discount formats required 3-step standardization.

2. Context-Aware Imputation: Category averages better than global means for null values.

3. Scalability Limits: Excel becomes cumbersome beyond ~100K rows (Pandas recommended next).

## 🔗 Appendix

Dataset Source: [Attach sanitized sample if possible]

Visuals:
Data Cleaning Flow

## 📜 License 
[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)  
Copyright © 2025 [Sagarkumar49](https://github.com/Sagarkumar49)
