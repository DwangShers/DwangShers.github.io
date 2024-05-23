---
Title: DBS101 Flipped Class 9
categories: [DBS101, Flipped_Class9]
tags: [DBS101]
---

### Topic : Query Optumization

---

In this flipped class, firstly we were divided into four gorups and each two groups had similar topics to master on the topic.

After the group discussion, we were divided into two groups which were the trivia group. Then, we had to create questions on the two topics for the other group. So, this whole flipped class was a challenge between the two groups whereby it ended up with a simile on our face.

Through this flipped class, the main goal is to usderstand query optimization through materialised views and understand advanced topics in query optimisation.

---

### Query Optimization Through Materialised Views

Query optimization through materialized views is a technique used in databases to improve the performance of query processing.
A materialized view is a database object that contains the results of a query, and unlike a regular view, it stores the query result physically on disk. This can significantly speed up query performance by avoiding the need to recompute the results each time the query is executed.

#### How Materialized Views Work

1. Creation: A materialized view is created using a SQL query that defines the data it will contain. This query is executed once, and the result is stored in the database.

```sql CREATE MATERIALIZED VIEW sales_summary AS
SELECT product_id, SUM(quantity) AS total_quantity, SUM(price) AS total_revenue
FROM sales
GROUP BY product_id;
```

2. Storage: The result of the query is stored in a physical table in the database. This allows for quick access to the precomputed results.

3. Refresh: Materialized views can become stale as the underlying data changes. They can be refreshed periodically or on demand to ensure they reflect the latest data. Refreshing can be done completely (recomputing the entire view) or incrementally (updating only the changed parts).

#### Benefits of Using Materialized Views

1. Improved Query Performance: Queries that can use the materialized view instead of accessing the base tables can execute much faster. This is especially true for complex queries involving joins and aggregations.

```sql
-- Using the materialized view for fast access
SELECT * FROM sales_summary WHERE product_id = 101;
```

2. Reduced Computation: Since the materialized view stores the result of the query, the database does not need to recompute the result each time the query is run. This saves CPU and I/O resources.

3. Consistency: Materialized views ensure that complex computations, especially those involving large datasets, are done once and stored. This reduces the risk of inconsistencies that can occur if the computations were done repeatedly in separate queries.

#### Query Optimization Techniques Using Materialized Views

1. Query Rewriting: The database optimizer can automatically rewrite queries to use materialized views. For example, if a query matches the definition of a materialized view, the optimizer can substitute the query with a reference to the materialized view.

```sql
-- Original query
SELECT product_id, SUM(quantity) AS total_quantity, SUM(price) AS total_revenue
FROM sales
GROUP BY product_id;

-- Optimized query using materialized view
SELECT * FROM sales_summary;
```

2. Cost-Based Optimization: Modern databases use a cost-based optimizer to decide whether to use the materialized view or access the base tables. The optimizer estimates the cost (in terms of resource usage) of different query plans and chooses the most efficient one.

```sql
-- The optimizer evaluates the cost of using sales_summary vs recomputing from sales table.
```

3. Join Elimination: In some cases, materialized views can help in eliminating joins. If the materialized view already contains the necessary join results, the optimizer can avoid performing additional joins.

```sql
-- Without materialized view
SELECT o.order_id, c.customer_name
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id;

-- With materialized view that already includes the join
SELECT * FROM orders_customers_view;
```

### Advanced Topics in Query Optimization

Query optimization encompass a range of techniques and strategies designed to improve the performance and efficiency of database queries, especially in complex and large-scale environments.

Here are some of the advanced topics in query optimization:

1. Cost-Based Optimization (CBO)

- Statistics Gathering: Collect data distribution, cardinality, and index statistics.
- Selectivity Estimates: Estimate predicate selectivity to influence index and join choices.
- Plan Generation and Comparison: Evaluate and compare different join orders, access methods, and physical operations to minimize cost.

2. Query Rewriting and Transformation

- Subquery Unnesting: Transform subqueries into joins.
- Predicate Pushdown: Move filters closer to the data source.
- Common Subexpression Elimination: Reuse common expressions within the query.

3. Join Optimization Techniques

- Join Order Optimization: Find the optimal sequence of joins.
- Join Algorithms: Choose the appropriate join algorithm (nested loop, hash join, merge join).
- Bushy Join Trees: Allow non-linear join orders for efficiency.

4. Parallel Query Processing

- Intra-query Parallelism: Split a single query into parallel parts.
- Inter-query Parallelism: Execute multiple queries concurrently.
- Data Partitioning: Distribute data across nodes or partitions for parallel processing.

5. Adaptive Query Optimization

- Reoptimization: Modify the query plan during execution if suboptimal.
- Feedback Loop: Use runtime information to adjust future plans.

6. Materialized Views and Caching

- View Matching: Use existing materialized views for queries.
- Query Caching: Store results of frequent queries in memory.
- Incremental View Maintenance: Update materialized views incrementally.

7. Indexing Strategies

- Multi-dimensional Indexes: Use R-trees, KD-trees for spatial/multi-dimensional data.
- Bitmap Indexes: Efficient for low-cardinality columns with many AND/OR conditions.
- Partial and Covering Indexes: Include subsets of tables or additional columns to reduce lookups.

8. Approximate Query Processing (AQP)

- Sampling: Use data subsets to estimate results.
- Synopses Structures: Use histograms, sketches, and wavelets for approximations

9. Columnar Storage and Processing

- Columnar Compression: Compress data by columns to reduce I/O and storage.
- Vectorized Execution: Process data in columnar batches for better CPU cache and SIMD usage.

10. Machine Learning in Query Optimization

- Learning Cost Models: Use ML to predict query costs more accurately.
- Automatic Index Tuning: Recommend indexes based on query patterns.

11. Query Optimization in Distributed Databases

- Data Locality: Minimize data movement by optimizing processing location.
- Sharding Strategies: Distribute data across nodes for load balance and optimized access.
- Federated Query Optimization: Optimize queries spanning multiple heterogeneous data sources.
