# Bank-Transaction-Analysis-Using-SQL
This report analyses customer transactions recorded in April 2024 using SQL queries.  The dataset contains 8 customers, Savings and Current account types, and 18 transactions with a total value of ₦138,000. The analysis includes data retrieval, filtering, sorting, aggregation, grouping, JOIN operations, and subqueries. 
# Customer Transaction Analysis using SQL

The analysis includes data retrieval, filtering, sorting, aggregation, grouping, JOIN operations, and subqueries.

---

## Key Insights
1. A total of 18 transactions worth ₦138,000 were recorded, with an average transaction value of ₦7,667.
2. Credit and Debit transactions were almost equal, showing balanced money inflow and outflow in customer accounts.
3. Aisha and Seun recorded the highest transaction totals, making them the bank’s most active customers.

---


### 1. Data Retrieval & Aggregation
```sql
-- Query to get total transaction volume, total value, and average value
SELECT 
    COUNT(*) AS total_transactions,
    SUM(amount) AS total_value,
    AVG(amount) AS average_transaction_value
FROM transactions;
