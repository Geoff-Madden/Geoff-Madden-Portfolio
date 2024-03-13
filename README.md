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
10. Calculate the sum of the Volume column in df_2020 for entries where Month ==
3.
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

  






   


Import files into Pandas

Examine dataframes using df.head(), df.sample(8), df.info(), df.shape

Get basic statistics with df.describe()

Sorting and filtering data

Retrieving data using index, iloc, loc

Updating values and adding columns

ANALYSIS OF A VEHICLE DATASET

Dataset manipulation

Create functions

Column selection, row selection and masks

Combining filtering and indexing

String matching

Sorting

Modifying column data

Removing columns

ANALYSIS OF FTSE DATA

Clean the data

Use a function to changes column formats

Use for loops

Cleaning and Moderating a dataset

Removal of superfluous data

Filling missing values

ANALYSIS OF CORONAVIRUS DATA

Concatenation

Joining datasets

Using the pandas .groupby() DataFrame method

Using the pandas .agg() method

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
