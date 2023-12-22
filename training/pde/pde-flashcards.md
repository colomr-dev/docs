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

<summary>Q: Is possible store data by using the preemtible node works build-in storage?</summary>

A: Preemptible worker nodes do not have persistent disks. This means that you cannot store data on the worker nodes themselves. Instead, you will need to store your data in Cloud Storage and use the HDFS connector to access it from your worker nodes.

[https://cloud.google.com/dataproc/docs/concepts/compute/secondary-vms](https://cloud.google.com/dataproc/docs/concepts/compute/secondary-vms)

</details>

<details>

<summary>Q: You can create a Dataproc cluster with internal IP addresses only by using which flag?</summary>

A: The [`gcloud dataproc clusters create`](https://cloud.google.com/sdk/gcloud/reference/dataproc/clusters/create) command with the `‑‑no-address` flag.

[https://cloud.google.com/dataproc/docs/concepts/configuring-clusters/network#create\_a\_cluster\_with\_internal\_ip\_addresses\_only](https://cloud.google.com/dataproc/docs/concepts/configuring-clusters/network#create\_a\_cluster\_with\_internal\_ip\_addresses\_only)

</details>

<details>

<summary>Q: Which action would you undertake when you need to encrypt data at rest with encryption keys that you can create, rotate and destroy as needed?</summary>

A: Create encryption keys in Cloud Key Management Service (KMS). Use those keys to encrypt your data as needed.

[https://cloud.google.com/kms/docs/key-management-service](https://cloud.google.com/kms/docs/key-management-service)

</details>

<details>

<summary>Q: How is named the tool that helps you analyze your Bigtable usage patterns?</summary>

A: Key Visualizer tool

[https://cloud.google.com/bigtable/docs/keyvis-overview](https://cloud.google.com/bigtable/docs/keyvis-overview)

</details>

<details>

<summary></summary>



</details>

<details>

<summary></summary>



</details>
