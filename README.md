# U.S. Cities Database

The SQL file has **29.880** registered cities. All cities are located in the **United States**.

The SQL file contains two tables:

 - US_STATES: ID, STATE_CODE and STATE_NAME.

 - US_CITIES: ID, ID_STATE, CITY, COUNTY, LATITUDE and LONGITUDE.

The US_CITIES table has all (or almost all) cities from the **United States**.

## Compatibility
The [us_cities.sql](./us_cities.sql) file is compatible with MySQL. See [sqlite](./sqlite) for the sqlite3 compatible version.
## Samples

### US_STATES

| ID | STATE_CODE | STATE_NAME |
|:--:|:----------:|:----------:|
|  1 |     AL     |   Alabama  |
|  2 |     AK     |   Alaska   |
|  3 |     AZ     |   Arizona  |

### US_CITIES

| ID | ID_STATE |      CITY      |      COUNTY      | LATITUDE  | LONGITUDE  |
|:--:|:--------:|:--------------:|:----------------:|:---------:|:----------:|
|  1 |    2     |      Adak      |  Aleutians West  | 55.999722 | -161.20777 |
|  2 |    2     |    Akiachak    |      Bethel      | 60.891854 | -161.39233 |
|  3 |    2     |     Akiak      |      Bethel      | 60.890632 | -161.19932 |
|  4 |    2     |     Akutan     |  Aleutians East  | 54.143012 | -165.78536 |
|  5 |    2     |    Alakanuk    |     Kusilvak     | 62.746967 | -164.60228 |


## Export Data

You can use the following SQL command to export the data to a CSV file.

``` sql
SELECT
	US_CITIES.ID, US_STATES.STATE_CODE, US_STATES.STATE_NAME, US_CITIES.CITY, US_CITIES.COUNTY, US_CITIES.LATITUDE, US_CITIES.LONGITUDE
FROM
	US_STATES
INNER JOIN
	US_CITIES
ON
	US_STATES.ID = US_CITIES.ID_STATE
ORDER BY
	US_CITIES.ID ASC
INTO OUTFILE
	'C:/US_Cities.csv'
FIELDS TERMINATED BY
	';'
ENCLOSED BY
	''
LINES TERMINATED BY
	'\n';
```
For convenience, the generated CSV file is [here](./csv/us_cities.csv).

## License

This project was created under the [MIT license][1].

If you find some inconsistent data, such as a duplicated city, please open an issue explaining what is happening or directly fix the problem and send a Pull Request.

## References

This SQL dump was created based on the SQL dump that can be found at the following link:
[http://www.farinspace.com/us-cities-and-state-sql-dump/][2]

Some changes that have been made:

 - The **zip** column was deleted.
 - Some duplicated cities were deleted.
 - All data were reorganized (rows and columns).
 - It was included the Puerto Rico state name that was missing in the original SQL.
 - It was included the **US_STATES** table.

  [1]: LICENSE
  [2]: http://www.farinspace.com/us-cities-and-state-sql-dump/
