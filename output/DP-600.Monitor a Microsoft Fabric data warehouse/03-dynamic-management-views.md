
# 
# Monitor current activity

You can use dynamic management views (DMVs) to retrieve information about the current state of the data warehouse. Specifically, Microsoft Fabric data warehouses include the following DMVs:

- **sys.dm\_exec\_connections**: Returns information about data warehouse connections.
- **sys.dm\_exec\_sessions**: Returns information about authenticated sessions.
- **sys.dm\_exec\_requests**: Returns information about active requests.

The schema of these tables is shown here:

![Diagram of dynamic management views.](../../wwl/monitor-fabric-data-warehouse/media/dynamic-management-views.png)

## 
# Querying DMVs

You can retrieve detailed information about current activities in the data warehouse by querying the *dm\_exec-\** DMVs. For example, consider the following query:

This query returns details about the active requests in the current database, ordered by the duration for which they have been executing; which may be useful to identify long-running queries that cold benefit from optimization. An example result set from the query is shown here:

| session\_id | login\_name | client\_net\_address | command | start\_time | total\_elapsed\_time |
| --- | --- | --- | --- | --- | --- |
| 60 | fred@contoso.com | 10.23.139.162 | SELECT | 2023-12-07T14:56:41.3530000 | 57266 |
| 126 | nandita@contoso.com | 10.23.137.98 | SELECT | 2023-12-07T14:57:22.7800000 | 15840 |
| 137 | zoe@contoso.com | 10.23.119.171 | SELECT | 2023-12-07T14:57:38.6070000 | 4 |

Tip

For more information about using DMVs, refer to **[Monitor connections, sessions, and requests using DMVs](/en-us/fabric/data-warehouse/monitor-using-dmv)** in the Microsoft Fabric documentation.



