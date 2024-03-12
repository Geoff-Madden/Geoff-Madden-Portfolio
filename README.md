COSTINGS ANALYSIS    

This was the task I was given to do that sparked my interest in data analytics and is described in my CV.
I have redacted to original to remove all the sensitive data.
64 suppliers prices were accessed by 420 products using a version of vlookup to access multiple pages of data.

=IFERROR(VLOOKUP(H7,INDIRECT("'"&INDEX(Supplier_List,MATCH(1,--(COUNTIF(INDIRECT("'"&Supplier_List&"'!$A$2:$s$2000"),H7)>0),0))&"'!$A$2:$s$2000"),2,FALSE),"Not Found")

The purpose was to track incoming prices to update the production costs and keep the margins profitable. 

ANALYSIS OF A STOCK PRICE DATASET

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
