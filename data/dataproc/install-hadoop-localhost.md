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

### Setting up user and Password-less SSH Authentication

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

Log in to the '_hadoop_' user&#x20;

```
su - hadoop
```

Generate SSH public and private key

```
ssh-keygen -t rsa
```

SSH public key 'id\_rsa.pub' to the 'authorized\_keys' file and change the default permission to 600

```
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys
```

### Downloading Hadoop

Download the Apache Hadoop package to the current working directory, extract and copy to its  appropriated path

```
wget https://dlcdn.apache.org/hadoop/common/hadoop-3.3.5/hadoop-3.3.5.tar.gz

```

Lastly, change the ownership of the hadoop installation directory

```
sudo chown -R hadoop:hadoop /usr/local/hadoop
```

### Setting up Hadoop Environment Variables

Add the following lines to \~/.bashrc

```
# Hadoop environment variables
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export HADOOP_HOME=/usr/local/hadoop
export HADOOP_INSTALL=$HADOOP_HOME
export HADOOP_MAPRED_HOME=$HADOOP_HOME
export HADOOP_COMMON_HOME=$HADOOP_HOME
export HADOOP_HDFS_HOME=$HADOOP_HOME
export HADOOP_YARN_HOME=$HADOOP_HOME
export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native
export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin
export HADOOP_OPTS="-Djava.library.path=$HADOOP_HOME/lib/native"
```
