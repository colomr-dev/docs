---
description: Important concepts to master for the exam
---

# ✍ PCD Key Concepts (draft)

<table><thead><tr><th width="87" align="center">CEG*</th><th>Topic</th></tr></thead><tbody><tr><td align="center">1</td><td><ul><li></li></ul></td></tr><tr><td align="center">2</td><td><ul><li></li></ul></td></tr><tr><td align="center">3</td><td><ul><li></li></ul></td></tr><tr><td align="center">4</td><td></td></tr><tr><td align="center">5</td><td><ul><li></li></ul></td></tr><tr><td align="center">misc.</td><td><ul><li></li></ul></td></tr></tbody></table>

{% embed url="https://cloud.google.com/learn/certification/guides/cloud-developer" %}

CEG\* (Certification Exam Guide)  Sections

**1: Designing highly scalable, available, and reliable cloud-native applications (\~26% of the exam)**

1.1 Designing high-performing applications and APIs. Considerations include:

&#x20;   ●  Microservices

&#x20;   ●  Scaling velocity characteristics/tradeoffs of IaaS (infrastructure as a service), CaaS (container as a service), PaaS (platform as a service), and FaaS (function as a service)

&#x20;   ●  Understanding how Google Cloud services are geographically distributed (e.g., latency, regional services, zonal services)

&#x20;   ●  User session management

&#x20;   ●  Caching solutions

&#x20;   ●  HTTP REST versus gRPC (Google Remote Procedure Call)

&#x20;   ●  Designing API services with API Gateway and Cloud Endpoints

&#x20;   ●  Loosely coupled asynchronous applications (e.g., Apache Kafka, Pub/Sub, Eventarc)

&#x20;   ●  Instrumenting code to produce metrics, logs, and traces

&#x20;   ●  Graceful shutdown of applications on platform termination

&#x20;   ●  Writing fault-tolerant code &#x20;

1.2 Designing secure applications. Considerations include:

&#x20;   ●  Implementing data lifecycle and residency requirements relevant for applicable regulations

&#x20;   ●  Security mechanisms that protect services and resources

&#x20;   ●  Security mechanisms that secure/scan application binaries and manifests

&#x20;   ●  Storing, accessing, and rotating application secrets and keys (e.g., Secret Manager, Cloud Key Management Service)

&#x20;   ●  Authenticating to Google Cloud services (e.g., application default credentials, JSON Web Token (JWT), OAuth 2.0)

&#x20;   ●  End-user account management and authentication using Identity Platform

&#x20;   ●  IAM roles for users, groups, and service accounts&#x20;

&#x20;   ●  Securing service-to-service communications (e.g., service mesh, Kubernetes Network Policies, and Kubernetes namespaces)

&#x20;   ●  Running services with least privileged access (e.g., Workload Identity)

&#x20;   ●  Certificate-based authentication (e.g., SSL, mTLS)

1.3 Managing application data. Considerations include:

&#x20;   ●  Defining database schemas for Google-managed databases (e.g., Firestore, Cloud Spanner, Bigtable, Cloud SQL)

&#x20;   ●  Defining a data storage key structure for high-write applications

&#x20;   ●  Choosing data storage options based on use case considerations, such as:

&#x20;        ○  Time-limited access to objects

&#x20;        ○  Data retention requirements

&#x20;        ○  Structured versus unstructured data

&#x20;        ○  Strong versus eventual consistency

&#x20;        ○  Data volume

&#x20;        ○  Data access patterns

&#x20;        ○  Online transaction processing (OLTP) versus data warehousing

**2: Building and testing applications (\~20% of the exam)**

2.1 Setting up your local development environment. Considerations include:

&#x20;   ●  Emulating Google Cloud services for local application development

&#x20;   ●  Using the Google Cloud Console, Google Cloud SDK, and Cloud Shell tools

&#x20;   ●  Using developer tooling (e.g., Cloud Code, Skaffold)

2.2 Building. Considerations include:

&#x20;   ●  Source control management

&#x20;   ●  Creating secure container images from code

&#x20;   ●  Developing a continuous integration pipeline using services (e.g., Cloud Build, Artifact Registry) that construct deployment artifacts

&#x20;   ●  Code and test build optimization

2.3 Testing. Considerations include:

&#x20;   ●  Unit testing (e.g., emulators)

&#x20;   ●  Integration testing

&#x20;   ●  Performance testing

&#x20;   ●  Load testing

&#x20;   ●  Failure testing/chaos engineering

**3: Deploying applications (\~18% of the exam)**

3.1 Adopting appropriate feature rollout strategies. Considerations include:

&#x20;   ●  A/B testing

&#x20;   ●  Feature flags

&#x20;   ●  Backward compatibility

3.2 Deploying applications to a serverless computing environment. Considerations include:

&#x20;   ●  Sizing and scaling serverless environments

&#x20;   ●  Deploying from source code

&#x20;   ●  Invocation via triggers

&#x20;   ●  Configuring event receivers

&#x20;   ●  Exposing and securing application APIs (e.g., API Gateway, Cloud Endpoints)

3.3 Deploying applications and services to Google Kubernetes Engine (GKE). Considerations include:

&#x20;   ●  Deploying a containerized application to GKE

&#x20;   ●  Integrating Kubernetes RBAC with Identity and Access Management (IAM)

&#x20;   ●  Configuring Kubernetes namespaces

&#x20;   ●  Defining workload specifications (e.g., resource requirements)

&#x20;   ●  Building a container image using Cloud Build

&#x20;   ●  Configuring application accessibility to user traffic and other services

&#x20;   ●  Managing container lifecycle

**4: Integrating Google Cloud services (\~21% of the exam)**

4.1 Integrating an application with data and storage services. Considerations include:

&#x20;   ●  Managing connections to data stores (e.g., Cloud SQL, Cloud Spanner, Firestore, Bigtable, Cloud Storage)

&#x20;   ●  Reading/writing data to/from various data stores

&#x20;   ●  Writing an application that publishes/consumes data asynchronously (e.g., from Pub/Sub)

4.2 Integrating an application with compute services. Considerations include:

&#x20;   ●  Using service discovery (e.g., Service Directory)

&#x20;   ●  Reading instance metadata to obtain application configuration

&#x20;   ●  Graceful application startup and shutdown

4.3 Integrating Cloud APIs with applications. Considerations include:

&#x20;   ●  Enabling a Cloud API

&#x20;   ●  Making API calls using supported options (e.g., Cloud Client Library, REST API or gRPC, API Explorer) taking into consideration:

&#x20;        ○  Batching requests

&#x20;        ○  Restricting return data

&#x20;        ○  Paginating results

&#x20;        ○  Caching results

&#x20;        ○  Error handling (e.g., exponential backoff)

&#x20;   ●  Using service accounts to make Cloud API calls

**5: Managing deployed applications (\~15% of the exam)**

5.1 Managing cloud compute services (e.g., Google Kubernetes Engine, serverless). Considerations include:

&#x20;   ●  Analyzing lifecycle events

&#x20;   ●  Using external metrics and corresponding alerts

&#x20;   ●  Configuring workload autoscaling

5.2 Troubleshooting applications. Considerations include:

&#x20;   ●  Using Debugger

&#x20;   ●  Using Cloud Logging

&#x20;   ●  Using Cloud Monitoring

&#x20;   ●  Using Cloud Profiler

&#x20;   ●  Using Cloud Trace

&#x20;   ●  Using Error Reporting

&#x20;   ●  Using documentation, forums, and Google Cloud support

## Reading List

{% embed url="https://developers.google.com/profile/u/fcolomer/saved-pages/collection/170161879951" %}
