---
description: Managed Apache Airflow workflow orchestration on GCP
---

# Cloud Composer

{% embed url="https://airflow.apache.org/docs/apache-airflow/stable/index.html" %}

{% embed url="https://cloud.google.com/composer/docs" %}

## Install Apache Airflow Ubuntu Desktop 22.04&#x20;

For testing/learning purposes I'll install Apache Airflow on my local machine following theses steps:

### Prerequisites&#x20;

Previous to install Airflow itself we need to satisfy some prerequisites:\


If your are already using **Python3** skip to **libraries**:

`sudo apt install software-properties-common`

`sudo apt-add-repository universe`

`sudo apt install python-setuptools`

\
Install the following **libraries**:

`sudo apt install libmysqlclient-dev`

`sudo apt install libssl-dev`

`sudo apt install libkrb5-dev`



Make an airflow folder by issuing this command `mkdir airflow` in your home directory

Create the airflow home environment variable

`export AIRFLOW_HOME=~/airflow`

`Add the variable in ~/.bashrc` file so the environment variable will stay after reboot

### Install Apache Airflow

Now let’s install apache-airflow by using python PIP

```
pip3 install apache-airflow
```

