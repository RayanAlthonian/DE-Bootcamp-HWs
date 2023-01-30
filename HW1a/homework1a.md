# Homework 1 Solution

This file contains the solution to the homework

### Question 1. Knowing docker tags

**Answer:** --iidfile string          Write the image ID to the file

### Question 2. Understanding docker first run

**Answer:** 3 

## Prepare Postgres 

Kindly, refer to the upload-data_green_zones.ipynb file for the code

### Question 3. Count records

How many taxi trips were totally made on January 15?

**Answer:** 20530

*Query:*

`SELECT COUNT(*) 
FROM public.green_taxi_data
WHERE date(lpep_pickup_datetime) = '2019-01-15' AND date(lpep_dropoff_datetime) = '2019-01-15'`

### Question 4. Largest trip for each day

Which was the day with the largest trip distance Use the pick up time for your calculations.

**Answer:** 2019-01-15

*Query:*

`SELECT date(lpep_pickup_datetime),MAX(trip_distance) as td 
FROM public.green_taxi_data
GROUP BY date(lpep_pickup_datetime)
ORDER BY td DESC`

### Question 5. The number of passengers

In 2019-01-01 how many trips had 2 and 3 passengers?

**Answer:** 2: 1282 ; 3: 254

*Query:*

`SELECT passenger_count, COUNT(1) 
FROM public.green_taxi_data
WHERE date(lpep_pickup_datetime) = '2019-01-01' AND passenger_count IN (2,3) 
GROUP BY passenger_count`

### Question 6. Largest tip

For the passengers picked up in the Astoria Zone which was the drop off zone that had the largest tip? We want the name of the zone, not the id.

**Answer:** Long Island City/Queens Plaza

*Query:*

`SELECT doz."Zone" as dropOff_Zone, MAX(gt.tip_amount) as tip
FROM public.green_taxi_data as gt
INNER JOIN public.zones as puz ON gt."PULocationID" = puz."LocationID" 
INNER JOIN public.zones as doz ON gt."DOLocationID" = doz."LocationID" 
WHERE puz."Zone" = 'Astoria'
GROUP BY dropOff_Zone
ORDER BY tip DESC
LIMIT 1`



