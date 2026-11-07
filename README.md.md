# Data Engineering Project

Portfolio projects built as part of a structured Data Engineering interview-prep program, focused on real-world data cleaning, ETL pipeline design, and SQL analytics — the core skills used in Data Engineering roles.

---

## Project 2: SQL-Heavy Analytics
**Tools:** SQL (SQLite), Python (for database setup)

A set of analytical SQL queries solving real business questions against a relational database of customers, products, and orders.

**What it covers:**
- Multi-table joins with aggregation (total spend per customer)
- Window functions — `RANK()`, `DENSE_RANK()`, `ROW_NUMBER()` — to rank customers within each region, with correct handling of tied values
- Common Table Expressions (CTEs) to filter on window function results (not possible directly in a single `WHERE` clause)
- `LAG()` for month-over-month revenue comparison per product
- A security-focused SQL **View** demonstrating column-level data access control — exposing only non-sensitive fields to a hypothetical downstream team

**Key design decision:** Window function results can't be filtered directly in the same query level as a `WHERE` clause, since window functions execute after `WHERE`. Queries were structured using layered CTEs to calculate, then rank, then filter — a pattern directly applicable to real analytics and interview questions (e.g., "find the top N per group").

---