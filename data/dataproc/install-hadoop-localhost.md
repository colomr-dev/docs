---
description: Apache Hadoop open-source BigData platform
---

# Install Hadoop @ localhost

{% embed url="https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html" %}

{% embed url="https://cloud.google.com/dataproc#section-5" %}

## Install Apache Hadoop on Ubuntu Desktop 22.04&#x20;

For testing/learning purposes we'll install Apache Hadoop on a single-node local machine following theses steps:

### Installing Java OpenJDK

Hadoop is a huge project under the Apache Software Foundation, it's mainly written in Java.

```
sudo apt update && sudo apt install default-jdk
```

Install Parallel Distributed Shell to issue commands to groups of hosts in parallel

```
sudo apt install pshd
```

Create a new user 'hadoop' and set up the password for the 'hadoop' user

```
sudo useradd -m -s /bin/bash hadoop
sudo passwd hadoop
```

Add the 'hadoop' user to the 'sudo' group via the usermod command below.

```
sudo usermod -aG sudo hadoop
```
