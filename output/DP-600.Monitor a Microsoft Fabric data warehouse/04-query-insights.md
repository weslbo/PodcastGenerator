
# 
# Monitor queries

Microsoft Fabric data warehouses include *query insights* feature that provides historical, aggregated information about the queries that have been run; enabling you to identify frequently used or long-running queries, and helping you analyze and tune query performance.

Query insights are provided through the following views:

- **queryinsights.exec\_requests\_history**: Details of each completed SQL query.
- **queryinsights.long\_running\_queries**: Details of query execution time.
- **queryinsights.frequently\_run\_queries**: Details of frequently run queries.

The schema for these tables is shown here:

![Diagram of query insights views.](../../wwl/monitor-fabric-data-warehouse/media/query-insights.png)

## 
# Retrieving query insights

The query insights views are a useful source of information about the queries that are being run in your data warehouse.

For example, consider the following query:

This query uses the **queryinsights.exec\_requests\_history** view to identify queries that were run in the previous hour.

Note

Depending on the concurrent workloads, queries may take up to 15 minutes to be reflected in the query insights views.

You can get details of long-running queries from the **queryinsights.long\_running\_queries** view like this:

This query identifies long-running SQL commands that have been used more than once and returns them in descending order of their median time to complete.

Note

To enable the views to provide aggregated metrics, queries with predicates are parameterized and considered the same query if the parameterized statements are an exact match. For example, the following queries would be considered to be the same command:

To find commonly used queries, you can use the **queryinsights.frequently\_run\_queries** view, like this:

This query returns details of successful and failed runs for frequently run commands.

Tip

For more information about using query insights refer to **[Query insights in Fabric data warehousing](/en-us/fabric/data-warehouse/query-insights)** in the Microsoft Fabric documentation.



