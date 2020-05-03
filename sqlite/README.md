# U.S. Cities Database (sqlite3)

This version of the .sql file is compatible with sqlite3.

## Usage
To create the database:
```sh
sqlite3 us_cities_db < us_cities.sql
```
To open the database:
```sh
sqlite3 us_cities_db
```
To export as csv from within the sqlite console:
```sh
sqlite> .headers on
sqlite> .mode csv
sqlite> .output us_cities.csv
```
and then paste the following query into the console:
```sql
SELECT
	US_CITIES.ID, US_STATES.STATE_CODE, US_STATES.STATE_NAME, US_CITIES.CITY, US_CITIES.COUNTY, US_CITIES.LATITUDE, US_CITIES.LONGITUDE
FROM
	US_STATES
INNER JOIN
	US_CITIES
ON
	US_STATES.ID = US_CITIES.ID_STATE
ORDER BY
	US_CITIES.ID ASC;
```