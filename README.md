COSTINGS ANALYSIS    

This was the task I was given to do that sparked my interest in data analytics and is described in my CV.
I have redacted to original to remove all the sensitive data.
64 suppliers prices were accessed by 420 products using extended versions of vlookup to access multiple pages of data.

=IFERROR(VLOOKUP(H7,INDIRECT("'"&INDEX(Supplier_List,MATCH(1,--(COUNTIF(INDIRECT("'"&Supplier_List&"'!$A$2:$s$2000"),H7)>0),0))&"'!$A$2:$s$2000"),2,FALSE),"Not Found")

The purpose was to track incoming prices to update the production costs and keep the margins profitable. 

ANALYSIS OF A STOCK PRICE DATASET

1. What's the mean of the values in the Adj Close column?
2. What's the minimum value in the Low column?
3. What's the maximum value in the High column?
4. What's the difference between min_low and max_high ?
5. How many rows are there in the DataFrame?
6. On how many days (i.e. number of rows) was Change % greater than zero?
7. On how many days (i.e. number of rows) has Adj Close been greater than the
value in the final row?
8. Create a new DataFrame called df_2020 which is the same as df but contains
only the rows where Year == 2020 .
9. Continuing with df_2020 , calculate the .mean() of Change % for entries where
Weekday == Monday.
10. Calculate the sum of the Volume column in df_2020 for entries where Month == 3
11. Using df_2020 , determine when Adj Close was the highest.
12. Create a DataFrame called df_top_10 which contains the 10 entries from df with
the highest positive Change % values.
13. How many entries in df_top_10 were not on a Monday?
14. Create a new DataFrame called df_var , which the same as df but with an
additional column Variation % , which is equal to:
(( High - Low ) / Close ) * 100
15. Create a new DataFrame called df_var_value , which the same as df_var but
with an additional column Traded Value , equal to:
Volume * Adj Close

ANALYSIS OF A VEHICLE DATASET

1. What's the mean of the values in the weight column?
2. What's the maximum value in the horsepower column?
3. How many cars have a weight of equal to or greater than 3500 ?
4. Create a new DataFrame with an additional column called ratio , which equals
horsepower divided by weight
5. Create a new DataFrame containing only cars with an origin of 'usa'
6. What's the mean mpg of cars of origin usa ?
7. How many cars of origin usa have 8 cylinders ?
8. Create a new DataFrame (from the original df ) which does not contain the rows
with a missing value
9. What's the first (or only) mode value for horsepower in df_horsepower ?
10. Create a DataFrame containing only cars with a horsepower greater than or equal
to mode_hp in df_horsepower
11. What percentage of the cars in df_high_hp have 8 cylinders ?
12. Add a column called name_year to a copy of df , with each entry containing a
string in the following format: name + ' - 19' + model_year
13. On a copy of the df_name DataFrame, set the index of the DataFrame as the
name_year column
14. Create a function which takes name_year as the only parameter, and returns the
acceleration for any car in df_car_index

ANALYSIS OF FTSE DATA

About the Dataset
In the following section, you will be analysing The Financial Times Stock Exchange 100
(FTSE 100) Index data, pronounced, the 'Footsie hundred', is a share index of the 100
companies listed on the London Stock Exchange with the highest market capitalisation.

Importing the dataset
First use the .read_csv() function to import the file FTSE100.csv from the data folder,
assigning it to df DataFrame.

Tidy Data
Starting from a copy of df , create a new DataFrame called clean_df with the following
changes:
Drop the row with a Ticker value of RDSA
Drop the Strong Buy column

Change Column Data Type
Convert the values in the Mid-price (p) column to floats (keeping the column in the
same place)

Format Change Values
Part 1: Create a function called format_change which takes a string such as those in the
Change column and does the following:
1. If the last character is a % sign, remove it
2. Convert the string to a float
3. If that float is posiive, multiply it by 100
4. Return the resulting float

Part 2: Starting from a copy of price_df , create a new DataFrame called change_df
with a new column called Change (%) :
This should contain the result returned from the function created above when given the
original Change column value as the argument

Holding Summary
Starting from the holding above and change_df , build a new dictionary containing the
following keys and the appropriate values in the given data formats.

Market Comparison
Create a DataFrame called comparison_df with the following columns added to a copy of
change_df :
'Beat Market' - This should be a Boolean column with True for stocks where Change
(%) exceeds that of the average market change
'Buy Ratio' - This should equal the Buy column divided by the Brokers column

Investigate
We want to identify any companies which match a given set of rules, so that we can look into
them further.
We want to identify companies in watchlist that meet at least one of the following
requirements:
i) Any company in watchlist whose prices is equal to or lower than the given target price.
ii) Any company in watchlist where Buy Ratio is 0.5 or greater.
Using the watchlist below and comparison_df you defined, create a list of companies
meeting the requirements, call this list companies_list . The list should only have the
company names, not the price.

ANALYSIS OF CORONAVIRUS DATA

1. Create a new DataFrame called countries which is the same as df but with the
World row removed.
2. Check the shape of your DataFrame to confirm that countries has one row fewer
than df :
3. Define a DataFrame based on the countries DataFrame, but which only contains
the columns in cols (defined below) and assign this to a variable called
countries_dr
4. Using the countries DataFrame we created earlier, find the sum of
total_tests for countries in Africa , assigning the result, as an integer, to
africa_tests .
5. How many countries in Africa have no value recorded for the number of
total_tests column? Assign the result to africa_missing_test_data .
6. How many countries have a higher value for total_tests than the United
Kingdom ? Assign your answer to a variable called countries_more_tests .
7. Create a DataFrame called beds_dr which is based on the countries
DataFrame, but contains only the columns hospital_beds_per_thousand and
total_deaths_per_million .
8. Refer to the beds_dr DataFrame. What is the average
total_deaths_per_million for entries in beds_dr where
hospital_beds_per_thousand is greater than the mean?
9. Refer to the beds_dr DataFrame. What is the average
total_deaths_per_million for entries in beds_dr where
hospital_beds_per_thousand is less than the mean?
10. Refer to the countries DataFrame. Create a new DataFrame called
no_new_cases which contains only rows from countries with zero new_cases .
11. Refer to the no_new_cases DataFrame. Which country in no_new_cases
DataFrame has had the highest number of total_cases ?
12. Refer to the countries DataFrame. What is the sum of the population of all
countries which have had zero total_deaths ?
13. Create a function called country_metric which accepts the following three
parameters:
14. Use your function to collect the value for Vietnam for the metric
aged_70_older , assigning the result to vietnam_older_70 .
15. Create another function called countries_average , which accepts the following
three parameters:
a DataFrame "df" (which can be assumed to be such as countries )
a list of countries "countries" (which can be assumed to all be found in the location
column of the DataFrame)
a string "metric" (which can be assumed to be a column (other than location ) which
will be found in the DataFrame) . For instance, this string value can be
life_expectancy .
16. Use your countries_average function to find out the average
life_expectancy of countries in the g7 list defined below. Assign the result to the
variable g7_avg_life_expectancy .
Q.17 Refer to the countries DataFrame. Find the country with lowest value for
life_expectancy in the countries DataFrame, and create a string which is
formatted as follows:
'{country} has a life expectancy of {diff} years lower than the G7 average.'

ANALYSIS OF ENERGY DATA

Scatter plots

Histograms

Bar charts

Box plots

Pie charts

Modifying plots using matplotlib

Plotting with seaborn

ANALYSIS OF TRAFFIC DATA

Creating plots with Bokeh

Pandas-Bokeh

ANALYSIS OF A PROPERTY DATASET

CHOCOLATE RATINGS
