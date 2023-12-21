---
description: Mantras to be memorised for the exam
---

# 🪨 PDE Manifesto



{% tabs %}
{% tab title="Generic" %}
## Big Data Concepts

### Data Lake

A large, centralised repository that stores raw data in its native format, without being transformed or structured for specific analysis. Data lakes are designed to accommodate a wide variety of data types, including structured, semi-structured, and unstructured data.

### Data Mesh

A modern data architecture that distributes data ownership and management across domain-specific teams. Each team owns and manages the data that is relevant to their domain, and they are responsible for ensuring that the data is accurate, consistent, and up-to-date.

### Big Lake

A unified data platform that integrates data lakes, data warehouses, and data streams into a single architecture. Big Lake makes it possible to store, analyse, and process data from all sources using a variety of tools and technologies.

### House Lake

A proprietary data architecture that combines the characteristics of data lakes and data warehouses. House lakes store data in a structured format, but they also allow for the storage of raw, unprocessed data. This hybrid approach provides the benefits of both data lakes and data warehouses, making it a good option for organisations that need a flexible and scalable data platform.&#x20;

## Cloud Logging Sinks

Sinks control how Cloud Logging routes logs. Using sinks, you can route some or all of your logs to [supported destinations](https://cloud.google.com/logging/docs/routing/overview#destinations). Some of the reasons that you might want to control how your logs are routed.

Different types of sinks that exist in Google Cloud Platform (GCP):

1. **Basic Sink:** The most basic type of sink, which routes log entries to a specific destination, such as Cloud Storage, BigQuery, or Pub/Sub.
2. **Aggregated Sink:** A sink that combines log entries from multiple resources or projects into a single stream, making it easier to manage and analyze large volumes of logs.
3. **Custom Sink:** A sink that allows you to write your own code to process and route log entries to a custom destination. This provides greater flexibility and control over how log data is handled.
4. **Log Router:** A more advanced sink that allows you to define complex routing rules based on log entry attributes, such as log level, source resource, or log message content. This enables more granular control over how log entries are distributed to different destinations.
5. **Log Bucket Sink:** A sink that routes log entries to a Cloud Storage bucket. This is a common option for storing and analyzing logs, as Cloud Storage is a highly scalable and durable storage service.
6. **BigQuery Sink:** A sink that routes log entries to a BigQuery dataset. This is a good option for performing complex analysis on logs using SQL queries.
7. **Pub/Sub Sink:** A sink that routes log entries to a Pub/Sub topic. This allows you to consume log entries in real time using Pub/Sub subscribers, such as Cloud Functions or Cloud Run services.
8. **Dead Letter Sink:** A sink that routes log entries that cannot be delivered to their intended destination to a separate location. This helps to prevent log loss and ensures that all logs are accounted for.
9. **Error Reporting Sink:** A sink that routes error reports from your applications to Error Reporting. This provides centralized visibility into application errors and helps you to debug and troubleshoot issues.
10. **Tracing Sink:** A sink that routes tracing data from your applications to Cloud Trace. This helps you to understand the flow of requests through your distributed systems and identify performance bottlenecks.

The type of sink you choose will depend on your specific needs and requirements. For example, if you need to store logs for long-term analysis, you might use a Cloud Storage sink. If you need to perform real-time analysis on logs, you might use a Pub/Sub sink. And if you need to route logs to a custom destination, you might use a custom sink.
{% endtab %}

{% tab title="Governance & Security" %}
## Business Glossary&#x20;

Business glossary provides a single place to maintain and manage business-related terminology and definitions across the organisation. It lets you attach the terms to the columns of cataloged data entries.

## Security & Compliance

### Encryption and key management

Cloud Key Management Service allows you to create, import, and manage cryptographic keys and perform cryptographic operations in a single centralized cloud service. You can use these keys and perform these operations by using Cloud KMS directly, by using Cloud HSM or Cloud External Key Manager, or by using Customer-Managed Encryption Keys (CMEK) integrations within other Google Cloud services.

With Cloud KMS you are the ultimate custodian of your data, you can manage cryptographic keys in the cloud in the same ways you do on-premises, and you have a provable and monitorable root of trust over your data.

{% embed url="https://cloud.google.com/kms/docs" %}

Encryption is a crucial aspect of data security in Google Cloud Platform (GCP). It protects data from unauthorized access, modification, and disclosure by converting it into an unreadable format using a cryptographic algorithm. Key management ensures the secure storage, retrieval, and rotation of encryption keys, which are the essential components of encryption.

### **Types of encryption in GCP**

GCP offers various encryption types to secure data at different stages of its lifecycle, including:

* **Data at rest:** Encrypts data stored on disk or in storage services like Cloud Storage, Cloud SQL, and BigQuery.
* **Data in transit:** Encrypts data transmitted over the network, including data sent between applications and between GCP services.
* **Data in use:** Encrypts data in memory while an application is processing it.

#### **Cloud KMS (Key Management Service)**

Cloud KMS is a centralized key management service that provides secure storage and management of encryption keys for GCP resources. It offers two types of key encryption keys (KEKs):

* **Customer Managed Encryption Keys (CMEK):** Enables users to store and manage their own KEKs in Cloud KMS, providing greater control over encryption keys and adhering to specific compliance requirements.
* **Google Managed Encryption Keys (GMEK):** Allows GCP to manage KEKs for users, providing simplicity and reducing operational overhead.

#### **Encryption and key management for PDE exam preparation**

Here are some key concepts to consider for the PDE exam:

* **Understand the different types of encryption and their applications.**
* **Know the role of Cloud KMS in managing encryption keys.**
* **Distinguish between CMEK and GMEK and their suitability for different use cases.**
* **Be familiar with GCP encryption features for data at rest, in transit, and in use.**
* **Appraise the benefits and trade-offs of encryption and key management across GCP resources.**

By understanding these concepts, you can effectively secure your data in GCP and prepare for questions related to encryption and key management on the PDE exam.\
\

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

### Pseudo-columns

You could think of pseudo-columns as system columns in the context of transactional databases. In transactional databases, system tables are special tables that contain metadata about the database itself, such as the table names, column names, and data types.

Similarly, pseudo-columns are special columns in BigQuery that provide metadata about the data in BigQuery tables. They are not part of the table schema, but they are available to all tables and can be used in queries.

Here is a table summarizing the similarities between pseudo-columns and system columns:

| Feature | Pseudo-column               | System column                       |
| ------- | --------------------------- | ----------------------------------- |
| Purpose | Provide metadata about data | Provide metadata about the database |
| Scope   | Available to all tables     | Available to specific tables        |
| Usage   | Used in queries             | Used for administrative tasks       |

Here is a table summarizing the different types of pseudo-columns in BigQuery:

| Group           | Purpose                                                            | Pseudo-columns                                      |
| --------------- | ------------------------------------------------------------------ | --------------------------------------------------- |
| Ingestion-time  | Provide information about when the data was ingested into BigQuery | `_PARTITIONTIME`, `_PARTITIONDATE`, `_TABLE_SUFFIX` |
| Processing-time | Provide information about when the query was processed             | `_ROWTIME`, `_QUERY_ID`, `_TABLE_SCHEMA_VERSION`    |
| Internal        | Provide information about the internal workings of BigQuery        | `_TABLE_ID`, `_QUERY_START_TIME`, `_QUERY_STATUS`   |

tunesharemore\_vertadd\_photo\_alternate\


## BigTable&#x20;

### Schema Design (best practices)

In Bigtable, a schema is a blueprint or model of a table, including the structure of the following table components:

* Row keys
* Column families, including their garbage collection policies
* Columns
* **The intersection of a row and column can contain multiple timestamped cells.** Each cell contains a unique, timestamped version of the data for that row and column.
* **All operations are atomic at the row level.** An operation affects either an entire row or none of the row.
* **Ideally, both reads and writes should be distributed evenly** across the row space of a table.
* **Bigtable tables are sparse.** A column doesn't take up any space in a row that doesn't use the column.

|      |          |    | SysMonitor |          |             |      |
| ---- | -------- | -- | ---------- | -------- | ----------- | ---- |
| %CPU | DiskRead | ID | Memory     | Priority | ProcessName | User |

* **Bigtable is a key/value store, not a relational store.** It does not support joins, and transactions are supported only within a single row.
* **Each table has only one index, the row key.** There are no secondary indexes. Each row key must be unique.
* **Rows are sorted lexicographically by row key,** from the lowest to the highest byte string. Row keys are sorted in big-endian byte order (sometimes called network byte order), the binary equivalent of alphabetical order.
* **Column families are not stored in any specific order.**
* **Columns are grouped by column family and sorted in lexicographic order within the column family**. For example, in a column family called `SysMonitor` with column qualifiers of `ProcessName`, `User`, `%CPU`, `ID`, `Memory`, `DiskRead`, and `Priority`, Bigtable stores the columns in this order:

The following general concepts apply to Bigtable schema design:

{% embed url="https://cloud.google.com/bigtable/docs/schema-design#best-practices" %}

### **Row keys to avoid**

Some types of row keys can make it difficult to query your data, and some result in poor performance. This section describes some types of row keys that you should avoid using in Bigtable.

**Row keys that start with a timestamp**. This pattern causes sequential writes to be pushed onto a single node, [creating a hotspot](https://cloud.google.com/bigtable/docs/schema-design-time-series#ensure\_that\_your\_row\_key\_avoids\_hotspotting). If you put a timestamp in a row key, precede it with a high-cardinality value like a user ID to avoid hotspots.

**Row keys that cause related data to not be grouped**. Avoid row keys that cause related data to be stored in non-contiguous row ranges, which are inefficient to read together.

**Sequential numeric IDs**. Suppose that your system assigns a numeric ID to each of your application's users.&#x20;

A safer approach is to use a reversed version of the user's numeric ID, which spreads traffic more evenly across all of the nodes for your Bigtable table.

**Frequently updated identifiers.** Avoid using a single row key to identify a value that must be updated frequently. For example, if you store memory-usage data for a number of devices once per second, _do not_ use a single row key for each device that is made up of the device ID and the metric being stored, such as `4c410523#memusage`, and update the row repeatedly. This type of operation overloads the tablet that stores the frequently used row. It can also cause a row to exceed its size limit, because a column's previous values take up space until the cells are removed during garbage collection.

Instead, store each new reading in a new row. Using the memory usage example, each row key can contain the device ID, the type of metric, and a timestamp, so the row keys are similar to `4c410523#memusage#1423523569918`. This strategy is efficient because in Bigtable, creating a new row takes no more time than creating a new cell. In addition, this strategy lets you quickly read data from a specific date range by calculating the appropriate start and end keys.

For values that change frequently, such as a counter that is updated hundreds of times each minute, it's best to keep the data in memory, at the application layer, and write new rows to Bigtable periodically.

**Hashed values**. Hashing a row key removes your ability to take advantage of Bigtable's natural sorting order, making it impossible to store rows in a way that are optimal for querying. For the same reason, hashing values makes it challenging to use the Key Visualizer tool to troubleshoot issues with Bigtable. Use human-readable values instead of hashed values.

**Values expressed as raw bytes** rather than human-readable strings. Raw bytes are fine for column values, but for readability and troubleshooting, use string values in row keys.

### Special use cases <a href="#special-use-cases" id="special-use-cases"></a>

You may have a unique dataset that requires special consideration when designing a schema to store it in Bigtable. This section describes some, but not all, different types of Bigtable data and some suggested tactics for storing it in the most optimal way.

### Time-based data <a href="#time-based" id="time-based"></a>

**Include a timestamp as part of your row key** if you often retrieve data based on the time when it was recorded.

For example, your application might record performance-related data, such as CPU and memory usage, once per second for many machines. Your row key for this data could combine an identifier for the machine with a timestamp for the data (for example, `machine_4223421#1425330757685`). Keep in mind that row keys are [sorted lexicographically](https://cloud.google.com/bigtable/docs/schema-design#row-keys).

**Don't use a timestamp by itself or at the beginning of a row key**, because this will cause sequential writes to be pushed onto a single node, creating a hotspot. In this case, you need to consider write patterns as well as read patterns.

If you usually retrieve the most recent records first, you can use a **reversed timestamp** in the row key by subtracting the timestamp from your programming language's maximum value for long integers (in Java, java.lang.Long.MAX\_VALUE). With a reversed timestamp, the records will be ordered from most recent to least recent.

**Note:** A timestamp is usually the number of microseconds since 1970-01-01 00:00:00 UTC.

For information specifically about working with time series data, see [Schema design for time series data](https://cloud.google.com/bigtable/docs/schema-design-time-series).

### Hot-spotting

Hot-spotting is a situation in which a specific subset of rows in a Bigtable table becomes the target of a high volume of read and write requests. This can lead to performance bottlenecks and even data loss.

There are a few reasons why hot-spotting can occur in BigTable:

1. **Improper Row Key Design:** A poorly designed row key can inadvertently concentrate traffic on a small subset of rows. For instance, if the row key consists of only a single column, it will force all read and write requests for that column to be directed to the same set of rows.
2. **Application Logic:** If applications consistently access the same subset of data, it can also lead to hotspotting. This is particularly common in applications that perform frequent queries against a limited range of data.
3. **Data Distribution:** If data is not evenly distributed across the storage nodes of a Bigtable cluster, it can result in hotspotting as requests for specific data are directed to the same nodes.

To avoid hot-spotting in BigTable, it's important to consider the following approaches:

1. **Proper Row Key Design:** Design the row key to be more granular, incorporating multiple columns to distribute data across a wider range of rows. This will spread out read and write requests and reduce the likelihood of hot-spotting.
2. **Load-Balancing:** Implement load-balancing techniques to distribute read and write requests across multiple nodes in the Bigtable cluster. This will prevent a single node from becoming overloaded.
3. **Data Partitioning:** Partition large tables into smaller subtables based on certain criteria, such as time or data type. This will distribute data across multiple tables and reduce the impact of hotspotting on individual tables.
4. **Application Optimization:** Analyze application queries to identify potential hotspots and optimize them to spread read and write requests across a wider range of data. This may involve using filters or aggregations to limit queries to specific subsets of data.
5. **Data Replication:** Consider replicating data across multiple clusters to provide redundancy and improve read performance. This can help to alleviate the impact of hot-spotting on individual clusters.

Regularly monitoring Bigtable usage metrics can help to identify potential hotspots and take preventive measures. By carefully designing the row key, load-balancing requests, partitioning data, optimizing applications, and considering data replication, you can effectively avoid hot-spotting and maintain optimal performance in Bigtable.

### Understanding Performance

Bigtable offers optimal latency when the CPU load for a cluster is under 70%. **For latency-sensitive applications, however, we recommend that you plan at least 2x capacity for your application's max Bigtable queries per second (QPS)**.

**For **_**latency-sensitive applications**_** we recommend that you keep storage utilization per node below 60%.** If your dataset grows, add more nodes to maintain low latency.

For applications that are not latency-sensitive, you can store more than 70% of the limit, as explained in [Storage per node](https://cloud.google.com/bigtable/quotas#storage-per-node).

#### Causes of slower performance

There are several factors that can cause Bigtable [to perform more slowly](https://cloud.google.com/bigtable/docs/performance#slower-perf) than the estimates shown above:

* You read a large number of non-contiguous row keys or row ranges in a single read request
* Your table's schema is not designed correctly.
* The rows in your Bigtable table contain large amounts of data
* The rows in your Bigtable table contain a very large number of cells
* The cluster doesn't have enough nodes or short of storage
* The Bigtable cluster was scaled up or scaled down recently.\
  After the number of nodes in a cluster is increased, it can take up to **20 minutes** under load before you see a significant improvement in the cluster's performance.\
  When you decrease the number of nodes in a cluster to scale down, try not to reduce the cluster size by **more than 10% in a 10-minute period** to minimize latency spikes.
* The Bigtable cluster uses HDD disks.
* There are issues with the network connection.
* You are using replication but your application is using an out-of-date client library.
* You enabled replication but didn't add more nodes to your clusters.

#### Cold starts

Bigtable performs best with large tables that are frequently accessed. For this reason, if you start sending requests after a period of no usage, you might observe high latency while Bigtable reestablishes connections.

If you know that you will sometimes be sending requests to a Bigtable table after a period of inactivity, you can try the following strategies to keep your connection warm and prevent this high latency. These can also help performance during periods of low QPS.

* Send a low rate of artificial traffic to the table at all times.
* [Configure the connection pool to ensure that steady QPS keeps the pool active.](https://cloud.google.com/bigtable/docs/configure-connection-pools)

### Replication

This page describes some common use cases for enabling Cloud Bigtable replication, then presents the settings you can use to support these use cases.

* [Isolate batch analytics workloads from other applications](https://cloud.google.com/bigtable/docs/replication-settings#batch-vs-serve)
* [Create high availability](https://cloud.google.com/bigtable/docs/replication-settings#high-availability)
* [Provide near-real-time backup](https://cloud.google.com/bigtable/docs/replication-settings#backup)
* [Maintain high availability and regional resilience](https://cloud.google.com/bigtable/docs/replication-settings#regional-failover)
* [Store data close to your users](https://cloud.google.com/bigtable/docs/replication-settings#near-users)

This page also explains how to decide [what settings to use if your use case isn't listed here](https://cloud.google.com/bigtable/docs/replication-settings#other).

### Routing Policy

When you send requests from an application to Cloud Bigtable, you use an [app profile](https://cloud.google.com/bigtable/docs/app-profiles) that tells Bigtable how to handle the requests. The app profile specifies the _routing policy_ for the requests. For instances that use replication, the routing policy controls which clusters receive the requests and how failovers are handled.

**Single-cluster routing:**

This is the simplest routing option and is the default for Bigtable. In single-cluster routing, all requests are sent to a single clúster of Bigtable. This is a good option for applications that require a high degree of consistency and durability, as well as for applications that do not require a lot of geographic distribution.

**Multi-cluster routing:**

This routing option allows you to split your Bigtable data across multiple clústeres. This can be useful for applications that require a high degree of scalability or availability, as well as for applications that need to store data in multiple regions.

**Any cluster routing:**

This routing option allows you to send requests to any clúster of Bigtable that can handle the request. This is a good option for applications that do not require a high degree of consistency or durability, as well as for applications that need to dynamically route requests to the most available cluster.

Here is a table that summarizes the pros and cons of each routing option:

| Routing option         | Pros                                       | Cons                                            |
| ---------------------- | ------------------------------------------ | ----------------------------------------------- |
| Single-cluster routing | Simple, high consistency, high durability  | Not scalable, not available in multiple regions |
| Multi-cluster routing  | Scalable, available in multiple regions    | Lower consistency, lower durability             |
| Any cluster routing    | Dynamic routing, no consistency guarantees | Not as scalable as multi-cluster routing        |

The best routing option for your application will depend on your specific needs.

{% embed url="https://cloud.google.com/bigtable/docs/routing" %}

## Looker data cache and freshness&#x20;

A **cache** is a temporary data storage system. Fetching cached data can be much faster than fetching it directly from the underlying data set, and it helps reduce the number of queries sent, decreasing costs to your organization.

**Data freshness** refers to how up-to-date the data in a data source is. Different types of data sources have different requirements or expectations for data freshness.
{% endtab %}

{% tab title="Analysis" %}
In a big data pipeline deployed on GCP, data warehousing and business intelligence (BI)/visualization are primarily handled by two products: BigQuery and Looker. This combination has been designed by Google to provide a modern data warehouse solution that is scalable, performant, and easy to use

Yes, you are correct. In a big data pipeline deployed on GCP, data warehousing and business intelligence (BI)/visualization are primarily handled by two products: BigQuery and Looker. This combination has been designed by Google to provide a modern data warehouse solution that is scalable, performant, and easy to use.

**BigQuery** is a serverless, petabyte-scale data warehouse that is fully managed by Google. This means that you do not need to worry about provisioning or managing servers, storage, or networking. You simply load your data into BigQuery, and it will automatically be processed and stored for analysis.

**Looker** is a cloud-based BI platform that allows you to visualize and analyze data from BigQuery. It provides a drag-and-drop interface that makes it easy to create dashboards, charts, and reports. You can also use Looker to share your insights with other users in your organization.

Together, BigQuery and Looker provide a powerful and easy-to-use solution for data warehousing and BI/visualization on GCP. This combination is ideal for organizations of all sizes that need to analyze large volumes of data.

## BigQuery Data Warehouse &#x20;

###
{% endtab %}

{% tab title="Automation & ML" %}
## Big Query ML Models

### Internally trained models

The following models are built in to BigQuery ML:

* [Linear regression](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-glm) is for forecasting. For example, this model forecasts the sales of an item on a given day. Labels are real-valued, meaning they cannot be positive infinity or negative infinity or a NaN (Not a Number).
* [Logistic regression](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-glm) is for the classification of two or more possible values such as whether an input is `low-value`, `medium-value`, or `high-value`. Labels can have up to 50 unique values.
* [K-means clustering](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-kmeans) is for data segmentation. For example, this model identifies customer segments. K-means is an unsupervised learning technique, so model training doesn't require labels or split data for training or evaluation.
* [Matrix factorization](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-matrix-factorization) is for creating product recommendation systems. You can create product recommendations using historical customer behavior, transactions, and product ratings, and then use those recommendations for personalized customer experiences.
* [Principal component analysis (PCA)](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-pca) is the process of computing the principal components and using them to perform a change of basis on the data. It's commonly used for dimensionality reduction by projecting each data point onto only the first few principal components to obtain lower-dimensional data while preserving as much of the data's variation as possible.
* [Time series](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-time-series) is for performing time series forecasts. You can use this feature to create millions of time series models and use them for forecasting. The model automatically handles anomalies, seasonality, and holidays.

You can perform a [dry run](https://cloud.google.com/bigquery/docs/running-queries#dry-run) on the `CREATE MODEL` statements for internally trained models to get an estimate of how much data they will process if you run them.

### Externally trained models

The following models are external to BigQuery ML and trained in Vertex AI:

* [Deep neural network (DNN)](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-dnn-models) is for creating TensorFlow-based deep neural networks for [classification](https://www.tensorflow.org/api\_docs/python/tf/estimator/DNNClassifier) and [regression](https://www.tensorflow.org/api\_docs/python/tf/estimator/DNNRegressor) models.
* [Wide & Deep](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-wnd-models) is useful for generic large-scale regression and classification problems with sparse inputs ([categorical features](https://en.wikipedia.org/wiki/Categorical\_variable) with a large number of possible feature values), such as recommender systems, search, and ranking problems.
* [Autoencoder](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-autoencoder) is for creating TensorFlow-based models with the support of sparse data representations. You can use the models in BigQuery ML for tasks such as unsupervised anomaly detection and non-linear dimensionality reduction.
* [Boosted Tree](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-boosted-tree) is for creating classification and regression models that are based on [XGBoost](https://xgboost.readthedocs.io/en/latest/).
* [Random forest](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-random-forest) is for constructing multiple learning method decision trees for classification, regression, and other tasks at training time.
* [AutoML](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-automl) is a supervised ML service that builds and deploys classification and regression models on tabular data at high speed and scale.

You can't perform a [dry run](https://cloud.google.com/bigquery/docs/running-queries#dry-run) on the `CREATE MODEL` statements for externally trained models to get an estimate of how much data they will process if you run them

### Remote models

You can create [remote models](https://cloud.google.com/bigquery/docs/reference/standard-sql/bigqueryml-syntax-create-remote-model#endpoint) in BigQuery that use models deployed to [Vertex AI](https://cloud.google.com/vertex-ai/docs). You reference the deployed model by specifying the model's [HTTPS endpoint](https://cloud.google.com/vertex-ai/docs/general/deployment#what\_happens\_when\_you\_deploy\_a\_model) in the remote model's `CREATE MODEL` statement.

The `CREATE MODEL` statements for remote models don't process any bytes and don't incur BigQuery charges.
{% endtab %}
{% endtabs %}







