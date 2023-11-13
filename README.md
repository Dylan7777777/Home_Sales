# Home_Sales

## Results of queries

1. What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.

![image](https://github.com/Dylan7777777/Home_Sales/assets/134973324/61ce1783-5d47-4d07-b884-cf043cc9b0d9)


2. What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? Round off your answer to two decimal places.

![image](https://github.com/Dylan7777777/Home_Sales/assets/134973324/eb138187-e2fc-4e62-9ab5-3355d2f850de)


3. What is the average price of a home for each year that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? Round off your answer to two decimal places.

![image](https://github.com/Dylan7777777/Home_Sales/assets/134973324/1278062e-ea87-4b4c-a7a7-353b020f9ef3)


4. What is the "view" rating for homes costing more than or equal to $350,000? Determine the run time for this query, and round off your answer to two decimal places.

    Original Data

![image](https://github.com/Dylan7777777/Home_Sales/assets/134973324/84114977-ec1c-4680-a2a5-e3a96c632ada)


5. Using the cached data, run the query that filters out the view ratings with an average price of greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime. Partition by the "date_built" field on the formatted parquet home sales data.

    Cached data

![image](https://github.com/Dylan7777777/Home_Sales/assets/134973324/c5b633a7-faec-4e75-bd81-ff4ed2bdc564)


    Parquet formatted data

![image](https://github.com/Dylan7777777/Home_Sales/assets/134973324/8f0218f7-e11c-4d0e-9465-a767e335b8ae)


The cached data had a faster runtime than the original data however surprisingly Parquet data ran slower than the original data.
