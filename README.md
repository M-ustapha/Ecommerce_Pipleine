# End-to-End Data Engineering Project – dbt, Snowflake & Apache Airflow

## Overview

This project demonstrates a complete data engineering pipeline, leveraging **dbt** (Data Build Tool), **Snowflake** (cloud-based data warehouse), and **Apache Airflow** (workflow orchestration tool). It covers the entire data flow — from ingestion and transformation to workflow automation — built in a scalable and organized structure.

## Tech Stack

- **dbt Core** – Data transformation and modeling
- **Snowflake** – Cloud data warehouse
- **Apache Airflow** – Workflow scheduling and orchestration
- **Python** – Scripting and automation
- **Git** – Version control

## Project Structure

```
snowflake_data_project/
├── models/             # dbt models (staging, marts)
├── dags/               # Airflow DAGs for scheduling
├── logs/               # Airflow execution logs
├── seeds/              # Sample seed data for dbt
├── macros/             # Custom dbt macros
├── dbt_project.yml     # dbt project configuration
├── README.md           # Project documentation
```

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/ansamAY/dbt_snowflake_project.git
cd your-project-folder
```

### 2. Set Up the Virtual Environment

```bash
python -m venv venv
# For Mac/Linux:
source venv/bin/activate
# For Windows:
venv\Scripts\activate
```

### 3. Configure dbt to Connect to Snowflake

Edit the `profiles.yml` file located at `~/.dbt/` with your Snowflake credentials:

```yaml
snowflake_project:
  outputs:
    dev:
      account: your_snowflake_account
      database: finance_db
      user: dbt_user
      password: your_password
      warehouse: finance_wh
      role: ACCOUNTADMIN
      schema: raw
      type: snowflake
  target: dev
```

### 4. Run dbt Models

Execute the dbt models and perform data integrity tests:

```bash
dbt run
dbt test
```

### 5. Launch Apache Airflow

Start the Airflow web server and scheduler:

```bash
airflow standalone
```

