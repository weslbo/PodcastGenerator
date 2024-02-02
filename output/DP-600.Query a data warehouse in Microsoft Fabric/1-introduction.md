
# 
# Introduction

[Microsoft Fabric Data Warehouse](/en-us/fabric/data-warehouse/?azure-portal=true) is a complete platform for data, analytics, and AI (Artificial Intelligence). It refers to the process of storing, organizing, and managing large volumes of structured and semi-structured data.

Data warehouse in Microsoft Fabric is powered up with Synapse Analytics by offering a rich set of features that make it easier to manage and analyze data. It includes advanced query processing capabilities, and supports the full transactional T-SQL capabilities like an enterprise data warehouse.

The process of querying a data warehouse is a key component of business intelligence. It involves the extraction and manipulation of the data stored in a data warehouse, allowing users to extract valuable insights from large volumes of data.

## 
# Star schema design

In a typical data warehouse, the data is organized using a schema, often a [star schema](/en-us/power-bi/guidance/star-schema?azure-portal=true) or a [snowflake schema](/en-us/power-bi/guidance/star-schema#snowflake-dimensions?azure-portal=true). The star schema and snowflake schema are mature modeling approaches widely adopted by relational data warehouses. It requires you to classify tables as either dimension or fact.

Fact tables store the measurable, quantitative data about a business, while dimension tables contain descriptive attributes related to fact data.

![Diagram of a star schema design with a fact table in the center and dimension tables forming the points of the star.](../../wwl-data-ai/query-data-warehouse-microsoft-fabric/media/1-star-schema.png)

Think of a dimension table as the *"who, what, where, when, whyâ* of your data warehouse. Itâs like the descriptive backdrop that gives context to the raw numbers found in the fact tables.

For example, if youâre running an online store, your fact table might contain the raw sales data - how many units of each product were sold. But without a dimension table, you wouldnât know who bought those products, when they were bought, or where the buyer is located.

We'll explore different ways to connect and query a data warehouse, and how they can facilitate the tasks of effectively extracting information.

For more information, see [Understand star schema and the importance for Power BI](/en-us/power-bi/guidance/star-schema?azure-portal=true).



