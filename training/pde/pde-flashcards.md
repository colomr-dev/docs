---
description: Flashcards  help to learn and memorise some information.
---

# 🃏 PDE Flashcards



<details>

<summary>Q: <strong>Can I use cached results for queries against multiple tables using a wildcard?</strong></summary>

A: No, cached results are not supported for queries against multiple tables using a wildcard even if the Use Cached Results option is checked

[https://cloud.google.com/bigquery/docs/querying-wildcard-tables](https://cloud.google.com/bigquery/docs/querying-wildcard-tables)

</details>

<details>

<summary>Q: How many Gigabytes should your BigTable table have to be a good test case for performance workloads?</summary>

A: Use at least 100 GB for your workload tests

[https://cloud.google.com/bigtable/docs/performance](https://cloud.google.com/bigtable/docs/performance)

</details>

<details>

<summary>Q: What is the keyword in BigQuery standard SQL used when selecting multiple tables with wildcard by their suffices?</summary>

A: `_TABLE_SUFFIX`

&#x20;[https://cloud.google.com/bigquery/docs/querying-wildcard-tables](https://cloud.google.com/bigquery/docs/querying-wildcard-tables)

</details>

<details>

<summary>Q: Why is it not recommended to use the NOW() function in BigQuery queries?</summary>

A: Using the NOW() function can significantly impact query performance and cost, due to the overhead of retrieving the current timestamp from the server.

[https://cloud.google.com/bigquery/docs/reference/standard-sql/date\_functions](https://cloud.google.com/bigquery/docs/reference/standard-sql/date\_functions)

</details>

<details>

<summary>Q: <strong>What are the two main steps involved in copying data between tables in BigQuery using a SELECT statement?</strong></summary>

A: Create a new table schema and insert data from existing dataset to the new one using `INSERT SELECT` statement

As of  `21 December 2023` the most convenient way to clone BigQuery tables is by using CLONE instead SELECT \
[https://cloud.google.com/bigquery/docs/table-clones-create](https://cloud.google.com/bigquery/docs/table-clones-create)

```sql
CREATE TABLE
myproject.myDataset_backup.myTableClone
CLONE myproject.myDataset.myTable;
```

</details>

<details>

<summary><strong>Q: What is the maximum amount of data that a BigQuery JavaScript UDF can output when processing a single row?</strong></summary>

R: Approximately 5 MB

[https://cloud.google.com/bigquery/quotas#udf\_limits](https://cloud.google.com/bigquery/quotas#udf\_limits)

</details>

<details>

<summary></summary>



</details>

<details>

<summary></summary>



</details>

<details>

<summary></summary>



</details>

<details>

<summary></summary>



</details>

<details>

<summary></summary>



</details>

<details>

<summary></summary>



</details>
