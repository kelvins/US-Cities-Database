# U.S. Cities Database

The SQL file has **29.880** registered cities. All cities are located in the **United States**.

The file contains the **state code**, the full **state** name, the **city** name, the **county**, **latitude** and **longitude** of all (or almost all) cities from the **United States**.

The data is ordered by state code, city and county.

## Sample

| State Code |    State   |     City     |    County   | Latitude |  Longitude |
|:----------:|:----------:|:------------:|:-----------:|:--------:|:----------:|
|     NY     |  New York  |   New York   |   New York  | 40.74838 | -73.996705 |
|     NY     |  New York  |   Cleveland  |    Oswego   | 43.24319 | -75.853691 |
|     ID     |    Idaho   |  Idaho City  |    Boise    | 43.75860 | -115.91843 |
|     AZ     |   Arizona  |    Phoenix   |   Maricopa  | 33.45100 | -112.06850 |
|     CA     | California |   Palo Alto  | Santa Clara | 37.44432 | -122.14968 |
|     CA     | California | Santa Monica | Los Angeles | 34.01762 | -118.49070 |
|     KS     |   Kansas   |   Nashville  |   Kingman   | 37.43441 | -98.417052 |


## License

This project was created under the [MIT license][1].

If you find some inconsistent data, such as a duplicated city, please open an issue explaining what is happening or directly fix the problem and send a Pull Request.

## References

This SQL dump was created based on the SQL dump that can be found at the following link:
[http://www.farinspace.com/us-cities-and-state-sql-dump/][2]

The zip column was deleted. Some duplicated cities were deleted. All data was reorganized.

  [1]: LICENSE
  [2]: http://www.farinspace.com/us-cities-and-state-sql-dump/
