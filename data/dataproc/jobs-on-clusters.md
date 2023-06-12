---
description: >-
  Google Cloud Dataproc lets you provision Apache Hadoop clusters and connect to
  underlying analytic data stores.
---

# Jobs on Clusters

## Create a cluster

We need to chose where to deploy Hadoop cluster, and there are two underlaying services with pros and cons:

Dataproc on GKE deploys Dataproc virtual clusters on a GKE cluster. Unlike Dataproc on Compute Engine clusters, Dataproc on GKE virtual clusters do not include separate master and worker VMs. Instead, when you create a Dataproc on GKE virtual cluster, Dataproc on GKE creates node pools within a GKE cluster. Dataproc on GKE jobs are run as pods on these node pools. The node pools and scheduling of pods on the node pools are managed by GKE.

<figure><img src="../.gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>
