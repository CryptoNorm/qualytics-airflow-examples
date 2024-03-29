# Qualytics Airflow Examples

This repository contains the example code for an Airflow pipeline that load Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.


# Repository Files
**/dags/snowflake_lc_demo.py**  : Airflow pipeline to for multi stage architecture. 
 This DAG performs the following steps: 
 - lc_qscan_raw : Perform Qualytics Data Store Scan on files in S3 to detect anomolies
 - lc_append_raw_to_bronze : Use Snowflake COPY to load file data into Snowflake "Bronze" table
 - lc_qscan_bronze : Perform Qualytics Data Store Scan on Snowflake "Bronze" table to detect anomolies
 - lc_merge_bronze_to_silver :Use Snowflake MERGE to refine data and load into Snowflake "Silver" table
 - lc_qscan_silverLoad : Perform Qualytics Data Store Scan on Snowflake "Silver" table to detect anomolies
```mermaid
graph LR
A(lc_qscan_raw) --> B(lc_append_raw_to_bronze) --> C(lc_qscan_bronze) --> D(lc_merge_bronze_to_silve)  --> E[lc_qscan_silver]
```
**Update**
  ```
  QUALYTICS_API_BASE_URL = 'https://[ENV].qualytics.io/api/'
  os.path.dirname(__file__), '[REPO PATH]/qualytics-airflow-examples', 'qualytics')
 ```

**/qualytics/.env** : This file is not in the repository but need to be created.   It stores you Qualytics credentials
```
AUTH0_DOMAIN = "auth.qualytics.io"
AUTH0_AUDIENCE = "[Your Audience]"
AUTH0_ORGANIZATION = ""
AUTH0_CLIENT_ID = "[Your Client ID]"
AUTH0_CLIENT_SECRET = "[You Client Secret]"
```
> Contact Qualytics for details

**/qualytics/auth/get_token.py** : Calls Qualytics REST API to request an authentication Token for a Qualytics environment

**/qualytics/scan_functions/scan_data.py** : Calls Qualytics REST API to initation a SCAN operation
>  Note: The Qualytics code requires the following python modules:  jose, dotenv, requests, json

**/snowflake/DDL/create_landing_stage_tables.sql**: Creates 

# Airflow Server

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

### Setup
>  - Install airflow.providers.snowflake.operators.snowflake on your Airflow server
>  - Configure Airflow Connections for Snowflake






# Snowflake

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

# AWS

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

# Qualytics

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.



