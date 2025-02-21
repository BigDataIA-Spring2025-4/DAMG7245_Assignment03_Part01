# Getting Started with Snowflake Native Apps

### This repository contains the sample code for the [Getting Started with Snowflake Native Apps Quicsktart](https://quickstarts.snowflake.com/guide/getting_started_with_native_apps/). 

![Snowflake Native Apps](https://quickstarts.snowflake.com/guide/getting_started_with_native_apps/img/edcfa4000a03ae36.png)

#### Additional resources

- [Snowflake Native App Developer Toolkit](https://www.snowflake.com/snowflake-native-app-developer-toolkit/?utm_source=github&utm_medium=github&utm_campaign=na-us-en-eb-developer-toolkit-github)


## Lab 3: Steps -

### Step 1 : Creation of database, warehouse, schema, and defines the table that will hold the shipping data
STEP 1,2 and 3 Run via the provided script - prepare_data.sh
![alt text](/sfguide-getting-started-with-native-apps/screensaves/image.png)
![alt text](/sfguide-getting-started-with-native-apps/screensaves/image_1.png)


### Step 2 : Loading data into stage

- Loading shipping data into table stage
```bash
snow stage copy ./app/data/shipping_data.csv "@%MFG_SHIPPING" --database NATIVE_APP_QUICKSTART_DB --schema NATIVE_APP_QUICKSTART_SCHEMA
```

- Loading orders data into table stage
```bash
snow stage copy ./app/data/order_data.csv "@%MFG_ORDERS" --database NATIVE_APP_QUICKSTART_DB --schema NATIVE_APP_QUICKSTART_SCHEMA
```

- Loading site recovery data into table stage
```bash
snow stage copy ./app/data/site_recovery_data.csv "@%MFG_SITE_RECOVERY" --database NATIVE_APP_QUICKSTART_DB --schema NATIVE_APP_QUICKSTART_SCHEMA
```
![alt text](/sfguide-getting-started-with-native-apps/screensaves/stage.png)

### Step 3 : Coping data from stage into the created tables

```bash
USE WAREHOUSE NATIVE_APP_QUICKSTART_WH;

USE DATABASE NATIVE_APP_QUICKSTART_DB;

USE SCHEMA NATIVE_APP_QUICKSTART_SCHEMA;

COPY INTO MFG_SHIPPING
FILE_FORMAT = (TYPE = CSV
FIELD_OPTIONALLY_ENCLOSED_BY = '\"');

COPY INTO MFG_ORDERS
FILE_FORMAT = (TYPE = CSV
FIELD_OPTIONALLY_ENCLOSED_BY = '\"');

COPY INTO MFG_SITE_RECOVERY
FILE_FORMAT = (TYPE = CSV
FIELD_OPTIONALLY_ENCLOSED_BY = '\"');
```

![alt text](/sfguide-getting-started-with-native-apps/screensaves/copy.png)

### Step 4 : Application Package create

Creation of the application package - via snowCLI
```bash
snow app run
```
![alt text](/sfguide-getting-started-with-native-apps/screensaves/snow_app_run_for_pck.png)
![alt text](/sfguide-getting-started-with-native-apps/screensaves/snowflake_app_pck.png)

### Step 5 : Addition of hellow world function in the application package
New functionality to our application we will modify UDF.py and redeployment
![alt text](/sfguide-getting-started-with-native-apps/screensaves/add_of_helloworld_func_2.png)

### Step 6 : Streamlit APllication Run 
From the deployed application we can observe the same on the snowflake 

![alt text](/sfguide-getting-started-with-native-apps/screensaves/streamlit1.png)
![alt text](/sfguide-getting-started-with-native-apps/screensaves/streamlit2.png)