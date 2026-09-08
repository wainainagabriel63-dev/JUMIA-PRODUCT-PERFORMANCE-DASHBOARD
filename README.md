# Jumia Product Performance Dashboard

## Project Overview
A data driven analysis of Jumia product pricing, discounts and customer engagement which is built entirely in Excel from raw data cleaning to an interactive dashboard and business recommendations.

## Dataset
The dataset includes the following columns:
- Product: Name of the product
- Current Price: Selling price in KES
- Old Price: Original price before discount
- Discount: Percentage discount offered
- Review: Number of customer reviews
- Rating: Average customer rating (out of 5)

## Data Cleaning and Preparation
- Checked for and handled missing values in Review and Rating columns, labeling them as "Unknown" rather than replacing with 0, to avoid distorting analysis and correlations.
- Removed the "KSh" currency prefix from price columns using Find and Replace, allowing proper Currency formatting.
- Used TRIM() and CLEAN() functions to remove extra spaces and non-printable characters from text columns.
- Used AVERAGE() to resolve cells containing price ranges instead of single values.

## Data Enrichment
- Created a Discount Amount column using the formula: Old Price - Current Price.
- **Rating Category**: Poor / Average / Excellent, based on rating thresholds.
- **Discount Category**: Low / Medium / High Discount, based on percentage thresholds.
- **Price Category**: Low / Medium / High Price, based on quartiles (QUARTILE.INC) of Current Price.
- **Review Category**: Low / Medium / High Reviews, based on quartiles of Review count.
- **Engagement Category**: Weak / Average / Strong Engagement, combining review count quartiles with rating thresholds.

## Trend Analysis
Correlation analysis (using CORREL()) was conducted to explore relationships between key variables:
- Discount vs Review: -0.1368 (weak negative relationship)
- Rating vs Review: 0.0572 (negligible relationship)
- Price vs Rating: 0.1100 (weak positive relationship)

Additional analysis included identifying top-performing products by rating, review count, and discount, as well as flagging products with high discounts but low engagement.

## Dashboard
An interactive Excel dashboard was built including:
- KPI overview (total products, average price, average discount, average rating, total reviews)
- Top 10 products by rating, reviews, and discount
- Trend analysis charts (Discount vs Review, Rating vs Review, Price vs Rating)
- Product category breakdowns (Rating Category, Discount Category) using Pivot Charts
- Slicers for interactive filtering by Rating Category, Discount Category, and Price Category

## Key Findings
- Discount percentage has little to no meaningful influence on the number of reviews a product receives.
- Product rating is not strongly related to review count, suggesting review volume is driven by other factors.
- Price has only a weak positive relationship with rating, meaning higher prices do not reliably indicate higher quality perception.

## Business Recommendations
- Discounting alone should not be relied upon to drive customer engagement; sellers should invest in product visibility, quality descriptions, and customer experience.
- Price should not be used as the sole signal of product quality; moderately priced products can perform just as well as expensive ones.
- Sellers should focus on products with weak engagement to investigate and address underlying issues, regardless of their price or discount level.
- Encouraging more customers to leave reviews could help build stronger, more reliable product performance data going forward.

## Tools Used
- Microsoft Excel (PivotTables, PivotCharts, Slicers, Conditional Formatting, Formulas)
- Git and GitHub for version control and submission
