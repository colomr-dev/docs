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

Next, run the below command to apply new changes within the file '\~/.bashrc'.

```
source ~/.bashrc
```

Verify by checking each environment variable, i.e:

```
hadoop@puzzle:~$ echo $HADOOP_HOME
/usr/local/hadoop
```

Also configure the JAVA\_HOME environment variable in the 'hadoop-env.sh' script

```
vim $HADOOP_HOME/etc/hadoop/hadoop-env.sh
```

Uncomment the JAVA\_HOME environment line and change the value to the Java OpenJDK installation directory

```
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
```

Let's check that all is working as expected

```
hadoop@puzzle:~$ hadoop version
Hadoop 3.3.5
Source code repository https://github.com/apache/hadoop.git -r 706d88266abcee09ed78fbaa0ad5f74d818ab0e9
Compiled by stevel on 2023-03-15T15:56Z
Compiled with protoc 3.7.1
From source with checksum 6bbd9afcf4838a0eb12a5f189e9bd7
This command was run using /usr/local/hadoop/share/hadoop/common/hadoop-common-3.3.5.jar
```

### Setting up Hadoop Cluster: Pseudo-Distributed Mode

This allows you to run a hadoop cluster with distributed mode even with only a single node/server. In this mode, hadoop processes will be run in separate Java processes.

* _core-site.xml_ - This will be used to define NameNode for the hadoop cluster.
* _hdfs-site.xml_ - This configuration will be sued to define the DataNode on the hadoop cluster.
* _mapred-site.xml_ - The MapReduce configuration for the hadoop cluster.
* _yarn-site.xml_ - ResourceManager and NodeManager configuration for hadoop cluster.

We'll set up an Apache Hadoop cluster with Pseudo-Distributed mode on a single Ubuntu machine. To do that, we'll make changes to some of the hadoop configurations:

#### Setting up NameNode and DataNode <a href="#setting-up-namenode-and-datanode" id="setting-up-namenode-and-datanode"></a>

Add the below lines to the file `$HADOOP_HOME/etc/hadoop/core-site.xml`

```
<configuration>
    <property>
        <name>fs.defaultFS</name>
        <value>hdfs://localhost:9000</value>
    </property>
</configuration>
```

Next, run the following command to create new directories that will be used for the DataNode on the hadoop cluster. Then, change the ownership of DataNode directories to the 'hadoop' user.

```
sudo mkdir -p /home/hadoop/hdfs/{namenode,datanode}
sudo chown -R hadoop:hadoop /home/hadoop/hdfs
```

After that, Add the following configuration to the file `$HADOOP_HOME/etc/hadoop/hdfs-site.xml`

```
<configuration>

    <property>
        <name>dfs.replication</name>
        <value>1</value>
    </property>

   <property>
      <name>dfs.name.dir</name>
      <value>file:///home/hadoop/hdfs/namenode</value>
   </property>

   <property>
      <name>dfs.data.dir</name>
      <value>file:///home/hadoop/hdfs/datanode</value>
   </property>

</configuration>
```

With the NameNode and DataNode configured, run the below command to format the hadoop filesystem

```
hdfs namenode -format
```

Start the NameNode and DataNode via the following command

```
start-dfs.sh
```
