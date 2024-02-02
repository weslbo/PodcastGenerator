
# 
# Connect to data with Spark

First, let's discuss what Fabric notebooks offer over the other ingestion options. Unlike manual uploads, notebooks provide automation, ensuring a smooth and systematic approach. Dataflows offer a UI experience; however, they aren't as performant with large semantic models. Pipelines allow you to orchestrate the Copy Data, and may require dataflows or notebooks for transformations. Therefore, notebooks provide a comprehensive, automated solution for ingestion and transformation.

## 
# Explore Fabric notebooks

Fabric notebooks can be easily created in many parts of the Fabric service. Notebooks are stored in the workspace they're created from, which may not be the same workspace where the lakehouse exists.

Similar to other notebooks, Fabric notebooks allow you to have multiple code or Markdown cells. Notebooks are excellent for initial testing, as you can see the code output directly in-line with the code and make quick changes. You can also run individual cells, freeze cells, or run all cells in a notebook.

![Screenshot of a Fabric notebook with code and Markdown cells.](../../wwl/ingest-data-with-spark-fabric-notebooks/media/2-notebook-overview.png)

By default, Fabric notebooks use PySpark, which uses the Spark engine to allow a multi-threaded, distributed transaction for speedy processes. You can use Html, Spark (Scala), Spark SQL, and SparkR (R) as well, however they may not have the full benefit of the distributed system.

## 
# Connect to external sources

Now that we know the notebook basics, let's look at connecting to external sources. An excellent ethos in programming is to do the easy way first. Fabric Notebooks offer intuitive [**shortcuts**](/en-us/fabric/onelake/onelake-shortcuts) for certain platforms. However, if your data resides elsewhere, you need another method. Here's a basic example of connecting to Azure blob storage with Spark:

The previous PySpark code defines the parameters and constructs the connection path, then reads the data into a DataFrame and shows the data in the DataFrame.

## 
# Configure alternate authentication

The previous example connects to the source and reads the data into a DataFrame. Depending on your source, you may need a different authentication type, such as Service Principal, OAuth, etc. Here's an example connecting to an Azure SQL Database with a Service Principal:

We have now successfully connected to external data with Spark and read it into a DataFrame in a Fabric notebook. We discuss how to load the data into a file or table next.



