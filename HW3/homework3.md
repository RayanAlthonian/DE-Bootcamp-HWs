## Homework 3 Solution 

This file illustrates my solution for HW 3. 

### Question 1: What is count for fhv vehicle records for year 2019?

**Answer:** 43,244,696

**Code:** `SELECT count(1) FROM perceptive-tape-376218.de_camp.external_fhv_2019`

### Question 2: What is the estimated amount of data that will be read when you execute your query on the External Table and the Materialized Table?

**Answer:** 0 MB for the External Table and 317.94MB for the BQ Table

### Question 3: How many records have both a blank (null) PUlocationID and DOlocationID in the entire dataset?

**Answer:** 717748

**Code:** `SELECT COUNT(1) FROM perceptive-tape-376218.de_camp.external_fhv_2019 WHERE PUlocationID IS NULL and DOlocationID IS NULL`

### Question 4: What is the best strategy to make an optimized table in Big Query if your query will always filter by pickup_datetime and order by affiliated_base_number?

**Answer:** Partition by pickup_datetime Cluster on affiliated_base_number

### Question 5:  Write a query to retrieve the distinct affiliated_base_number between pickup_datetime 03/01/2019 and 03/31/2019 (inclusive)

**Answer:** 647.87 MB for non-partitioned table and 23.06 MB for the partitioned table 

**Code:** 

*Query 1:*
`SELECT DISTINCT(affiliated_base_number) FROM perceptive-tape-376218.de_camp.fhv_2019_non_partitoned WHERE pickup_datetime BETWEEN '2019-03-01' and '2019-03-31'`

*Query 2:*
`SELECT DISTINCT(affiliated_base_number) FROM perceptive-tape-376218.de_camp.fhv_2019_partitoned_clustered WHERE pickup_datetime BETWEEN '2019-03-01' and '2019-03-31'`

### Question 6: Where is the data stored in the External Table you created?

**Answer:** GCP Bucket

### Question 7: It is best practice in Big Query to always cluster your data.

**Answer**: False




