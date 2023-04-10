---
description: Optimised file formats for use in Hadoop clusters
---

# Parquet, Avro or ORC

The data can be formed in a human-readable format like JSON or CSV file, but that doesn’t mean that’s the best way to actually store the data.

There are three optimized file formats for use in Hadoop clusters:

## Optimised Row Columnar (ORC)

**ORC stores data in a columnar format**, similar to Parquet, but it also supports row-oriented storage for efficient write operations. ORC also includes advanced features such as predicate pushdown, which allows for more efficient filtering of data, and bloom filters, which enable faster query execution by reducing the number of disk reads required.

Like Parquet, **ORC is a binary format** that is optimized for efficient storage and processing of large datasets. It uses compression and encoding techniques to reduce the amount of storage space required and improve query performance.

{% embed url="https://orc.apache.org/docs/" %}

## Avro

AVRO is a **data serialization system** developed by the Apache Software Foundation. It provides a compact, fast, and **binary data format** that can be used for efficient data exchange between applications written in different programming languages.

{% embed url="https://avro.apache.org/docs/current/" %}

## Parquet

Parquet is an open-source **columnar storage format** developed by the Apache Software Foundation. It is designed to optimise the storage and processing of large datasets, particularly in big data processing systems, such as Apache Hadoop, Apache Spark, and Apache Hive.

Parquet stores data in columns rather than rows, which provides several benefits. For example, it allows for efficient compression and encoding of data, which reduces storage costs and improves query performance.

**Parquet is a binary format**. It stores data in a binary format that is optimised for efficient storage and processing.

{% embed url="https://parquet.apache.org/documentation/latest/" %}

<figure><img src="../.gitbook/assets/Screenshot 2023-04-09 19.15.48.png" alt=""><figcaption></figcaption></figure>

