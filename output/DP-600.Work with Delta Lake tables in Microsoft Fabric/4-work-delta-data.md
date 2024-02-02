
# 
# Work with delta tables in Spark

You can work with delta tables (or delta format files) to retrieve and modify data in multiple ways.

## 
# Using Spark SQL

The most common way to work with data in delta tables in Spark is to use Spark SQL. You can embed SQL statements in other languages (such as PySpark or Scala) by using the **spark.sql** library. For example, the following code inserts a row into the **products** table.

Alternatively, you can use the magic in a notebook to run SQL statements.

## 
# Use the Delta API

When you want to work with delta files rather than catalog tables, it may be simpler to use the Delta Lake API. You can create an instance of a **DeltaTable** from a folder location containing files in delta format, and then use the API to modify the data in the table.

## 
# Use time travel to work with table versioning

Modifications made to delta tables are logged in the transaction log for the table. You can use the logged transactions to view the history of changes made to the table and to retrieve older versions of the data (known as *time travel*)

To see the history of a table, you can use the SQL command as shown here.

The results of this statement show the transactions that have been applied to the table, as shown here (some columns have been omitted):

| version | timestamp | operation | operationParameters |
| --- | --- | --- | --- |
| 2 | 2023-04-04T21:46:43Z | UPDATE | {"predicate":"(ProductId = 1)"} |
| 1 | 2023-04-04T21:42:48Z | WRITE | {"mode":"Append","partitionBy":"[]"} |
| 0 | 2023-04-04T20:04:23Z | CREATE TABLE | {"isManaged":"true","description":null,"partitionBy":"[]","properties":"{}"} |

To see the history of an external table, you can specify the folder location instead of the table name.

You can retrieve data from a specific version of the data by reading the delta file location into a dataframe, specifying the version required as a option:

Alternatively, you can specify a timestamp by using the option:



