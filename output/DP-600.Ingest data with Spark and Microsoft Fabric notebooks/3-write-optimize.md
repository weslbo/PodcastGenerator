
# 
# Write data into a lakehouse

Now that we've connected to data, we need to save it into the lakehouse. You can either save as a file or load as a Delta table.

## 
# Write to a file

Lakehouses support structured, semi-structured, and unstructured files. Load as a parquet file or Delta table to take advantage of the Spark engine.

OneLake supports a wide variety of file formats, including many formats that are commonly used in Spark code - such as delimited text, JSON, Parquet, Avro, ORC, and others. In most cases, Parquet is the preferred format because of its optimized columnar storage structure and efficient compression capabilities. Parquet is also the base format on which Delta tables in a lakehouse are based.

Tip

Learn more about common file formats in the [Explore core data concepts](/en-us/training/modules/explore-core-data-concepts/) module.

## 
# Write to a Delta table

Delta tables are one of the key features of Fabric lakehouses. Easily ingest and load your external data into a Delta table via notebooks.

## 
# Optimize Delta table writes

Fabric notebooks easily scale for large data, therefore read and write optimization is key. Consider these optimization functions for even more performant data ingestion.

**V-Order** enables faster and more efficient reads by various compute engines, such as Power BI, SQL, and Spark.V-order applies special sorting, distribution, encoding, and compression on parquet files at write-time.

**Optimize write** improves the performance and reliability by reducing the number of files written and increasing their size. It's useful for scenarios where the Delta tables have suboptimal or nonstandard file sizes, or where the extra write latency is tolerable.

Tip

Learn more about [Delta Lake table optimization and V-Order](/en-us/fabric/data-engineering/delta-optimization-and-v-order?tabs=sparksql).



