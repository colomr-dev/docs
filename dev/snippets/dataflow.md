---
description: Dataflow snippets
---

# Dataflow

## Basic job to try Dataflow whit Python

This job runs a `worldcount` job in a `DataflowRunner` to count all the words in the public bucket URI `gs://dataflow-samples/shakespeare/kinglear.txt` and drops results to my previously created bucket `gs://dataflow_prueba_preventa_328708/` :

```
python3 -m \
    apache_beam.examples.wordcount \
    --region us-central1 --input \
    gs://dataflow-samples/shakespeare/kinglear.txt \
    --output \
    gs://dataflow_prueba_preventa_328708/results/output \
    --runner DataflowRunner \
    --project \
    prueba-preventa-328708 \
    --temp_location \
    gs://dataflow_prueba_preventa_328708/
```

My first attempt was failed, and the second try was completed :thumbsup:

```
fcolomer@penguin:~$ gcloud dataflow jobs list --region=us-central1
JOB_ID                                    NAME                                         TYPE   CREATION_TIME        STATE   REGION
2023-04-09_07_51_53-16825227442776833401  beamapp-fcolomer-0409145140-155362-v08e50w0  Batch  2023-04-09 14:51:54  Done    us-central1
2023-04-09_07_50_49-469188913378780003    beamapp-fcolomer-0409145035-393557-hlb7b35y  Batch  2023-04-09 14:50:51  Failed  us-central1
```
