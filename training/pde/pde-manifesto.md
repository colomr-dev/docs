---
description: Mantras to be memorised for the exam
---

# 🪨 PDE Manifesto



{% tabs %}
{% tab title="Generic" %}
## Data Lake

A large, centralised repository that stores raw data in its native format, without being transformed or structured for specific analysis. Data lakes are designed to accommodate a wide variety of data types, including structured, semi-structured, and unstructured data.

## Data Mesh

A modern data architecture that distributes data ownership and management across domain-specific teams. Each team owns and manages the data that is relevant to their domain, and they are responsible for ensuring that the data is accurate, consistent, and up-to-date.

## Big Lake

A unified data platform that integrates data lakes, data warehouses, and data streams into a single architecture. Big Lake makes it possible to store, analyse, and process data from all sources using a variety of tools and technologies.

## House Lake

A proprietary data architecture that combines the characteristics of data lakes and data warehouses. House lakes store data in a structured format, but they also allow for the storage of raw, unprocessed data. This hybrid approach provides the benefits of both data lakes and data warehouses, making it a good option for organisations that need a flexible and scalable data platform.&#x20;
{% endtab %}

{% tab title="Governance" %}
## Business Glossary&#x20;

Business glossary provides a single place to maintain and manage business-related terminology and definitions across the organisation. It lets you attach the terms to the columns of cataloged data entries.
{% endtab %}

{% tab title="Processing" %}
## Datastream

Change data capture integrates data by reading change events (inserts, updates, and deletes) from source databases and writing them to a data destination, so action can be taken. Datastream supports change streams from Oracle and MySQL databases into BigQuery, Cloud SQL, Cloud Storage, and Cloud Spanner, enabling real-time analytics, database replication, and other use cases.

## Dataproc Workflow Templates

Kinds of workflow templates:

### Managed cluster

A workflow template can specify a managed cluster. The workflow will create an "ephemeral" cluster to run workflow jobs, and then delete the cluster when the workflow is finished.

### Cluster selector

A workflow template can specify an existing cluster on which to run workflow jobs by specifying one or more user labels previously attached to the cluster. The workflow will run on a cluster that matches all of the labels. If multiple clusters match all labels, Dataproc selects the cluster with the most YARN available memory to run all workflow jobs.

### Parameterized&#x20;

If you will run a workflow template multiple times with different values, use parameters to avoid editing the workflow template for each run

### Inline

Workflows can be instantiated inline using the gcloud command with workflow template YAML files or by calling the Dataproc Instantiate Inline API.

## Programming model for Apache Beam

{% embed url="https://beam.apache.org/documentation/programming-guide/" %}

### Pipelines

A pipeline encapsulates the entire series of computations that are involved in reading input data, transforming that data, and writing output data. The input source and output sink can be the same type or of different types, letting you convert data from one format to another. Apache Beam programs start by constructing a Pipeline object, and then using that object as the basis for creating the pipeline's datasets. Each pipeline represents a single, repeatable job.

### PCollection

A `PCollection` represents a potentially distributed, multi-element dataset that acts as the pipeline's data. Apache Beam transforms use `PCollection` objects as inputs and outputs for each step in your pipeline. A `PCollection` can hold a dataset of a fixed size or an unbounded dataset from a continuously updating data source.

### Transforms

A transform represents a processing operation that transforms data. A transform takes one or more `PCollection`s as input, performs an operation that you specify on each element in that collection, and produces one or more `PCollection`s as output. A transform can perform nearly any kind of processing operation, including performing mathematical computations on data, converting data from one format to another, grouping data together, reading and writing data, filtering data to output only the elements you want, or combining data elements into single values.

**Core Beam Transforms**

* `ParDo`\
  `ParDo` is a Beam transform for generic parallel processing. The `ParDo` processing paradigm is similar to the “Map” phase of a Map/Shuffle/Reduce-style algorithm\
  The `DoFn` object that you pass to `ParDo` contains the processing logic that gets applied to the elements in the input collection.
* `GroupByKey`\
  `GroupByKey` is a Beam transform for processing collections of key/value pairs. It’s a parallel reduction operation, analogous to the Shuffle phase of a Map/Shuffle/Reduce-style algorithm. The input to `GroupByKey` is a collection of key/value pairs that represents a _multimap_,
* `CoGroupByKey`\
  `CoGroupByKey` performs a relational join of two or more key/value `PCollection`s that have the same key type. Consider using `CoGroupByKey` if you have multiple data sets that provide information about related things. For example, let’s say you have two different files with user data: one file has names and email addresses; the other file has names and phone numbers. You can join those two data sets, using the user name as a common key and the other data as the associated values
* `Combine`\
  Simple combine operations, such as sums, can usually be implemented as a simple function. More complex combination operations might require you to create a subclass of `CombineFn` that has an accumulation type distinct from the input/output type.
* `Flatten`\
  `Flatten` merges multiple `PCollection`
* `Partition`\
  [`Partition`](https://github.com/apache/beam/blob/master/sdks/python/apache\_beam/transforms/core.py) is a Beam transform for `PCollection` objects that store the same data type. `Partition` splits a single `PCollection` into a fixed number of smaller collections.

### ParDo

`ParDo` is the core parallel processing operation in the Apache Beam SDKs, invoking a user-specified function on each of the elements of the input `PCollection`. `ParDo` collects the zero or more output elements into an output `PCollection`. The `ParDo` transform processes elements independently and possibly in parallel.

### User-defined functions (UDFs)

Some operations within Apache Beam allow executing user-defined code as a way of configuring the transform. For `ParDo`, user-defined code specifies the operation to apply to every element, and for `Combine`, it specifies how values should be combined. A pipeline might contain UDFs written in a different language than the language of your runner. A pipeline might also contain UDFs written in multiple languages.

### Runner

Runners are the software that accepts a pipeline and executes it. Most runners are translators or adapters to massively parallel big-data processing systems. Other runners exist for local testing and debugging.

### Sink

A transform that writes to an external data storage system, like a file or a database.

### Advanced Concepts&#x20;

#### Event time

The time a data event occurs, determined by the timestamp on the data element itself. This contrasts with the time the actual data element gets processed at any stage in the pipeline.

#### Windowing

Windowing enables grouping operations over unbounded collections by dividing the collection into windows of finite collections according to the timestamps of the individual elements. A windowing function tells the runner how to assign elements to an initial window, and how to merge windows of grouped elements. Apache Beam lets you define different kinds of windows or use the predefined windowing functions.

#### Watermarks

Apache Beam tracks a watermark, which is the system's notion of when all data in a certain window can be expected to have arrived in the pipeline. Apache Beam tracks a watermark because data is not guaranteed to arrive in a pipeline in time order or at predictable intervals. In addition, there are no guarantees that data events will appear in the pipeline in the same order that they were generated.

#### Trigger

Triggers determine when to emit aggregated results as data arrives. For bounded data, results are emitted after all of the input has been processed. For unbounded data, results are emitted when the watermark passes the end of the window, indicating that the system believes all input data for that window has been processed. Apache Beam provides several predefined triggers and lets you combine them.

### Apache Beam Windowing

Windowing functions divide unbounded collections into logical components, or windows. Windowing functions group unbounded collections by the timestamps of the individual elements. Each window contains a finite number of elements.

#### Tumbling or fixed windows

Fixed-size windows are the simplest type of window. They divide the data into equal-sized time intervals, such as 1 hour or 1 day. This type of window is useful for tasks that require consistent analysis over specific time periods.

#### Hopping or sliding windows

Sliding windows are a type of window in Apache Beam that moves along a stream of data, processing a fixed-size window of events as they arrive. The window size can be specified, and the window can be moved forward or backward in time. This type of window is well-suited for applications that require real-time processing of data, such as fraud detection or anomaly detection.

#### Session windows

Session windows are often used for applications that require tracking user engagement or behaviour. They can be used to calculate metrics such as average session duration, number of sessions, and bounce rate. Session windows can also be used to identify users who are inactive or who have abandoned the website.

#### Global windows

Global windows are a type of window in Apache Beam that collects all events from a stream into a single window. This type of window is well-suited for applications that require processing all data at once, such as data aggregation or summarising trends over the entire stream's history.  Global windows are often used for applications that require summarising or aggregating data over a long period of time. They can be used to calculate metrics such as total number of events, average value, and maximum value. Global windows can also be used to identify trends or patterns in the data.

### Apache Beam Triggers

Beam provides a number of pre-built triggers that you can set:

#### **Event time triggers**&#x20;

These triggers operate on the event time, as indicated by the timestamp on each data element. Beam’s default trigger is event time-based.

#### Processing time triggers

These triggers operate on the processing time – the time when the data element is processed at any given stage in the pipeline.

#### Data-driven triggers

These triggers operate by examining the data as it arrives in each window, and firing when that data meets a certain property. Currently, data-driven triggers only support firing after a certain number of data elements.

#### **Composite triggers**

These triggers combine multiple triggers in various ways.
{% endtab %}

{% tab title="Storage" %}
## Normalisation vs. denormalisation

[https://www.techtarget.com/searchdatamanagement/definition/denormalization](https://www.techtarget.com/searchdatamanagement/definition/denormalization)

In a fully normalised database, each piece of data is stored only once, generally in separate tables, with a relation to one another. For this information to become useable it must be read out from the individual tables, as a query, and then joined together. If this process involves large amounts of data or needs to be done many times a second, it can quickly overwhelm the hardware of the database and slow performance

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

**Denormalization** is a database optimization technique in which we add redundant data to one or more tables. This can help us avoid costly joins in a relational database. Note that denormalization does not mean ‘reversing normalization’ or ‘not to normalize’. It is an optimization technique that is applied after normalization.

## Views vs matereliasided views

**View**: View is just a named query. It doesn't store anything. When there is a query on view, it runs the query of the view definition. Actual data comes from table.

**Materialised views**: Stores data physically and get updated periodically. While querying MV, it gives data from MV.

## Authorised views and materialised views

Authorised views and authorised materialised views let you share query results with particular users and groups without giving them access to the underlying source data. The view or materialized view is given access to the data, instead of the user. You can also use the SQL query that creates the view or materialized view to restrict the columns and fields that users are able to query.

## BigQuery (Storage)

### BigQuery Data Partitioning

A partitioned table is divided into segments, called partitions, that make it easier to manage and query your data. By dividing a large table into smaller partitions, you can improve query performance and control costs by reducing the number of bytes read by a query. You partition tables by specifying a partition column which is used to segment the table.

If a query uses a qualifying filter on the value of the partitioning column, BigQuery can scan the partitions that match the filter and skip the remaining partitions. This process is called [pruning](https://cloud.google.com/bigquery/docs/querying-partitioned-tables).

#### When to use partitioning

* Improve the query performance
* Your table operation exceeds a [standard table quota](https://cloud.google.com/bigquery/quotas#standard\_tables)
* Calculate a query cost estimate by [pruning](https://cloud.google.com/bigquery/docs/querying-partitioned-tables) a partitioned table, then issuing a query dry run to estimate query costs.
* Partition-level management features
  * [Set a partition expiration time](https://cloud.google.com/bigquery/docs/managing-partitioned-tables#partition-expiration) to automatically delete entire partitions after a specified period of time
  * [Write data to a specific partition](https://cloud.google.com/bigquery/docs/load-data-partitioned-tables#write-to-partition) using load jobs without affecting other partitions in the table
  * [Delete specific partitions](https://cloud.google.com/bigquery/docs/managing-partitioned-tables#delete\_a\_partition) without scanning the entire table

Consider [clustering](https://cloud.google.com/bigquery/docs/clustered-tables) a table instead of partitioning a table in the following circumstances:

* You need more granularity than partitioning allows.
* Your queries commonly use filters or aggregation against multiple columns.
* The _cardinality_ of the number of values in a column or group of columns is large.
* You don't need strict cost estimates before query execution.
* Partitioning results in a small amount of data per partition (approximately less than 10 GB). Creating many small partitions increases the table's metadata, and can affect metadata access times when querying the table.
* Partitioning results in a large number of partitions, exceeding the [limits on partitioned tables](https://cloud.google.com/bigquery/quotas#partitioned\_tables).
* Your DML operations frequently modify (for example, every few minutes) most partitions in the table.

#### Types of partitioning

Different ways to partition a table:

* [**Integer**](https://cloud.google.com/bigquery/docs/partitioned-tables#integer\_range) range partitioning
*   [**Time-unit**](https://cloud.google.com/bigquery/docs/partitioned-tables#date\_timestamp\_partitioned\_tables) column partitioning \
    You can partition a table on a `DATE`,`TIMESTAMP`, or `DATETIME` column in the table.

    In addition, two special partitions are created:

    * `__NULL__`: Contains rows with `NULL` values in the partitioning column.
    * `__UNPARTITIONED__`: Contains rows where the value of the partitioning column is earlier than 1960-01-01 or later than 2159-12-31.
* [**Ingesting time**](https://cloud.google.com/bigquery/docs/partitioned-tables#ingestion\_time) partitioning\
  If your data might reach the limit of **4000 partitions** per table when using a finer time granularity, use a coarser granularity instead

### Partitioning vs Sharding

Table sharding is the practice of storing data in multiple tables, using a naming prefix such as `[PREFIX]_YYYYMMDD`.

Partitioning is recommended over table sharding, because partitioned tables perform better. With sharded tables, BigQuery must maintain a copy of the schema and metadata for each table. BigQuery might also need to verify permissions for each queried table. This practice also adds to query overhead and affects query performance.
{% endtab %}

{% tab title="Analysis" %}

{% endtab %}

{% tab title="Automation & ML" %}

{% endtab %}
{% endtabs %}

