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
-- Query to compare Credit vs Debit transaction volumes
SELECT 
    transaction_type, 
    COUNT(*) AS transaction_count,
    SUM(amount) AS total_amount
FROM transactions
GROUP BY transaction_type;

-- Query to identify top customers by transaction value
SELECT 
    c.customer_name,
    SUM(t.amount) AS total_spent
FROM customers c
JOIN transactions t ON c.customer_id = t.customer_id
GROUP BY c.customer_name
ORDER BY total_spent DESC;

Recommendations
Offer loyalty rewards or special banking benefits to high-value customers like Aisha and Seun to improve customer retention.

Improve customer engagement by sending transaction alerts and personalised financial tips to customers.

Encourage customers to use digital banking channels such as mobile apps and online transfers for faster and easier transactions.
