# SQL Date Interval and Timestamps
## Queries examples for interval date and timestamps cases:
```sql

SELECT
  COUNT (DISTINCT (aircraft_id))
FROM flight
WHERE date BETWEEN '2015-08-01' AND CAST('2015-08-01' AS date) + INTERVAL '1' MONTH;
 
 ```
```sql

SELECT 
  CAST('2015-01-01' AS timestamp) + INTERVAL '5' DAY;

```
```sql

SELECT
  AVG(delay)
FROM flight
WHERE EXTRACT(MONTH from date) = 08;

```
```sql

SELECT
  EXTRACT(YEAR from date),
  AVG(delay)
FROM flight
GROUP BY EXTRACT(YEAR from date);

```
```sql

SELECT
	code,
  COUNT(flight.id),
  AVG(delay)
FROM route JOIN flight 
ON route.code = flight.route_code
WHERE date < current_date - INTERVAL '6' MONTH
GROUP BY
	code;

```
