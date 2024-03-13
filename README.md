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

Data Collection
Run the following cell to import and concatenate the datasets, assigning the result to
DataFrame data :

Data Processing
1. First of all, let's tidy up the data DataFrame:
Use the .rename() method to change the name of the level_0 column to Use
Use the .fillna() method to update all NaN values to 0
Use the .astype() method to convert all numerical columns ['Electricity',
'Natural Gas', 'Oil', 'District Heating', 'Other'] to integers
Use the .sum(axis=1) method to create a new column Total which contains the
sum of all numerical columns

Data Grouping
2. Create a new DataFrame called ss , using .groupby() to group DataFrame data
by column 'Sub-Sector' , which contains the .sum() for each of the numerical (energy
type) columns for each group:
3. Create a new DataFrame called use , using .groupby() to group DataFrame data
by column 'Use' , which contains the .sum() for each of the numerical (energy type)
columns for each group:
4. Create a new DataFrame called sector , using .groupby() to group DataFrame
data by column 'Sector' , and make use of .agg() method on the Total column
such that the new DataFrame has columns for 'sum' , 'mean' , and 'count' of the
values in 'Total' :

Data Visualisation
5. Refer to the ss DataFrame.
Create a histogram from the Electricity column of ss DataFrame using the .plot()
method: ss['Electricity']
6. Refer to the ss DataFrame.
Create a scatter plot of Natural Gas vs Total , to see the relationship between the two
columns of ss DataFrame.
7. Refer to the sector DataFrame.
Create a vertical bar chart of the 'sum' column of the sector DataFrame using the
.plot() method: sector['sum']
8. Refer to the given new_df_use DataFrame, which is identical to the use DataFrame
but excludes the Total column (see below for the code).
Create a horizontal and stacked bar chart from the new_df_use DataFrame, using the
.plot() method:

ANALYSIS OF TRAFFIC DATA

Exploratory Analysis
1. Use .groupby() to create a DataFrame called year which groups df by 'year' and contains the columns
['pedal_cycles', 'cars_and_taxis', 'all_hgvs'] , with the .sum() of each of these for each year:
2. We want to look at the change over time of each of these forms of transport relative to the earliest values (year 1993).
To do so, we will create an index. An index allows us to inspect the growth over time of a variable relative to some starting
value (known as the base). By convention, this starting value is 100.0 . If the value of our variable doubles in some future
time period, then the value of our index in that future time period would be 200.0 .
create a new DataFrame called year_index as a .copy() of year
for the index, select 1993 as the base year. This means that all values for 1993 should be equal to 100.0 . All
subsequent years should be relative to that
3. Having already imported and set up pandas_bokeh at the start of the notebook, we can now create a Bokeh plot of
year_index DataFrame simply using the .plot() method and saving to variable yi_fig .
4. Now that you have created your yi_fig variable using just .plot() method, make the following changes to the
specified properties of yi_fig :
Out[7]:
pedal_cycles cars_and_taxis all_hgvs
year
1993 100.000000 100.000000 100.000000
1994 100.229413 102.048581 102.143030
1995 103.358260 103.851256 104.900983
1996 101.675079 106.454909 108.160667
1997 101.853694 108.192646 110.718300
Out[8]: Figure(id = '1003', …)
(http
#add your code below
year_index = year.copy()
base = year_index.iloc[0]
year_index = (year_index/base)*100
year_index.head()
#add your code below
yi_fig = year_index.plot()
yi_fig
11/03/2024, 12:54 traffic - Jupyter Notebook
https://kloud.edukate.ai/user/cs-20150/pak-15159/notebooks/traffic.ipynb 5/10
change the text of the title to 'Change in road use by vehicle type over time'
change the axis_label of the yaxis to 'Road use by distance (1993 = 100)'
change the axis_label of the xaxis to 'Year'
remove the toolbar by changing the .toolbar_location attribute to None
change the legend location using legend.location attribute to 'top_left'
change the ticker of the xaxis to use the values [1993, 1998, 2003, 2008, 2013, 2018]
5. Create a DataFrame called green_2018 which:
uses only the data from df for 2018
groups this 2018 data by name
contains the columns ['pedal_cycles', 'buses_and_coaches'] which have the .sum() for each group
is sorted in descending order by the values for pedal_cycles
divide all of the values in the resulting DataFrame by 1000000
6. Use the .plot() method to create a horizontal, stacked bar chart from the green_2018 DataFrame, assigning it to
green_bar variable
7. Once you have created your green_bar variable (specifying only that it should be a stacked, horizontal bar plot),
modify the following properties of your variable such that:
the plot .width is 800 pixels
the axis_label of the xaxis is 'Vehicle miles (millions)'
the axis_label of the yaxis is 'Region'
the text of the title is 'Regional travel by bicycle and bus in 2018'
8. Create a DataFrame called length_motor as follows:
group df by ['year', 'name'] with columns for ['total_link_length_miles', 'all_motor_vehicles']
containing the .sum() of these:
9. From length_motor , create a new DataFrame called reg_density which has a row index of year (i.e. one row
for each year 1993-2018), and a column for each region (i.e. each unique value in name ), with the values within the
DataFrame being the appropriate million_vehicle_miles_per_road_mile for that year in the given region:
10. As we did earlier when creating year_index DataFrame, create a new DataFrame called density_index , which
is the same as reg_density except the all values are relative to the 1993 value, which should equal 100 . Do not
modify reg_density DataFrame.
11. Assign to density_plot a figure created by using the .plot() method on density_index DataFrame, with
the parameter hovertool=False .
12. Make the following changes to density_plot :
make the height and width both 800
remove the toolbar by changing the .toolbar_location attribute to None
change the legend location using legend.location attribute to 'top_left'
change the ticker of the xaxis to use the values [1993, 1998, 2003, 2008, 2013, 2018]

ANALYSIS OF A PROPERTY DATASET

1. Refer to the df DataFrame. Create a new DataFrame called res containing only entries from df with
a CLASSDESC of 'RESIDENTIAL' .
2. Create a new DataFrame called res_16 containing only properties from res with BEDROOMS greater
than 0 and less than 7.
3. Use .groupby() on res_16 DataFrame to create a Series with an index of BEDROOMS and values of
the .mean() of FULLBATHS for each number of BEDROOMS . Assign this series to a new variable called
bed_bath :
4. Refer to the bed_bath variable from above question, also note bed_bath is a pandas series data
object.
5. Refer to the res_16 DataFrame.
Using the res_16['BEDROOMS'] Series calculate .value_counts() for each value in the series
6. Refer to the beds variable from above question, also note beds is a pandas series data object.
Use the .plot() method on beds to create a bar plot with kind parameter set to bar and title
parameter set to Residential housing by number of bedrooms
Save your line plot into a variable called beds_bar
7. Create a function called zip_land which takes two arguments: a DataFrame (with the same columns
as df ) and an integer (which it can be assumed will always be present in the PROPERTYZIP column of the
DataFrame).
8. Refer to the df DataFrame. Create a new DataFrame called sales which contains only entries from
df with a SALEDESC of 'VALID SALE' .
9. Add a column to sales called PITTSBURGH , containing boolean values of True where
PROPERTYCITY equals PITTSBURGH and False if not.
10. Create a seaborn .violinplot() with the following properties:
x = 'PITTSBURGH'
y = 'FAIRMARKETTOTAL'
data = only entries from sales where sales['BEDROOMS'] == 1]
11. Create a seaborn .regplot() with the following properties:
x = 'SALEPRICE'
y = 'FAIRMARKETTOTAL'
data = only entries from sales where sales['GRADEDESC'] == 'EXCELLENT'

CHOCOLATE RATINGS

1. Load the dataset flavors_cacao.csv into a DataFrame called choco_df using the
file path 'data/flavors_cacao.csv' and display the first 5 rows of the DataFrame
using the .head() method.
2. Using the .loc method select the column named rating from the DataFrame
choco_df , Then filter the rows where the value in the column company_location is
equal to 'U.K.' . Store the resulting data in a variable called uk_ratings .
3. Using the .loc method select the column named rating from the DataFrame
choco_df , Then filter the rows where the value in the column company_location is
equal to 'Switzerland' . Store the resulting data in a variable called
swiss_ratings .
4. How many rows are in uk_ratings ?
5. What is the mean rating of the chocolate produced by companies in the UK?
6. What is the median rating of the chocolate produced by companies in the UK?
7. What is the Standard Error of the Mean (SEM) of the ratings of the chocolates
produced by UK companies?
8. How many rows are in swiss_ratings ?
9. What is the mean rating of the chocolate produced by Swiss companies?
10. What is the median rating of the chocolate produced by Swiss companies?
11. What is the Standard Error of the Mean (SEM) of the ratings of the chocolate
produced by Swiss companies?
12. Use box plots to compare ratings from the UK and Switzerland
13 Create a function called find_outliers that accepts a DataFrame as input. The
function will determine outliers in the rating column of the DataFrame using the
specified criteria.
14. Use your function find_outliers to determine the outliers in the choco_df
data, first filtering the dataframe so it contains only ratings from the UK

