Overview
A retail business records every customer, product, order, line item, payment, and review in an operational database, but the raw tables answer nothing on their own. This project builds and documents a complete, verified SQL answer set for the store, from single-table retrieval to set operations.

The dataset has 2,131 rows across six tables: 30 customers, 50 products, 400 orders, 1,201 order items, 400 payments, and 50 product reviews, covering one year of trading.

Problem
Marketing has no clean contact list, merchandising cannot see which categories perform, finance cannot break settlement down by payment method, and inventory cannot separate what sells from what sits. One question can span three tables, the data is stored per line item while questions are asked per order, customer, category, and day, and “never sold” or “never ordered” means reasoning about rows that are not there.

My role
Solo SQL mini project from Data Analytics with GenAI. I wrote the script and its 45-page documentation.

Process
Schema: create the retail_store database and its six tables, with keys and constraints, using CREATE TABLE IF NOT EXISTS.
Load: insert the supplied dataset with INSERT IGNORE, so the script can be re-run without duplicate-key errors.
Verify: one UNION ALL query reports the row count of all six tables before any analysis begins.
Query: answer the 42 questions in six levels, each with a plain-language explanation and its expected result.
Approach and methods
Every query is written to be readable first: keywords on their own lines, short table aliases, and an explicit alias for every calculated column.

    SELECT, WHERE, ORDER BY
    Aggregations and GROUP BY
    INNER, LEFT, and RIGHT JOIN
    Scalar and correlated subqueries
    EXISTS and NOT EXISTS
    UNION
    
Key features

One script that builds the database, loads the data, verifies the load, and answers every question in order
42 queries across six levels: basics, filtering and formatting, aggregations, joins, subqueries, and set operations
An expected result for every query, including four that correctly return no rows
INTERSECT, which the MySQL setup does not support, replaced with an INNER JOIN and DISTINCT
Key findings
Revenue of ₹69,60,973.66 across 400 orders, an average order value of ₹17,402.43
All 30 customers have ordered and all 50 products have sold: no dormant segment and no dead stock in this dataset
Electronics leads on units sold (687), but Clothing has the highest average item price (₹3,473.17)
Debit Card settles the largest value (₹19,30,577.88) and UPI the smallest (₹16,17,408.78); no single method dominates
194 of 400 orders exceed the placing customer’s own average order value
23 of 30 customers have both ordered and reviewed a product

<img width="1200" height="1588" alt="image" src="https://github.com/user-attachments/assets/1efefa60-ba77-4593-890d-8e3b8e544bbd" />
