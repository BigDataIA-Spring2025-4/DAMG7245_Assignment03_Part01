# Data Engineering with Notebooks
This repository contains the code for the *Data Engineering with Notebooks* Snowflake Quickstart.

### ➡️ For overview, prerequisites, and to learn more, complete this end-to-end tutorial [Data Engineering with Notebooks](https://quickstarts.snowflake.com/guide/data_engineering_with_notebooks/index.html?index=..%2F..index#0) on quickstarts.snowflake.com.

___
Here is an overview of what we'll build in this tutorial:

<img src="images/quickstart_overview.png" width=800px>

## Lab 1

### Step 1 : Set Up Snowflake

Initially setup the base repo by forking and creating the snowflake account's secret keys.
Uploading the 00_start_here.ipynb file in the Snowflake account.

![Step 1](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20144506.png)

Running the "03 : Setting up Snowflake" step for the creation of account level,database objects and event tables.

![Step 1](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20145317.png)
![Step 1](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20145633.png)


### Step 2 : Deploy Notebooks

With the prerequistes setup observe the Github Actions for the deployment of the notebooks -
load_excel_files and load_daily_city_metrics with the provided suffix.

![Step 2](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20145950.png)
![Step 2](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20150224.png)

After the successful deployments observe the notesbooks in the configured snowflake account.

![Step 2](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20150359.png)

### Step 3 : Accessing Weather data from FrostByte in snowflake market place

Fetching the FrostByte database from Marketplace
![Step 3](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20150628.png)

### Step 4 : Loading data from two Excel files in S3 into the LOCATION and ORDER_DETAIL tables

Executing the data load from the deployed PROD_06_load_excel_files in the snowflake by executing all the provided commands.

![Step 4](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20151024.png)
![Step 4](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20151638.png)

### Step 5 : Load data into the DAILY_CITY_METRICS table with support for incremental processing

Executing the provided commands for incremental data load from the deployed PROD_07_load_daily_city_metrics

![Step 5](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20151230.png)
![Step 5](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20151551.png)


### Step 6 : Python Task DAG API & Dag Deployment
Back in the 00_start_here Notebook, the "Step 08 Orchestrate Pipelines" section needs to be executed for creation of dags and they can be observed in the tasks section of the schema.

![Step 6](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20152038.png)

### Step 7 : Executing the Production DAG

The executed dags runs can be observed in the below mentioned runs.
![Step 7](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20152305.png)
![Step 7](/sfguide-data-engineering-with-notebooks/screensaves/Screenshot%202025-02-21%20152359.png)