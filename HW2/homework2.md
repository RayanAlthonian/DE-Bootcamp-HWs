## Week 2 Homework

This file contains the solution for homework 2 in the data engineering course 

### Question 1. Load January 2020 data

**Answer:** 447,770 

**Script Name:** etl_web_to_gcs_hw.py

### Question 2. Scheduling with Cron

**Answer:** 0 5 1 * *

### Question 3. Loading data to BigQuery

**Answer:** 14,851,920

**Script Name:**: el_gcs_to_bq_hw.py

**Deployment Command:** prefect deployment build flows/02_gcp/el_gcs_to_bq_hw.py:el_parent_flow -n "Parameterized EL" -a

**SQL Query:** SELECT count(1) FROM `perceptive-tape-376218.de_camp.rides`

### Question 4. Github Storage Block

**Answer:** 88,605

### Question 5. Email or Slack notifications

**Answer:** 514,392

### Question 6. Secrets

**Answer:** 8
