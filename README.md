# Customer Shopping Behavior Analysis

An end-to-end retail customer analytics project using Python, PostgreSQL, and Power BI. The project examines customer demographics, purchasing patterns, product preferences, discount usage, shipping choices, and subscription behavior.

## Business problem
A retail company wants to understand shopping behavior to improve sales, customer satisfaction, customer engagement, and long-term loyalty. This project uses customer shopping data to identify trends and support marketing and product decisions.

## Project deliverables
- **Python:** Data loading, exploration, cleaning, missing-value treatment, feature engineering, and PostgreSQL integration (see the analysis report).
- **SQL / PostgreSQL:** Ten business questions and queries in `sql/customer_behavior_analysis.sql`.
- **Power BI:** Interactive customer behavior dashboard in `power_bi/customer_behavior_dashboard.pbix`.
- **Reports:** Business problem statement and analysis report in `reports/`.
- **Dataset:** Original CSV in `data/`.

## Dataset
- 3,900 rows
- 18 columns
- 37 missing values in `Review Rating`
- 0 duplicate rows found in the supplied CSV

Main fields include customer ID, age, gender, item purchased, category, purchase amount, location, size, color, season, review rating, subscription status, shipping type, discount applied, promo code used, previous purchases, payment method, and purchase frequency.

## SQL analysis questions
1. Total revenue by gender.
2. Discount users whose purchase amount is at least the overall average.
3. Top five products by average review rating.
4. Average purchase amount by Standard vs Express shipping.
5. Subscriber vs non-subscriber transaction count, average spend, and revenue.
6. Five products with the highest discount-use rate.
7. New, Returning, and Loyal customer segmentation using previous purchases.
8. Top three purchased items within each category.
9. Subscription status among repeat buyers with more than five previous purchases.
10. Revenue contribution by age group.

## Key findings documented in the report
- Revenue by gender: Female = 75,191; Male = 157,890.
- Average purchase amount: Standard shipping = 58.46; Express shipping = 60.48.
- Subscribers: average spend = 59.49 and total revenue = 62,645.
- Non-subscribers: average spend = 59.87 and total revenue = 170,436.
- Customer segments: Loyal = 3,116; Returning = 701; New = 83.
- Top five products by discount rate: Hat, Sneakers, Coat, Sweater, and Pants.
- Average purchase amount across the dataset is approximately $59.76; average review rating is approximately 3.75.

These are descriptive findings from this dataset and should not be interpreted as proof of causation.

## How to use
1. Create a PostgreSQL database and import `data/customer_shopping_behavior.csv` into a table named `customer`.
2. Ensure column names are snake_case, matching the SQL file (for example, `purchase_amount`, `item_purchased`, `review_rating`, `previous_purchases`, `age_group`).
3. Run `sql/customer_behavior_analysis.sql` in PostgreSQL.
4. Open the Power BI file using Power BI Desktop. If prompted, reconnect it to your local data source.
5. Read the project report in `reports/` for methodology, screenshots, and recommendations.

## Repository structure
```text
customer-behavior-analysis/
├── data/
│   └── customer_shopping_behavior.csv
├── sql/
│   └── customer_behavior_analysis.sql
├── power_bi/
│   └── customer_behavior_dashboard.pbix
├── 
|── business_problem_document.pdf
|── customer_shopping_behavior_analysis.pdf
└── README.md
```

## Business recommendations in the report
- Promote subscription benefits to encourage sign-ups.
- Reward repeat buyers through customer loyalty programs.
- Review discount policy while considering profitability and margins.
- Highlight highly rated and popular products in campaigns.
- Use age-group and shipping-preference patterns to inform targeted marketing.

## Notes and limitations
- The supplied CSV has no transaction date. Avoid monthly or year-over-year trend claims unless a valid date field is added.
- `purchase_frequency_days` should be documented carefully: the supplied CSV contains a frequency category, not a transaction date.
- The SQL script uses PostgreSQL syntax (`::numeric`, window functions).
- The Power BI `.pbix` is included as supplied. Refresh may require updating the source path.
- Check the dataset's original license and attribution requirements before redistributing the CSV publicly.
- The Python source `.py` file was not among the uploaded files; the Python workflow is described in the supplied PDF report.

