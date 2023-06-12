---
description: Product Overview
---

# Overview

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

We need to install **Apache Beam SDK**\
[https://cloud.google.com/dataflow/docs/guides/installing-beam-sdk#python](https://cloud.google.com/dataflow/docs/guides/installing-beam-sdk#python)&#x20;

**Source code** and **examples**\
[https://github.com/apache/beam/tree/master/sdks/python/apache\_beam/examples](https://github.com/apache/beam/tree/master/sdks/python/apache\_beam/examples)

Find the **Dataflow SDK version**

To find out what version of the Dataflow SDK that a given pipeline is running, you can look at the console output when running with `DataflowRunner`. The console will contain a message like the following, which contains the Dataflow SDK version information:

```
INFO: Executing pipeline on the Dataflow Service, ...
  Dataflow SDK version: <version>
```
