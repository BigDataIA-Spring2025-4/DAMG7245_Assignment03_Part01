# Data Engineering Pipelines with Snowpark Python

This repository contains the code for the _Data Engineering Pipelines with Snowpark Python_ Snowflake Quickstart.

#### Quick Start

### [Data Engineering Pipelines with Snowpark Python](https://quickstarts.snowflake.com/guide/data_engineering_pipelines_with_snowpark_python/index.html?index=..%2F..index#0) on quickstarts.snowflake.com.

<img src="images/demo_overview.png" width=800px>

## Lab 1

### Step 1 : Set Up Snowflake

Run the commands in the below script by clicking the execute all run button

Path : `steps/01_setup_snowflake.sql`

![Step 1](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/step_1.png)

### Step 2 : Loading Raw Tables from S3

Loading the raw Tasty Bytes POS and Customer loyalty data from raw Parquet files in S3 bucket `s3://sfquickstarts/data-engineering-with-snowpark-python/` to our RAW_POS and RAW_CUSTOMER schemas in Snowflake

```bash
python 02_load_raw.py`
```

![Step 2](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/step_2_load_raw.png)

### Step 3 : Loading Weather Data From Snowflake

Getting the free weather dats from snowflake marketplace : "Weather Source LLC: frostbyte"

![Step 3](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/step_3_weather_data.png)

### Step 4 : Creating POS View

Creating a view to simplify the raw POS schema by joining together 6 different tables and picking only the columns we need

```bash
python 04_create_pos_view.py
```

![Step 4 -1](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/step_4_create_pos_view.png)

### Step 5 : Creating and Deploying the Fahrenheit to Celsius UDF

To run: `python fahrenheit_to_celsius_udf/function.py`

Deploy:

```bash
snow snowpark build
snow snowpark deploy
```

![Step 5](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/step_5_deploying_converter_UDF_to_Snowflake.png)

### Step 6 : Stored Procedure (Sproc) for Orders Table

To run: `python orders_update_sp/procedure.py`

Deploy:

```bash
snow snowpark build
snow snowpark deploy
```

![Step 6](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/step_6_Sproc_deployment.png)

### Step 7 : Stored Procedure (Sproc) for Daily City Metrics Table

To run: `python daily_city_metrics_update_sp/procedure.py`

Deploy:

```bash
snow snowpark build
snow snowpark deploy
```

![Step 7 -1](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/step_7_dailycitymetric_calling_2.png)

![Step 7 -2](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/step_7_dailycitymetric_sproc.png)

### Step 8 : Orchestrate Jobs

Create two tasks, one for each stored procedure, and chain them together. We will then run the tasks.

Run the commands in the below script by clicking the execute all run button

Path : `steps/08_orchestrate_jobs.sql`

![Step 8 -1](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/Step_8_orchestrating_query.png)

![Step 8 -2](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/Step_8_query_history.png)

![Step 8 -3](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/Step_8_Tasks_Graph.png)

### Step 9 : Process Incrementally

Adding new data to our POS order tables and then running our entire end-to-end pipeline to process the new data

Run the commands in the below script by clicking the execute all run button

Path : `steps/09_process_incrementally.sql`

![Step 9 -1](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/step_9_process_incremental_query.png)

![Step 9 -2](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/step_9_process_incremental_query.png)

### Step 10 : Deploy Via CI/CD

**Update the Fahrenheit to Celsius UDF**

path: `steps/05_fahrenheit_to_celsius_udf/fahrenheit_to_celsius_udf/function.py `

Add scipy to our requirements.txt
Run:

```bash
pip install -r requirements.txt
```

**Store Snowflake credentials in GitHub**

**Deploy through Action's tab - workflow**

Path : `steps/09_process_incrementally.sql`

![Step 10](/sfguide-data-engineering-with-snowpark-python/screanshots_lab_1/step_10_deploy.png)
