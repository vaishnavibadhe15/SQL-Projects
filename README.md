# Pizza Sales Analysis using SQL (MySQL)

A SQL project that analyses pizza sales data to answer 13 business questions about revenue, best-selling products, customer ordering patterns, and sales trends. It uses multi-table joins, aggregations, subqueries, and window functions in MySQL.

---

## Business Questions Answered

The queries are grouped by difficulty.

### Basic

| # | Question | SQL concepts |
|---|----------|--------------|
| 1 | What is the total number of orders placed? | `COUNT` |
| 2 | What is the total revenue generated from pizza sales? | `JOIN`, `SUM`, `ROUND` |
| 3 | Which is the highest-priced pizza? | `JOIN`, `ORDER BY`, `LIMIT` |
| 4 | Which pizza size is ordered most often? | `JOIN`, `GROUP BY`, `COUNT` |

### Intermediate

| # | Question | SQL concepts |
|---|----------|--------------|
| 5 | What are the top 5 most ordered pizza types and their quantities? | 3-table `JOIN`, `GROUP BY`, `SUM`, `LIMIT` |
| 6 | What is the total quantity ordered for each pizza category? | 3-table `JOIN`, `GROUP BY`, `SUM` |
| 7 | How are orders distributed by hour of the day? | `HOUR()`, `GROUP BY` |
| 8 | How many pizza types are there in each category? | `GROUP BY`, `COUNT` |
| 9 | What is the average number of pizzas ordered per day? | Subquery in `FROM`, `AVG`, `ROUND` |

### Advanced

| # | Question | SQL concepts |
|---|----------|--------------|
| 10 | What are the top 3 pizza types by revenue? | Multi-table `JOIN`, `SUM`, `ORDER BY`, `LIMIT` |
| 11 | What percentage of total revenue does each pizza category contribute? | Scalar subquery, percentage calculation |
| 12 | How does cumulative revenue grow over time? | Window function `SUM() OVER (ORDER BY ...)` |
| 13 | What are the top 3 pizza types by revenue within each category? | `RANK() OVER (PARTITION BY ...)`, nested subqueries |

---

## Database Schema

The project uses a database named `pizzahut` with four tables:

| Table | Description |
|-------|-------------|
| `orders` | One row per order: `order_id`, `order_date`, `order_time` |
| `order_details` | Line items of each order: `orders_details`, `order_id`, `pizza_id`, `quantity` |
| `pizzas` | Each pizza variant: `pizza_id`, `pizza_type_id`, `size`, `price` |
| `pizza_types` | Pizza names and categories: `pizza_type_id`, `name`, `category` |

**Relationships**

```
orders.order_id          ->  order_details.order_id
order_details.pizza_id   ->  pizzas.pizza_id
pizzas.pizza_type_id     ->  pizza_types.pizza_type_id
```

> Add an ER diagram screenshot here (MySQL Workbench: Database -> Reverse Engineer): `images/er_diagram.png`

---

## Key Insights

> Run the queries and replace these with your real results. Recruiters read this section first.

1. **Total orders / revenue:** [e.g., "X orders generated $Y in revenue."]
2. **Best sellers:** [e.g., "The top 5 pizza types by quantity are ..."]
3. **Peak hours:** [e.g., "Orders peak around 12-1 PM and 5-7 PM."]
4. **Category and size trends:** [e.g., "Classic is the top category by quantity; size L is ordered most."]
5. **Revenue drivers:** [e.g., "The top 3 pizzas by revenue are ..., and category X contributes Y% of total revenue."]
6. **Recommendation:** [e.g., "Run lunch and dinner promotions during peak hours."]

---

## Sample Output

> Add screenshots of a few query results to the `images/` folder and link them here.

![Top 5 pizza types](images/top5_pizza_types.png)
![Cumulative revenue](images/cumulative_revenue.png)

---

## How to Run

1. Install **MySQL** and **MySQL Workbench**.
2. Create the database:
   ```sql
   CREATE DATABASE pizzahut;
   USE pizzahut;
   ```
3. Import the `pizzas` and `pizza_types` CSV files using the Table Data Import Wizard in Workbench.
4. Run the `CREATE TABLE` statements for `orders` and `order_details` from `pizza_sales_sql.sql`, then import their CSV files.
5. Run the queries in `pizza_sales_sql.sql` one by one.

---

## Repository Structure

```
├── pizza_sales_sql.sql     # Table creation + 13 analysis queries
├── README.md
├── data/                   # CSV files (optional)
└── images/                 # ER diagram and query result screenshots
```

---

## Tools

- MySQL
- MySQL Workbench

---

## Author

**Vaishnavi Badhe**

Data Analyst| Python, SQL, Power BI, Machine Learning
Mumbai, India

