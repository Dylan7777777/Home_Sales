# Home_Sales

## Results of queries

1. What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.

+--------------------+----------+
|round(avg(price), 2)|year(date)|
+--------------------+----------+
|           296363.88|      2022|
|           301819.44|      2021|
|           298353.78|      2020|
|            300263.7|      2019|
+--------------------+----------+

2. What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? Round off your answer to two decimal places.

+--------------------+----------------+
|round(avg(price), 2)|year(date_built)|
+--------------------+----------------+
|           292859.62|            2010|
|           291117.47|            2011|
|           293683.19|            2012|
|           295962.27|            2013|
|           290852.27|            2014|
|            288770.3|            2015|
|           290555.07|            2016|
|           292676.79|            2017|
+--------------------+----------------+

3. What is the average price of a home for each year that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? Round off your answer to two decimal places.

+--------------------+----------------+
|round(avg(price), 2)|year(date_built)|
+--------------------+----------------+
|           285010.22|            2010|
|           276553.81|            2011|
|           307539.97|            2012|
|           303676.79|            2013|
|           298264.72|            2014|
|           297609.97|            2015|
|            293965.1|            2016|
|           280317.58|            2017|
+--------------------+----------------+

4. What is the "view" rating for homes costing more than or equal to $350,000? Determine the run time for this query, and round off your answer to two decimal places.

    Original Data

    +----+--------------------+
|view|round(avg(price), 2)|
+----+--------------------+
|   7|           403005.77|
|  51|           788128.21|
|  15|            404673.3|
|  54|           798684.82|
|  11|           399548.12|
|  29|           397771.65|
|  69|           750537.94|
|  42|            396964.5|
|  87|           1072285.2|
|  73|           752861.18|
|  64|           767036.67|
|   3|            398867.6|
|  30|            397862.0|
|  34|           401419.75|
|  59|            791453.0|
|   8|           398592.71|
|  28|           402124.62|
|  22|           402022.68|
|  85|          1056336.74|
|  16|           399586.53|
+----+--------------------+
only showing top 20 rows

--- 0.5126147270202637 seconds ---

5. Using the cached data, run the query that filters out the view ratings with an average price of greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime. Partition by the "date_built" field on the formatted parquet home sales data.

    Cached data

    +----+--------------------+
|view|round(avg(price), 2)|
+----+--------------------+
|   7|           403005.77|
|  51|           788128.21|
|  15|            404673.3|
|  54|           798684.82|
|  11|           399548.12|
|  29|           397771.65|
|  69|           750537.94|
|  42|            396964.5|
|  87|           1072285.2|
|  73|           752861.18|
|  64|           767036.67|
|   3|            398867.6|
|  30|            397862.0|
|  34|           401419.75|
|  59|            791453.0|
|   8|           398592.71|
|  28|           402124.62|
|  22|           402022.68|
|  85|          1056336.74|
|  16|           399586.53|
+----+--------------------+
only showing top 20 rows

--- 0.3375117778778076 seconds ---

    Parquet formatted data

    +----+--------------------+
|view|round(avg(price), 2)|
+----+--------------------+
|   7|           403005.77|
|  51|           788128.21|
|  15|            404673.3|
|  54|           798684.82|
|  11|           399548.12|
|  29|           397771.65|
|  69|           750537.94|
|  42|            396964.5|
|  73|           752861.18|
|  87|           1072285.2|
|  64|           767036.67|
|   3|            398867.6|
|  30|            397862.0|
|  34|           401419.75|
|  59|            791453.0|
|   8|           398592.71|
|  28|           402124.62|
|  22|           402022.68|
|  85|          1056336.74|
|  35|           401934.21|
+----+--------------------+
only showing top 20 rows

--- 0.642744779586792 seconds ---

The cached data had a faster runtime than the original data however surprisingly Parquet data ran slower than the original data.
