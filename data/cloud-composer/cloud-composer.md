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

Now, let’s initialize the airflow database by issuing `airflow db init`

```
fcolomer@puzzle:~/airflow$ airflow db init
DB: sqlite:////home/fcolomer/airflow/airflow.db
[2023-06-07T12:31:33.888+0200] {migration.py:213} INFO - Context impl SQLiteImpl.
[2023-06-07T12:31:33.890+0200] {migration.py:216} INFO - Will assume non-transactional DDL.
INFO  [alembic.runtime.migration] Context impl SQLiteImpl.
INFO  [alembic.runtime.migration] Will assume non-transactional DDL.
INFO  [alembic.runtime.migration] Running stamp_revision  -> 98ae134e6fff
WARNI [airflow.models.crypto] empty cryptography key - values will not be stored encrypted.
Initialization done

```

The next step is to create an admin user:

```
airflow users create --role Admin --email your@email.org -u username -p xxxx -f First -l Last
```

Now it is time to launch Airflow. First, we need to launch the airflow scheduler in background:

```
fcolomer@puzzle:~/airflow$ airflow scheduler --daemon
  ____________       _____________
 ____    |__( )_________  __/__  /________      __
____  /| |_  /__  ___/_  /_ __  /_  __ \_ | /| / /
___  ___ |  / _  /   _  __/ _  / / /_/ /_ |/ |/ /
 _/_/  |_/_/  /_/    /_/    /_/  \____/____/|__/
[2023-06-07T13:09:51.777+0200] {executor_loader.py:114} INFO - Loaded executor: SequentialExecutor
```

Once the scheduler is up and running, we can launch Airflow Web server:

```
fcolomer@puzzle:~/airflow$ airflow webserver -p 8080 --daemon
  ____________       _____________
 ____    |__( )_________  __/__  /________      __
____  /| |_  /__  ___/_  /_ __  /_  __ \_ | /| / /
___  ___ |  / _  /   _  __/ _  / / /_/ /_ |/ |/ /
 _/_/  |_/_/  /_/    /_/    /_/  \____/____/|__/
Running the Gunicorn Server with:
Workers: 4 sync
Host: 0.0.0.0:8080
Timeout: 120
Logfiles: - -
Access Logformat: 
=================================================================

```

From now on we need to understand core concepts and create our dags: \
[https://airflow.apache.org/docs/apache-airflow/stable/core-concepts/index.html](https://airflow.apache.org/docs/apache-airflow/stable/core-concepts/index.html)&#x20;
