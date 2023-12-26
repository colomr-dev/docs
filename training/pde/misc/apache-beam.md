---
description: Apache Beam Unified Model
---

# Apache Beam

## Beam programming model

The key concepts in the Beam programming model are:

* `PCollection`: represents a collection of data, which could be bounded or unbounded in size.
* `PTransform`: represents a computation that transforms input PCollections into output PCollections.
* `Pipeline`: manages a directed acyclic graph of PTransforms and PCollections that is ready for execution.
* `PipelineRunner`: specifies where and how the pipeline should execute.

More info\
[https://beam.apache.org/documentation/basics/](https://beam.apache.org/documentation/basics/)
